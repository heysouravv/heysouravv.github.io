---
layout: post
title: "Epic Clarity — Agentic AI Layer"
categories: [engineering, data]
---

**Purpose:** Intelligence map of Epic Clarity's data topology for teams building an agentic AI layer on top of clinical EHR data. Covers all 12 domains, agent use cases, investment wedges, build sequence, and architecture decisions.

---

## Quick Orientation

|  | Chronicles | Clarity | Caboodle |
| --- | --- | --- | --- |
| **Type** | Hierarchical MUMPS/Caché DB | Relational SQL (~30,000 tables) | Star schema EDW (~300 tables) |
| **Purpose** | Live clinical operations | Reporting & analytics | Dashboards & KPIs |
| **Granularity** | Full operational record | Record-level, full depth | Aggregated, curated subset |
| **Freshness** | Real-time | T-1 (nightly ETL) | T-1 (nightly ETL) |
| **AI Surface** | Not queryable directly | **Primary agent surface** | Secondary / faster reads |
| **External data** | No | No | Yes (claims, registries) |

>  **The insight:** Clarity's complexity — 30,000 tables, ZC_ join dependencies, continuation tables — is the moat. Whoever builds schema intelligence on top of it first wins. The difficulty is the feature.
> 

---

## Critical Constraints — Read Before Building

>  **These are not edge cases. Every one surfaces in the first month.**
> 
- **T-1 freshness** — All data is one day old. Agents must surface data-as-of timestamps on every output. Never use Clarity for real-time operational decisions.
- **Date format** — Dates stored as days since `12/31/1840` in `_REAL` columns (MUMPS heritage). All time-series logic requires conversion before use.
- **ZC_ dependency** — Every categorical field (gender, race, order status, encounter type) is a numeric code requiring a `JOIN ZC_*` for human-readable output. LLM-generated SQL that skips this produces unreadable garbage.
- **Continuation tables** — `PATIENT`, `PATIENT_2`, `PATIENT_3` are one logical record. Same for `CLARITY_SER`, `ORDER_MED`, others. Querying only the base table silently loses data.
- **LINE column pattern** — One-to-many relationships use a `LINE` column (MUMPS inheritance). Appears in medications, flowsheets, diagnoses, charge lines. Agents that ignore this produce row-multiplied aggregations.
- **30K table surface** — RAG over the data dictionary is the only viable architecture. No LLM can navigate this at context scale. Build schema retrieval before writing any agent logic.
- **Multi-tenant schema variation** — Health systems customize their Clarity schemas. An agent built against one instance will silently fail against another. Tenant-aware schema isolation is the core technical moat.

---

## Domain Map — 12 Subject Areas

### 01 · Patient Identity & Demographics

**Key Tables:** `PATIENT` · `PATIENT_2` · `PATIENT_3`

**Fields & Subtypes**

| Field Group | Detail |
| --- | --- |
| Identity | MRN, DOB, gender, race, ethnicity |
| Contact | Language, address, zip code |
| Linkage | Guarantor ID, coverage ID → payer |
| Status | Patient status flags, merge history |

**Agent Use Cases**

- Identity resolution and deduplication across source systems
- SDOH risk stratification using zip-level poverty index and language barriers
- Patient cohort builder for population health programs
- Outreach eligibility filtering by demographics and payer

---

### 02 · Encounters & Visits

**Key Tables:** `PAT_ENC` · `PAT_ENC_2` · `PAT_ENC_DX` · `HSP_ACCOUNT`

**Fields & Subtypes**

| Field Group | Detail |
| --- | --- |
| Core | Visit date/time, encounter type, department |
| Settings | Ambulatory · Inpatient · ED · Telehealth · Telephone · MyChart |
| Inpatient | LOS, discharge disposition, ADT events (admit-discharge-transfer) |
| Diagnosis | Encounter-level ICD-10 linkage |

**Agent Use Cases**

- Readmission prediction via encounter sequence modeling
- Care pathway anomaly detection across patient timelines
- No-show and cancellation propensity scoring
- ED-to-inpatient conversion analysis
- LOS benchmarking against cohort and DRG norms

---

### 03 · Clinical Documentation

**Key Tables:** `PROBLEM_LIST` · `ALLERGY` · `IP_FLWSHT_REC` · `HNO_NOTE_TEXT` · `PAT_ENC_DX`

