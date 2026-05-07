---
layout: post
title: "Data Migration Strategies for Healthcare Systems"
categories: [engineering, backend]
---
## Overview

There are three approaches to data migration when modernizing healthcare systems. The choice depends on how the system is used and the organization’s priorities. In healthcare, these map to **risk tiers** — not just technical approaches.

| Strategy | Risk | What Moves | Timeline |
| --- | --- | --- | --- |
| Reader-First | Low | Reports, dashboards, analytics queries | Month 1-6 |
| Bi-Directional | Moderate | Parallel systems during transition | Month 3-9 |
| Writer-First | High | ETL pipelines, data feeds, write-backs | Month 6-12 |

---

## Why Healthcare is Different

Healthcare isn’t “move data from A to B.” It’s a regulated, high-stakes environment where:

- A broken report can delay a CMS submission — **financial penalties**
- A bad data write can surface wrong info in a clinical workflow — **patient safety risk**
- Any data movement touching PHI needs audit trails — **HIPAA compliance**
- Epic changes the Clarity schema with every upgrade — **moving target**

---

## Strategy 1: Reader-First Migration

### What it means

Migrate everything that **reads** from Epic Clarity/Caboodle — reports, dashboards, quality measures, analytics queries. These are read-only operations that present data to analysts, clinicians, and executives.

### Why hospitals start here

- No risk to patient data integrity (read-only, nothing writes back)
- Immediate, visible ROI (reports run 10x faster on Snowflake)
- Regulatory reports (HEDIS, CMS Stars, meaningful use) modernize without touching clinical workflows
- Analysts can self-serve instead of waiting in the Crystal Reports queue

### How it works in Clarity

**Sarah (Data Architect) logs into Clarity.**

She goes to Migrate, creates a new migration, and connects the GitHub repo where Informatica XMLs are stored. She picks “Reader-First” strategy.

The agent runs. 10 minutes later she has:
- 41 PySpark jobs generated
- 41 DDL files for Snowflake tables
- 738 tests, all green
- A conversion report showing every Informatica expression mapped to PySpark

She clicks into the completed job and sees the lineage map — every source table flowing through transformations into target tables. She screenshots this for the steering committee deck.

She shares the lineage map link with James (the consultant). He opens it, sees the full picture, and flags that 3 mappings reference a deprecated table (`PAT_ENC_HSP`) that was merged into `PAT_ENC` in Clarity 23.1. The agent already flagged this in the conversion report.

### What the agent generates

For each Informatica XML mapping, the agent produces:
- A PySpark job that reads from MySQL (Epic Clarity), applies the same transformations, and writes to Snowflake
- A Snowflake DDL file (CREATE TABLE with correct types)
- Automated tests validating the conversion
- A conversion report with lineage, patterns used, and test results

### Supported source formats

- Informatica PowerCenter XML (available today)
- Crystal Reports .rpt (planned)
- SSRS .rdl (planned)
- Business Objects .rep/.biar (planned)

---

## Strategy 2: Bi-Directional Migration

### What it means

During the transition period (which can be 6-18 months for a hospital), both old and new systems run in parallel. Data must stay consistent across both.

### Why this matters in healthcare

- Hospitals do phased rollouts — department by department, not big-bang
- During transition, some reports read from Clarity, some from Snowflake
- Financial data reconciliation is legally required (SOX-equivalent for hospital finance)
- If a regulatory report runs in both systems and produces different numbers — that’s an audit finding

### How it works in Clarity

**Month 3-6: Phased Rollout**

The team decides to roll out department by department. Cardiology goes first.

Sarah goes to the Go-Live Readiness dashboard. It shows:
- Cardiology: 12 reports migrated, all validated, 3 signed off by Dr. Chen, 9 pending sign-off
- Emergency Dept: 8 reports migrated, 6 validated, 2 have data drift warnings
- Internal Medicine: not started

