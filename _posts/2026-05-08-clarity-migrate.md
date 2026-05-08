---
layout: post
title: "Clarity Migrate"
categories: [engineering, data]
---
## The Problem We're Solving

Every year, hundreds of health systems in the United States switch their electronic health record system to Epic. Some are moving from Cerner. Some from Meditech. Some from Allscripts. Some are consolidating multiple Epic instances into one.

When this happens, the clinical side gets most of the attention — training doctors, mapping workflows, configuring order sets. But behind the scenes, there's a massive data problem that nobody talks about until it's too late.

### The Pipeline Problem

Over the years, every health system builds hundreds of data pipelines. These are automated processes that move data from the EHR into reporting systems, analytics platforms, data warehouses, billing systems, quality dashboards, and regulatory feeds.

A typical health system has:
- 200-500 Informatica PowerCenter mappings
- 50-150 SQL stored procedures
- 30-80 HL7 interface feeds
- 20-50 flat-file extracts
- Dozens of custom scripts nobody documented

Every single one of these pipelines reads from tables in the old EHR. When you switch to Epic, those old tables don't exist anymore. The data is now in Epic's Clarity database, which has a completely different structure — different table names, different column names, different conventions for how data is stored.

Every pipeline must be rewritten.

### Why This Is So Painful

**It takes forever.** Each pipeline takes a consultant 2-5 days to manually convert. With 500 pipelines, that's 1,500 days of work — roughly 18 months with a team of 8 people.

**It costs a fortune.** At consulting rates, that's $10-20 million in professional services just for the data migration. This comes on top of the $100M+ the health system is already spending on the Epic implementation itself.

**It requires rare expertise.** To convert a pipeline, you need someone who understands both the old system (Cerner's data model) and the new system (Epic's Clarity database). These people are extremely hard to find. On a team of 8 consultants, usually only 2-3 know both systems well enough.

**The quality is inconsistent.** Junior consultants miss subtle but critical details about how Epic stores data. They sort by the wrong date column. They assume the first diagnosis in a list is the primary one. They use numeric codes instead of text values. These bugs are invisible during development and only surface in production — where they cause billing delays, incorrect quality reports, and compliance failures.

**The deadline doesn't move.** Epic go-live dates are immovable. If the data pipelines aren't ready, the health system operates blind — no dashboards, no reports, no analytics. Revenue suffers. Patient safety suffers.

### The Hidden Complexity of Epic's Data

Epic's database isn't just big (18,000-30,000 tables). It's genuinely strange. It was originally built on a 1960s programming language called MUMPS, and many of those design decisions survive today in the form of patterns that look wrong to anyone trained on modern databases.

For example:
- When a patient has multiple diagnoses for a visit, they're stored with a LINE number. But LINE 1 is NOT the primary diagnosis — it's just the first one entered. The primary diagnosis could be at LINE 5. There's a separate flag field you have to check.
- When you need to sort events chronologically, you can't use the date column. Multiple events on the same day all have the same date. Instead, Epic has a special decimal number that encodes both the date AND the sequence. You have to sort by that decimal number. This number counts days since December 31, 1840. Why 1840? Because that's what the MUMPS programming language chose in the 1960s.
- Category values like "Completed," "Scheduled," "Canceled" are stored as text, not as numeric codes. There are no lookup tables. You have to match on the exact text.
- ICD-10 diagnosis codes (which you need for billing and quality reporting) are NOT in the diagnosis table where you'd expect them. They're buried three joins deep through the claims tables.
- A field called INPATIENT_DATA_ID sounds like it identifies hospital admissions. It doesn't. 95% of records with this field are outpatient visits. It actually enables a workflow tracking feature.

Every migration team discovers these gotchas the hard way. Usually in production. Usually at great cost.

---

## What Clarity Migrate Does

Clarity Migrate converts legacy data pipelines to Epic Clarity automatically. You give it a pipeline file from your old system, and it gives you back a working Epic-native pipeline — tested, validated, and ready to deploy.