**Fields & Subtypes**

| Field Group | Detail |
| --- | --- |
| Diagnoses | ICD-10 codes, problem list, onset date |
| Notes | Progress notes, discharge summaries, surgical notes, consult notes — **free text** |
| Observations | Vital signs, flowsheet rows, measurements |
| History | Immunizations, social history, SDOH fields |

>  **`HNO_NOTE_TEXT` is the highest-value unstructured table in Clarity.** This is where the clinical story lives. Every NLP use case runs through here.
> 

**Agent Use Cases**

- NLP / LLM extraction from note text — chief complaint, HPI, assessment, plan
- Diagnosis coding accuracy audit — ICD vs. free-text alignment
- Clinical decision support triggers from flowsheet deviations
- Automated prior auth documentation generation
- Allergy-drug interaction alerting

---

### 04 · Orders & Medications

**Key Tables:** `ORDER_PROC` · `ORDER_MED` · `MAR_ADMIN_DOSES` · `RX_PHR_ORDER`

**Fields & Subtypes**

| Field Group | Detail |
| --- | --- |
| Orders | Order type, datetime, ordering provider, priority, status |
| Medications | Route, dose, frequency, administration record (MAR) |
| Pharmacy | Dispenses, refills, renewals, IV infusions |
| Protocol | Order set linkage, standing orders, protocol flags |

**Agent Use Cases**

- Polypharmacy risk detection across multi-drug regimens
- Medication adherence inference from refill gap analysis
- Order set optimization — co-ordered items correlated against outcomes
- High-cost drug utilization monitoring
- Formulary compliance enforcement and alerting

---

### 05 · Labs & Results

**Key Tables:** `ORDER_RESULTS` · `LNS_RESULT` · `LNS_SPECIMEN` · `CLARITY_COMPONENT`

**Fields & Subtypes**

| Field Group | Detail |
| --- | --- |
| Results | Value, unit, reference range, abnormal flag, status |
| Specimen | Collection datetime, specimen type, accession number |
| Categories | Chemistry · Hematology · Microbiology / cultures · Pathology |
| POC | Point-of-care and rapid testing |

**Agent Use Cases**

- Trend-based early warning from deteriorating lab trajectories over time
- Sepsis, AKI, and deterioration alerting from multi-lab sequences
- Critical value notification gap detection
- Lab utilization and redundancy reduction by ordering pattern
- Research cohort identification by lab phenotype

---

### 06 · Imaging & Radiology

**Key Tables:** `ORDER_PROC` (rad) · `RAD_EXAM` · `CLARITY_PROC` · `Cupid` (cardiology)

**Fields & Subtypes**

| Field Group | Detail |
| --- | --- |
| Orders | CPT codes, modality, ordering indication, priority |
| Results | Report text (free text), read datetime, radiologist |
| Modalities | X-ray · CT · MRI · Ultrasound · Echo · Cath · Nuclear |
| Procedures | Interventional, procedural imaging |

**Agent Use Cases**

- LLM extraction from radiology report text — incidental finding triage
- Imaging appropriateness scoring against clinical guidelines
- Repeat imaging detection and cost flagging
- Order-to-read turnaround time SLA monitoring

---

### 07 · Scheduling & Access

**Key Tables:** `PAT_ENC` (appt view) · `CLARITY_DEP` · `CLARITY_SER_DEPT`

**Fields & Subtypes**

| Field Group | Detail |
| --- | --- |
| Appointments | Datetime, type, status, slot, provider, location |
| Outcomes | No-show flag, cancellation reason, reschedule history |
| Access | Wait time, referral source, waitlist position |
| Type | New patient · Follow-up · Procedure · Urgent · Waitlist |

**Agent Use Cases**

- Intelligent slot fill and open access optimization
- No-show prediction driving proactive outreach
- Referral leakage detection — did the patient follow through?
- Access equity analysis by zip code, race, and payer
- Demand forecasting for capacity planning by service line

---

### 08 · Billing & Revenue Cycle

**Key Tables:** `HSP_ACCOUNT` · `ARPB_TRANSACTIONS` · `CLARITY_EDI` · `COVERAGE` · `ACCOUNT`

**Fields & Subtypes**