She sets Cardiology to dual-write mode. Now every night, the PySpark jobs write to BOTH the old MySQL staging tables (so legacy Crystal Reports still work) AND the new Snowflake tables (so the new dashboards work).

The Data Drift Monitor runs every 6 hours. On day 3, it flags that `FACT_ENCOUNTER` in Snowflake has 12 more rows than MySQL. She investigates — a late-arriving encounter got picked up by the Snowflake incremental load but the Informatica job hasn’t run yet. Not a real issue. She marks it “expected” and the drift monitor learns to ignore timing gaps under 24 hours.

After 2 weeks of dual-write with zero drift, the Cardiology director signs off. Sarah flips Cardiology to Snowflake-only mode. The old Crystal Reports for that department get decommissioned.

She repeats for each department. The go-live dashboard shows progress ticking up from 15% to 40% to 78% to 100% over 4 months.

### Key capabilities

- **Dual-write mode**: Generated PySpark jobs write to both MySQL staging and Snowflake simultaneously
- **Data drift monitor**: Scheduled checks that compare row counts, checksums, and aggregates between source and target. Alerts when systems diverge beyond a configurable threshold.
- **Go-live readiness dashboard**: Visual status of which departments/reports are migrated, validated, and signed off
- **Rollback**: If Snowflake target diverges, auto-generated recovery scripts restore from source of truth

---

## Strategy 3: Writer-First Migration

### What it means

Migrate ETL pipelines that **write** data — data entry feeds, lab result ingestion, claims submissions, clinical registry updates. These are write operations that push data into clinical and financial systems.

### Why this is the highest risk

- Writing to Epic requires Epic-approved integration methods (Bridges, Open.Epic, Interconnect, FHIR APIs)
- Every write path needs HL7/FHIR compliance for interoperability
- PHI writes need audit trails (HIPAA §164.312)
- Wrong data written to a patient chart is a patient safety event
- Wrong data written to billing is a fraud risk (False Claims Act)

### How it works in Clarity

**Month 6-9: Write Path Migration**

Once the read path is fully migrated, the team tackles the write path.

They have an Informatica workflow that ingests lab results from an external lab vendor, transforms them, and writes to Epic via HL7 Bridge. This is a clinical write path — if it breaks, lab results don’t show up in Epic and clinicians don’t see them.

Sarah goes to Migrate and selects “Writer-First” strategy.

The agent flags this as high risk because:
- It writes to a clinical system (patient-facing)
- It contains PHI (PAT_ID, RESULT_VALUE)
- The target is an Epic API, not a database table

The generated PySpark job includes:
- FHIR resource mapping (lab result to FHIR R4 Observation)
- An audit trail for every record written
- A sandbox validation step that runs against Epic’s test environment first
- A rollback script that can reverse the last batch if something goes wrong

Before this goes to production, it goes through an approval workflow:
1. The data architect reviews the generated code
2. The Epic analyst validates the FHIR mapping
3. The compliance officer confirms the PHI handling
4. The clinical informatics director signs off

Each approval is tracked in the migration timeline.

### Key capabilities

- **FHIR pipeline generation**: Convert legacy HL7v2 feeds to FHIR R4 bundles
- **CDC pattern detection**: Identify incremental load patterns in Informatica and convert to streaming/micro-batch PySpark with MERGE statements
- **Write-back validation sandbox**: Run converted write pipelines against Epic’s test environment before production
- **Audit trail generation**: Every record written is logged with timestamp, user, target system, and PHI columns touched

---

## Cross-Cutting: Reconciliation

### The #1 question from every CFO and CMO

> “How do we know the numbers match?”
> 

Every migration — regardless of strategy — needs validation. After each migration job completes, Clarity auto-generates reconciliation checks.

### How it works

Sarah runs a migration against staging Snowflake. The jobs complete. She goes to the Validation tab in the job detail view.