The core idea: an AI agent that has been taught everything about Epic's data model — all 6,630 documented tables, all 55,159 columns, all the naming conventions, all the gotchas — and uses that knowledge to do in minutes what a human consultant does in days.

### How It Works — The Simple Version

```
You:      Here's a Cerner Informatica mapping that builds a patient demographics table.
          [drops XML file]

Kiro:     Reading... Found 2 source tables (PATIENT, CLARITY_SER).
          Verified both exist in Epic Clarity.
          Found 4 transformations: filter, expression, lookup, load.

          Generated:
          ✓ PySpark job (148 lines)
          ✓ Target table DDL
          ✓ 26 automated tests
          ✓ All tests passing

          Done in 3 minutes.
```

### How It Works — The Detailed Version

**Step 1: Understanding the source.**
The agent reads the legacy pipeline file. If it's an Informatica XML, it parses the source tables, target table, transformations (filters, expressions, lookups, joins, aggregations), and the data flow between them. If it's SQL, it extracts the table references, joins, WHERE clauses, and business logic.

**Step 2: Finding the Epic equivalents.**
For each table referenced in the old pipeline, the agent searches an index of Epic's 6,630 tables to find the equivalent. If the old pipeline reads from Cerner's CV3_ENCOUNTER table, the agent finds that the Epic equivalent is PAT_ENC. It looks up the exact column names, data types, and relationships.

When there's no perfect match (for example, Cerner's CV3_CLINICAL_EVENT maps loosely to Epic's ORDER_PROC with only 87% confidence), the agent flags it for human review and explains why.

**Step 3: Applying Epic's rules.**
This is where the agent earns its keep. It reads a set of rules about how Epic stores data — the patterns that trip up every migration team — and applies them to the generated code.

If the old pipeline sorts by a date column, the agent knows to use Epic's decimal _REAL column instead. If the old pipeline looks up a diagnosis code, the agent knows that ICD-10 codes are in the CLM_DX table, not CLARITY_EDG. If the old pipeline filters on a status code, the agent knows to use the text value ('Completed'), not a number ('2').

These aren't guesses. These are rules derived from Epic's official documentation and validated against real Epic data.

**Step 4: Generating the code.**
The agent writes a complete PySpark job that reads from Epic Clarity (via JDBC), applies all the transformation logic from the original pipeline, and writes the results to the target data warehouse (Snowflake or Postgres). The code uses environment variables for all database credentials — never hardcoded.

It also writes a CREATE TABLE statement for the target table, with proper data types, primary keys, and indexes.

**Step 5: Writing and running tests.**
The agent writes automated tests that verify the generated code is correct:
- Does the code compile?
- Does it reference the right source and target tables?
- Are database credentials coming from environment variables (not hardcoded)?
- Are the key transformation keywords present (filter, join, age calculation, gender mapping)?
- Are Epic patterns applied correctly?

Then it runs the tests. If any fail, it reads the error, fixes the code, and re-runs. It keeps trying until all tests pass (up to 3 attempts).

**Step 6: Proving it works.**
Once tests pass, the agent can run the actual PySpark job against test databases — a MySQL instance with sample Epic data (source) and a Postgres instance (target). It verifies that data actually landed in the target table, checks row counts, validates the schema, and runs the job twice to confirm it's idempotent (produces the same results on re-run).

**Step 7: Committing the code.**
Only after the proof passes does the agent commit the code to git. It creates a branch with a timestamp, writes a commit message summarizing what was converted and the proof results, and pushes. If the proof didn't pass, nothing is pushed. Broken code never makes it to the repository.

---

## The Four Modes

### Read Mode — "What do I have?"

You drop legacy pipeline files into Read mode and get back an analysis report. No code is generated. The agent tells you:
- What source tables the pipeline references
- What the Epic equivalent is for each one (with confidence scores)
- What transformations are applied (filters, joins, aggregations)
- What flags to watch out for (ambiguous mappings, missing equivalents)
- How complex the conversion will be