| Field Group | Detail |
| --- | --- |
| Charges | CPT / DRG codes, charge amount, charge drop timing |
| Claims | Payer, claim status, denial reason, remittance |
| AR | AR aging, patient balance, co-pay, write-offs |
| Auth | Authorization records, referral linkage |

**Agent Use Cases**

- Denial prediction before claim submission — intercept at charge entry
- Undercoding / upcoding audit — ICD vs. charges alignment
- Prior authorization automation from clinical documentation
- Revenue leakage detection — charges not dropped post-procedure
- Payer contract performance analysis and renegotiation intelligence

---

### 09 · Operational & Capacity

**Key Tables:** `ADT_ARRIVAL` · `ADT_DAYS` · `OT_CASE_RECORD` · `BED_CENSUS`

**Fields & Subtypes**

| Field Group | Detail |
| --- | --- |
| Beds | Status, unit, service line, census by hour |
| OR | Case start/end, surgeon, turnover time, cancellation reason |
| Flow | Patient transport, transfer events, escalation flags |
| Staffing | Assignments, coverage gaps, float pool |

**Agent Use Cases**

- Real-time bed demand prediction and proactive discharge planning
- OR block utilization optimization — recover unused time
- LOS outlier detection triggering case management workflow
- Patient flow bottleneck analysis — ED through inpatient
- Staffing demand-supply mismatch alerting by unit and shift

---

### 10 · Providers & Workforce

**Key Tables:** `CLARITY_SER` · `CLARITY_SER_2` · `CLARITY_EMP` · `SER_DEPT_ATTND`

**Fields & Subtypes**

| Field Group | Detail |
| --- | --- |
| Identity | NPI, specialty, department, credentials, DEA |
| Attribution | Ordering, attending, referring, and cosigning linkage |
| Care team | Composition, role, shift, assignment |
| Activity | User access logs, documentation timestamps, after-hours patterns |

**Agent Use Cases**

- Provider performance benchmarking across outcomes, utilization, and coding
- Referral pattern analysis and out-of-network leakage detection
- Care team attribution for value-based contract performance
- Clinical variation analysis by provider and service line
- Burnout proxy signals from documentation burden and after-hours login patterns

---

### 11 · Population Health & Quality

**Key Tables:** `REGISTRY_PATIENT` · `QM_RESULT` · `CARE_PLAN` · `HEALTHY_PLANET_*`

**Fields & Subtypes**

| Field Group | Detail |
| --- | --- |
| Measures | HEDIS, CMS Stars, MIPS, MACRA result values |
| Gaps | Care gap flags, measure numerator/denominator status |
| Risk | Patient risk scores, registry membership, tier |
| SDOH | Social risk factors, community resource linkage |

**Agent Use Cases**

- Automated care gap closure via outreach agent
- Risk stratification driving proactive intervention prioritization
- Quality measure trajectory forecasting for month-end performance
- SDOH-adjusted outcome benchmarking for equity reporting
- Value-based contract P&L attribution by attributed population

---

### 12 · System & Configuration *(Foundation Layer)*

**Key Tables:** `ZC_*` (all category master files) · `CLARITY_DEP` · `CLARITY_POS`

**Fields & Subtypes**

| Field Group | Detail |
| --- | --- |
| Code maps | Numeric code → display value for every categorical field |
| Structure | Department hierarchy, facility structure, POS codes |
| Security | User roles, access levels, build configuration |
| Metadata | Epic version, module activation, local customizations |

>  **Every domain query depends on this layer.** ZC_ joins are a precondition for human-readable output across all 11 other domains. Build the ZC_ resolver before writing any agent logic.
> 

**Agent Use Cases**

- Schema-aware SQL generation — LLM grounding on ZC_ maps is mandatory
- Data dictionary embedding for RAG-based analytics assistant
- Role-based query scoping in the agent access control layer
- Cross-domain lineage mapping for compliance audit trails

---

## Agent Architecture — How the Layer Stacks