The reconciliation report shows every table side by side:
- `DIM_PATIENT`: 48,231 rows in source, 48,231 in target. Checksums match. Green.
- `FACT_ENCOUNTER`: 312,445 rows in source, 312,402 in target. 43 rows missing. Yellow warning.

She clicks “View Diff” on `FACT_ENCOUNTER`. Clarity shows her the 43 rows that exist in source but not target. They’re all encounters with `APPT_STATUS_C = 6` (canceled but with a specific sub-status). The Informatica filter was `APPT_STATUS_C IN (2,6)` but the agent converted it as `APPT_STATUS_C = 2`. She edits the PySpark job, re-runs, and now it’s green across the board.

Without reconciliation, this would have gone to production with 43 missing encounters. In revenue cycle, that’s potentially $43K+ in unbilled charges.

### What gets compared

| Metric | What it catches |
| --- | --- |
| Row count | Missing or extra records |
| Column count | Schema drift (added/removed columns) |
| Null rate | Transformation logic errors (NVLs not applied) |
| Aggregate checksums | Data value differences (SUM, AVG, MIN, MAX on key columns) |
| Date ranges | Temporal gaps or truncation |
| Referential integrity | Broken foreign keys after migration |

---

## Cross-Cutting: PHI Detection

### HIPAA compliance, built in

Every migration job gets a PHI scan before it runs. The agent detects columns that contain Protected Health Information based on the HIPAA Safe Harbor standard (18 identifier types).

### How it works

When Sarah creates a new migration, the first thing she sees is:

> “This migration involves 8 high-risk PHI columns including PAT_FIRST_NAME, PAT_MRN_ID, and BIRTH_DATE. Snowflake column-level masking policies are recommended before granting analyst access.”
> 

The lineage map shows PHI columns with a red shield icon. The reconciliation report includes a PHI section confirming that PHI columns in the target have encryption-at-rest and masking policies applied.

When she shares the migration report with the compliance team, they can see exactly which PHI flows where — without needing to read any code.

### PHI classification

| Risk Level | Column Examples | Recommendation |
| --- | --- | --- |
| High | PAT_FIRST_NAME, PAT_MRN_ID, SSN | Hash or tokenize in target. Do not store in plaintext outside Epic. |
| High | BIRTH_DATE | Consider age bucketing (18-25, 26-35) for analytics tables. |
| Medium | ZIP | Truncate to 3-digit prefix per Safe Harbor. Full ZIP is PHI if population < 20,000. |
| Medium | HOSP_ADMSN_TIME | Acceptable for operational analytics. Restrict for de-identified datasets. |
| Safe | DEPARTMENT_ID, ENC_TYPE_C | No restrictions. |

---

## Application Features Summary

| Feature | Who Uses It | Why They Care |
| --- | --- | --- |
| Strategy selector | Data architects | Pick the right approach — not everything is the same |
| Reconciliation reports | Data architects, auditors | “Prove the numbers match” — the #1 question |
| Go-live readiness dashboard | Project managers, CIO | “How far along are we?” — tracks the 12-month program |
| Dual-write mode | Data engineers | “Run both systems safely during transition” |
| Data drift monitor | Data engineers, on-call | “Alert me if systems diverge” |
| PHI detection | Compliance, security | “Show me where patient data flows” — HIPAA audit readiness |
| Writer-first migration | Epic analysts, clinical informatics | “Modernize our data feeds” — the next frontier |
| Lineage map | Everyone | Visual source-to-target flow for every migration |

---

## The Thread Connecting Everything

**Trust.**

Hospitals won’t migrate to Snowflake unless they trust the data is correct, the PHI is protected, and they can roll back if something goes wrong. Every feature above is a trust signal.

- Reconciliation says: “The numbers match. Here’s proof.”
- PHI detection says: “We know where patient data flows. It’s protected.”
- Dual-write says: “You can run both systems until you’re confident.”
- Go-live readiness says: “Here’s exactly where you are in the program.”
- Rollback says: “If something goes wrong, we can undo it.”

The technology is table stakes. The trust is the product.