**When you use this:** Day 1 of a migration engagement. Drop all 500 pipelines at once and get a complete inventory — what can be auto-converted, what needs manual review, and how long the project will take. This report alone is worth $50-100K to a health system because it replaces days of manual discovery.

### Write Mode — "Build me something new."

You describe what you need in plain English, and the agent builds it from scratch. You don't need a source pipeline — just a requirement.

"Build a pipeline that creates a 30-day readmission fact table from Epic Clarity, including patient demographics, admission diagnosis, length of stay, and the department of the index visit."

The agent figures out which Epic tables to use (PAT_ENC, PAT_ENC_HSP, PROBLEM_LIST, CLARITY_DEP), how to join them, how to calculate length of stay, and how to identify a readmission. It writes the PySpark, the DDL, the tests, and runs everything.

**When you use this:** Post-migration, when the health system needs new analytics capabilities that didn't exist in the old system. Instead of scoping a multi-day project, you get working code in minutes.

### Bidi Mode — "Convert this end-to-end."

The full conversion pipeline. Give it a legacy pipeline file, and it does everything: reads, maps, generates code, tests, proves, and pushes to git.

This is the main work mode during a migration sprint. A data engineer feeds 20 pipelines per day through Bidi mode, reviews the output, and merges the pull requests. What used to take the team months now takes days.

**When you use this:** The daily conversion workflow during a migration project. This is the mode that turns a 14-month project into a days-long project.

### Ask Mode — "Answer a question."

You ask a question about Epic data in plain English, and the agent generates the SQL, runs it, and gives you the answer along with an explanation of which tables it used and why.

"How many diabetic patients had an ER visit in the last 90 days and were readmitted within 30 days?"

The agent knows that "diabetic" means searching PROBLEM_LIST for active diabetes diagnoses. It knows "ER visit" means filtering PAT_ENC by department name (not a dedicated encounter type column). It knows "readmitted" means checking PAT_ENC_HSP for hospital admissions within 30 days. It knows to sort by the decimal _REAL date, not the text date column. It writes a 30-line SQL query that a human analyst would take an hour to construct.

**When you use this:** Ongoing, forever. Every analyst, every CMIO, every VP of Revenue Cycle can query Epic data without knowing SQL or Epic's schema. This is the mode that creates recurring SaaS revenue.

**What makes Ask mode different from ChatGPT or any generic text-to-SQL tool:**
A generic LLM would write `SELECT * FROM patients WHERE diagnosis = 'diabetes'`. That query doesn't work in Epic. There is no `patients` table with a `diagnosis` column.

Our agent knows Epic. It knows the patient table is called PATIENT. Diagnoses are in PROBLEM_LIST (for ongoing conditions) or PAT_ENC_DX (for visit-specific ones). The diagnosis name is in CLARITY_EDG, joined by DX_ID. Active problems have PROBLEM_STATUS_C_NAME = 'Active' (text, not a number). And to get the ER department, you join PAT_ENC to CLARITY_DEP on DEPARTMENT_ID and filter by DEPARTMENT_NAME.

This level of Epic-specific knowledge is what separates a toy demo from a real product.

---

## Who This Is For

### The Consulting Firm (Cardamom Health)

Cardamom Health is an Epic consulting firm based in Madison, Wisconsin, founded by former Epic employees. They serve 150+ health systems doing Epic optimization, data services, and AI/ML. Their CTO has publicly advocated for agentic AI approaches to healthcare data problems.

**Their current model:** Charge by the hour. Revenue is linear with headcount. To do more work, they need more consultants. Finding consultants who know both legacy EHRs and Epic is their biggest hiring constraint.

