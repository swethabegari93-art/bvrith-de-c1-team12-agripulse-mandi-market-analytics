# Week 06 Log — [Sprint Name]

**Week:** 6  
**Date range:**   31-08-2026 to 6-09-2026         

**Team:** Team 12  
**Project:** AgriPulse Market Mandi Analysis

---

## 1. Sprint Goal

Implement and validate the Silver Data Quality layer for AgriPulse.
Apply the required DQ rules, separate valid records into Trusted Silver tables and invalid records into Quarantine tables, and verify reconciliation and data quality results.

---

## 2. Work Completed

| Task                                                     | Owner       | Status | Evidence                  |
| -------------------------------------------------------- | ----------- | ------ | ------------------------- |
| Validated Silver Candidate tables                        | Hari Gopika | Done   | Week 6 DQ notebook        |
| Implemented DQ checks for Markets                        | Hari Gopika | Done   | `markets_checked`         |
| Implemented DQ checks for Commodities                    | Hari Gopika | Done   | `commodities_checked`     |
| Implemented DQ checks for Prices                         | Hari Gopika | Done   | `prices_checked`          |
| Implemented DQ checks for Arrivals                       | Hari Gopika | Done   | `arrivals_checked`        |
| Created Trusted Silver tables                            | Hari Gopika | Done   | `silver_*_trusted` tables |
| Created Quarantine tables                                | Hari Gopika | Done   | `quarantine_*` tables     |
| Generated DQ rule-failure summary                        | Hari Gopika | Done   | `dq_results_summary`      |
| Verified Candidate → Trusted + Quarantine reconciliation | Hari Gopika | Done   | Reconciliation queries    |
| Verified Trusted/Quarantine intersection                 | Hari Gopika | Done   | Intersection check        |
| Reviewed controlled replay/rework process                | Hari Gopika | Done   | Week 6 DQ notebook        |


---

## 3. Key Decisions

-Only records that pass the applicable DQ checks are promoted to Trusted Silver; failed records are routed to Quarantine.
-Gold-layer processing will use Trusted Silver data only, while quarantined records will not be used for downstream Gold analysis.

---

## 4. Blockers / Risks

| Blocker                                                                                                         | Impact                                                                                               | Help Needed                                                   |
| --------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| Approved reference/alias mappings and some configuration values were not available in the provided requirements | Full reference validation and some configuration-based checks require approved project configuration | Confirm approved reference mappings/configuration             |
| `silver_market_daily_candidate` was not available                                                               | DQ-REL validation could not be executed on a daily Candidate table                                   | Create/provide the approved daily Candidate table if required |


---

## 5. Evidence Added to GitHub

-Week 6 Data Quality notebook updated
-DQ results and reconciliation screenshots added
-Trusted and Quarantine table outputs captured
-DQ summary output captured
-Gold-layer preparation/code notebook updated

---

## 6. AI Transparency Note

| Question                                | Response                                                                                                                                                                        |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Where AI helped**                     | AI helped with writing and debugging PySpark/SQL DQ queries, structuring the notebook, and troubleshooting schema-related errors.                                               |
| **What we changed after AI suggestion** | We modified queries to match the actual column names and available Trusted/Candidate tables in Databricks.                                                                      |
| **What we verified manually**           | We manually executed the queries in Databricks and checked table schemas, DQ results, reconciliation counts, and quarantine records.                                            |
| **What we can explain without AI**      | We can explain the purpose of Candidate, Trusted and Quarantine layers, the DQ rules, reconciliation, and why invalid records must not be promoted directly to Trusted or Gold. |


---

## 7. Next Week Preparation

-Build and validate the Gold-layer tables using only Trusted Silver data.
-Verify Gold table schemas, joins, aggregations, and record counts before finalizing the notebook.