```
USER / WORKFLOW TRIGGER
Natural language query  ·  scheduled job  ·  API event  ·  alert threshold

        ↓

[ 01 ]  ORCHESTRATION LAYER
        Intent classification
        Domain router  →  selects one of 12 Clarity domains
        ReAct planning loop  →  multi-step decomposition
        Memory / state management across turns

        ↓                              ↓

[ 02a ]  NLP / LLM MODULE         [ 02b ]  SQL GENERATION MODULE
         Free-text extraction               Schema RAG over data dictionary
         HNO_NOTE_TEXT parsing             ZC_ map grounding (mandatory)
         Summarisation                      Domain-scoped query builder
         Structured field population        Query validation + explain plan

                    ↓                    ↓

        [ 03 ]  CLARITY DATABASE LAYER
                ~30,000 SQL tables  ·  12 domains
                Nightly ETL  ·  T-1 freshness
                Domain-scoped views recommended over raw tables

                            ↓

                [ 04 ]  OUTPUT LAYER
                        Insight cards  ·  alerts  ·  triggers
                        Draft documents (prior auth, appeal letters)
                        Downstream API calls (RCM system, payer portal, care management)
                        Data-as-of timestamp on every output  ←  non-negotiable
```

>  **The domain router is the most consequential design decision.** Intent misclassification routes a billing query to clinical tables and produces numerically plausible wrong answers — which is worse than an obvious error. The router must be purpose-built, not a general-purpose prompt.
> 

---

## High-Value Wedges — VC / PE Lens

*Ranked by combined score: willingness to pay + time-to-ROI + structural moat.*

| Domain | Agent Wedge | TAM Signal | Moat | Sharp Insight |
| --- | --- | --- | --- | --- |
| **Billing / RCM** | Denial prediction + auto-appeal | $20B+ RCM market | Payer-specific model training | CFO-level pain. Denial rate is a visible P&L line. Fastest path to a signed contract. |
| **Scheduling** | No-show prediction + slot fill | Access crisis is acute | Cross-system network effect | Every unfilled slot is quantifiable lost revenue. Easy to instrument ROI from day one. |
| **Clinical Docs** | Prior auth automation via NLP | $35B admin waste annually | Fine-tuned on Epic note schemas | `HNO_NOTE_TEXT` is the crown jewel. Unstructured data no one else has modeled well. |
| **Labs** | Deterioration early warning | Patient safety liability | Outcome-labeled training data | Sepsis and AKI are the two lead use cases. Direct patient harm reduction narrative. |
| **Population Health** | Care gap closure + VBC attribution | VBC contract penetration growing | Measure-specific logic + payer rules | HEDIS and CMS Stars drive the ROI. Requires deepest Epic integration to win. |
| **OR / Capacity** | Block utilization optimizer | $150B surgical market | OR data is notoriously siloed | 30% of block time goes unused industry-wide. Direct surgical margin impact. |
| **Provider Analytics** | Clinical variation + benchmarking | MIPS / value-based pressure | Multi-system benchmarking data | Requires multi-system data to build the comparison set — the network is the moat. |

---

## Architecture Decisions to Lock Early

> These five decisions have the highest cost if deferred. Each becomes exponentially harder to change once agent logic is built on top of it.
> 

### 01 · Schema Retrieval Strategy

Vector store over the Clarity data dictionary is the only viable architecture at 30,000 tables. The embedding corpus must include table names, column names, descriptions, ZC_ join dependencies, and sample values. **Build this before writing a single agent.** Everything else depends on it.

### 02 · Domain Router Design

Fine-tune a small classifier on domain-labeled Clarity queries. Do not rely on a general LLM's prompt-following for routing. Routing errors produce plausible wrong answers with no visible error signal — the worst failure mode in an analytics agent.

### 03 · ZC_ Grounding Layer

Build a static ZC_ resolver that maps every categorical field to its human-readable lookup at query construction time. Bake it into the SQL generation layer as a mandatory post-processing step. Without it, every categorical output is a numeric code that users cannot interpret.

### 04 · Data Freshness Contract

Every agent output must carry a `data_as_of` timestamp. Build this into the output schema from day one — not as a UI afterthought. Clinical users who do not understand T-1 lag will use agent outputs in operational contexts where stale data causes patient harm.

### 05 · Multi-Tenant Schema Isolation

Design the vector store and SQL generation module to be tenant-aware from the start. Health systems customize their Clarity schemas. An agent built against one instance silently fails against another. This is your core technical moat if you scale across health systems — and your deepest risk if you ignore it.

---

Epic Clarity — Agentic AI Layer · Internal Brainstorm · Confidential