**With Clarity Migrate:**
- **Read mode** becomes a product they can sell: a migration assessment for $50-100K, delivered in hours instead of weeks
- **Bidi mode** makes their existing consultants 10x more productive: they review agent output instead of writing code from scratch
- **Ask mode** becomes a SaaS product: self-service Epic analytics sold as a monthly subscription to every health system they serve
- Junior consultants become productive in days instead of months — they learn Epic patterns by reviewing agent output

The revenue model shifts from selling hours to selling outcomes.

### The Health System CIO

The person who has to deliver the Epic migration on time and on budget.

**Their nightmare:** Pipeline conversions fall behind schedule. The data team is the bottleneck. Go-live happens with broken dashboards, missing reports, and incorrect quality measures. The board asks why they spent $100M on an EHR that can't produce a readmission report.

**With Clarity Migrate:**
- Day 1: Complete pipeline inventory with complexity scores and timeline estimates
- Days 2-5: Automated conversion of 500 pipelines with proof reports
- Go-live: Every pipeline tested, proven, and committed. No surprises.
- Post go-live: Self-service analytics for everyone who needs data

### The Clinical Informaticist (CMIO)

The doctor or nurse who bridges clinical practice and IT.

**Their frustration:** They need data answers but can't write SQL. Every question is a 3-5 day IT ticket. By the time the answer comes back, the meeting is over, the decision is made, and the data would have changed the outcome.

**With Clarity Migrate Ask mode:**
- "What's our 30-day readmission rate for heart failure patients?" → Answer in 10 seconds
- "Which departments have the highest no-show rate?" → Answer in 10 seconds
- "Compare medication count per patient between 2024 and 2025" → Answer in 10 seconds
- Export the SQL, share it with IT for the official dashboard

### The VP of Revenue Cycle

The person responsible for making sure the health system gets paid.

**Their fear:** A broken billing pipeline delays $2M per week in claims. The billing data model is the most complex part of Epic — 35+ tables with no direct link between clinical encounters and billing transactions. The previous migration team missed the ICD-10 code location and the CSN linkage path. It took 3 months to find and fix those bugs.

**With Clarity Migrate:**
- The billing-expert knowledge file encodes every critical join path and gotcha
- The agent knows ICD-10 codes are in CLM_DX (not CLARITY_EDG)
- The agent knows to bridge through ARPB_VISITS (not try a direct CSN join)
- Proof reports verify billing data before go-live
- Zero revenue leakage on Day 1

### The Data Engineer

The person who actually writes the code.

**Their reality:** They spend 70% of their time on research — looking up Epic table documentation, figuring out which table to use, understanding join patterns — and 30% on actual coding. Epic has 18,000+ tables. The documentation is one table at a time with no cross-referencing. They keep forgetting the rules (is LINE 1 the primary diagnosis? which date column do I sort by?).

**With Clarity Migrate:**
- Read mode: Drop the XML, immediately see which Epic tables to use
- Write mode: Describe the pipeline, get working code with tests
- The agent applies all the patterns correctly every time — no more forgetting
- Tests are generated automatically — no more skipping them under deadline pressure
- They review and refine instead of writing from scratch
- They learn Epic patterns by reading the agent's output

---

## The Epic Knowledge Engine

The reason this works is the knowledge layer. It's not a generic AI writing code. It's an AI that has been systematically taught the complete Epic data model and the rules that experienced consultants learn over years of practice.

### How the knowledge is organized

**The schema index.** All 6,630 Epic table schemas from Epic's official documentation site (open.epic.com/EHITables) are loaded into a SQLite database with full-text search. When the agent needs to find a table related to "billing transactions," it runs one SQL query and gets results in milliseconds. This is critical — without the index, the agent would have to scan 6,630 individual files and would time out before finding anything useful.

**The pattern rules.** Six rules that govern how Epic stores data differently from every other database. These rules are encoded in a markdown file that the agent reads before generating any code. Every rule includes examples of what's wrong (the way a generic LLM would do it) and what's correct (the way an Epic expert does it).

**The domain knowledge.** Separate files for billing and clinical data that contain the join paths, gotchas, and domain-specific rules that can't be inferred from the schema alone. For example, the billing file documents that there's no direct link between clinical encounters and billing transactions — you have to go through a bridge table — and explains why this matters and how to handle it.

**The cross-EHR mappings.** A file that maps table names from Cerner, Meditech, and Allscripts to their Epic equivalents, with confidence scores. This is what enables the agent to understand a Cerner pipeline and know which Epic tables to use.

### Why this can't be replicated by prompting ChatGPT

You could paste Epic documentation into ChatGPT and ask it to convert a pipeline. Here's why that doesn't work:

1. **Context window limits.** Epic's documentation is millions of tokens. You can't fit it all in one prompt. You need a searchable index.

2. **Hallucination.** Without verified schema data, the LLM will confidently generate table and column names that don't exist. Our agent searches the actual schema database and only uses verified tables.

3. **Pattern application.** Knowing that LINE ≠ priority is different from consistently applying that rule across every query in a 150-line PySpark job. Our pattern rules are injected into the agent's system prompt so they're applied to every line of generated code.

4. **Validation loop.** ChatGPT generates code and hopes it works. Our agent generates code, writes tests, runs them, reads the failures, fixes the code, and re-runs until everything passes. This self-correction loop catches the mistakes that slip through on the first attempt.

5. **Domain-specific join paths.** The CSN-to-billing linkage, the ICD-10 code location, the INPATIENT_DATA_ID misnomer — these are things you only learn from years of Epic experience. We've encoded them so the agent knows them from day one.

---

## The Dashboard

The platform includes a web dashboard built on Next.js with a Cloudflare-inspired dark design. It provides a visual interface for all four modes.

**Overview.** Stats at a glance: 6,630 schemas loaded, 414 tables with data, 5 subagents active. Quick-action cards for each mode. Recent run history with status badges.

**Read page.** Drag-drop area for pipeline files. Source EHR selector (Cerner, Meditech, Allscripts, Athena). Analyze button. Results show mapping table with confidence scores, flags for ambiguous mappings, and the full agent trace.

**Write page.** Text input for natural language requirements. Example prompts to get started. Generated file list with line counts. View code button.

**Bidi page.** File upload plus a stage progress bar (READ → WRITE → TEST → PROVE). Live streaming terminal showing agent activity — which schemas it's searching, which patterns it's applying, which files it's writing. Proof report with row counts and verification status.

**Ask page.** Text input for plain English questions. Example queries. Big answer display with the SQL that generated it, the tables used, and explanatory notes. Query history.

**Runs page.** Table of all runs with mode, pipeline name, status, duration, and table count. Filter and sort.

**Settings page.** Integration cards for Epic Clarity (source), Snowflake (target), PostgreSQL (dev target), GitHub (code push), and AWS Bedrock (LLM). Each card shows connection status, configuration details, and test/edit buttons. Security section showing PHI redaction, audit trail, encryption, and telemetry status.

---

## Security

The platform is designed for HIPAA-covered environments.

**What the agent processes:** Table names, column names, data types, SQL structures, ETL logic. This is metadata — descriptions of the data structure, not patient data itself.

**What the agent never sees:** Individual patient records, names, dates of birth, social security numbers, or any other protected health information.

**Even so, every precaution is taken:**

All text that passes through the system is scrubbed for 18 categories of protected health information before being logged, stored, or sent to the LLM. Social security numbers, medical record numbers, phone numbers, email addresses, dates of birth, IP addresses, patient names, ZIP codes, and account numbers are all redacted automatically.

Every action the agent takes is recorded in an immutable audit log. Each entry includes a timestamp, the action performed, the source and target, and an HMAC signature that makes tampering detectable.

Database credentials are encrypted at rest using industry-standard encryption. In generated code, credentials always come from environment variables — never hardcoded.

The agent binary has been stripped of all telemetry. There are zero outbound network calls except to the AWS Bedrock API (which runs in the customer's own AWS account under their own HIPAA Business Associate Agreement). No data phones home. No analytics. No tracking.

The container runs as a non-root user with read-only access to source files and write access only to the output workspace.

---

## What We've Proven

### The test suite

We ran 10 automated tests covering every capability of the platform:

- **Schema search:** Can the agent find Epic tables related to encounters? To billing? (Passed in 16-44 seconds)
- **Pattern knowledge:** Does the agent correctly explain LINE joins? _REAL date sorting? (Passed in 23-26 seconds)
- **Clinical domain:** Can the agent design a readmission query with the right tables and gotchas? (Passed in 52 seconds)
- **Billing domain:** Does the agent know the CSN-to-billing linkage path? Where ICD-10 codes live? (Passed in 22 seconds)
- **Cross-EHR mapping:** Can the agent map 5 Cerner tables to Epic with confidence scores? (Passed in 64 seconds)
- **Full Read mode:** Can the agent analyze a complete Cerner SQL pipeline and produce a mapping report? (Passed in 91 seconds)
- **Ask mode (clinical):** Can the agent write a 30-line diabetic readmission SQL query using correct Epic patterns? (Passed in 92 seconds)
- **Ask mode (billing):** Can the agent write an AR aging query? (Timed out at 2 minutes — query was too complex for the time limit, but partial output was correct)

9 out of 10 passed. The one timeout was a limit issue, not a quality issue.

### The live conversion

We ran a full Bidi conversion on a real Informatica PowerCenter mapping (m_patient_demographics.xml). The agent:

1. Parsed the XML and identified 2 source tables, 1 target table, and 4 transformations
2. Verified both source tables exist in Epic's schema index
3. Applied Epic conventions (text category values for gender, date arithmetic for age)
4. Generated a 148-line PySpark job with JDBC connectivity, filtering, expressions, and a provider lookup join
5. Generated a CREATE TABLE with primary key and indexes
6. Generated 26 automated tests covering compilation, table names, credential safety, and transformation logic
7. Ran all 26 tests — all passed
8. Produced a conversion report with full traceability, including a flag that one column (SPECIALTY) doesn't appear in Epic's schema index

Total time: approximately 3 minutes.

This is a pipeline that would take a consultant 2-3 days.

---

## The Business Opportunity

### The market

- 40% of hospital IT leaders are planning EHR migration projects in 2026
- Epic is the dominant destination — they hold 38% of the US hospital market and growing
- Each migration involves 200-1,000+ data pipelines that must be converted
- The data migration component typically costs $10-20M in professional services

### The math

| | Manual | Clarity Migrate |
|---|---|---|
| Pipelines | 500 | 500 |
| Time per pipeline | 3 days | 4 minutes |
| Total effort | 1,500 days | 33 hours |
| Calendar time | 18 months | 2 days |
| Cost | $15M+ | ~$50K compute |

Even if we're conservative and assume the agent handles 60% of pipelines fully automatically and 40% need human review, the project drops from 18 months to days and the cost drops by 80%.

### The revenue model

| Mode | When | Revenue |
|---|---|---|
| Read | Day 1 of engagement | Migration assessment fee ($50-100K) |
| Bidi | Days 2-5 | Project delivery (same fee, 10x faster, higher margin) |
| Write | Post-migration | Analytics pipeline upsell |
| Ask | Ongoing | SaaS subscription (per seat per month) |

Read and Bidi are project revenue. Ask is recurring revenue. The platform serves both models.

### The competitive advantage

Nobody else has this combination:
1. A headless, HIPAA-hardened autonomous agent
2. An indexed knowledge base of Epic's complete schema catalog
3. Domain-specific rules for billing and clinical data
4. Cross-EHR mapping tables with confidence scoring
5. A prove-then-push validation loop
6. All four modes (Read, Write, Bidi, Ask) on the same knowledge layer

Generic text-to-SQL tools don't know Epic. Epic consultants don't have agents. We have both.
