# Week 07 Log — [Sprint Name]

**Week:** 7  
**Date range:** 5-09-2026 to 11-09-2026    
**Team:** Team 12  
**Project:** AgriPulse Market Mandi Analysis

---

## 1. Sprint Goal

Build the Gold analytics layer using only approved Trusted Silver data.
Create and validate the required 8 KPI outputs for trusted observations, modal prices, arrivals, price spreads, market coverage, price changes, volatility, and trusted event freshness.

---

## 2. Work Completed

| Task                                                    | Owner          | Status                | Evidence                         |
| ------------------------------------------------------- | -------------- | --------------------- | -------------------------------- |
| Reviewed Week 6 Trusted Silver handoff                  | [Student Name] | Done                  | Week 6 DQ notebook               |
| Validated Trusted Silver grain and lookup relationships | [Student Name] | Done                  | Validation output / screenshot   |
| Created Trusted Observation Count Gold KPI              | [Student Name] | Done                  | `gold_trusted_observation_count` |
| Created Average Modal Price Gold KPI                    | [Student Name] | Done                  | `gold_average_modal_price`       |
| Created Total Arrival Tonnes Gold KPI                   | [Student Name] | Done                  | `gold_total_arrival_tonnes`      |
| Created Average Price Spread Gold KPI                   | [Student Name] | Done                  | `gold_average_price_spread`      |
| Created Market Coverage Rate Gold KPI                   | [Student Name] | Done                  | `gold_market_coverage_rate`      |
| Created Price Change % Gold KPI                         | [Student Name] | Done                  | `gold_price_change_pct`          |
| Created Volatility Index Gold KPI                       | [Student Name] | Done                  | `gold_volatility_index`          |
| Added Fresh Trusted Event Rate KPI contract             | [Student Name] | Done / Not Configured | `gold_fresh_trusted_event_rate`  |
| Performed Gold-layer validation checks                  | [Student Name] | Done                  | Week 7 validation screenshot     |


---

## 3. Key Decisions

**-Gold aggregations were created using Trusted Silver data only; Candidate and Quarantine data were not used.
-The approved full observation grain was maintained as market_id + commodity_id + variety_id + report_date.
-Price and arrival calculations were based on the approved unit and conversion information, including the arrival-to-tonne conversion factor.
-Price change percentage uses the previous trusted modal price with a null/zero guard to avoid invalid division.
-Volatility is calculated using standard deviation of modal price at the defined monthly market/commodity/variety grain.
-The Fresh Trusted Event Rate KPI was kept as NOT_CONFIGURED because an approved trusted event source and freshness threshold were noy  available for this Week 7 implementation.**
---

## 4. Blockers / Risks

| Blocker                                                                  | Impact                                                  | Help Needed                                           |
| ------------------------------------------------------------------------ | ------------------------------------------------------- | ----------------------------------------------------- |
| Fresh trusted event source/freshness threshold not configured            | KPI 8 cannot be calculated with verified project data   | Confirm approved event source and freshness threshold |
| Gold KPI results depend on the correctness of Week 6 Trusted Silver data | Incorrect Trusted data could affect Gold metrics        | Continue Silver DQ validation                         |
| Lookup completeness must be monitored during joins                       | Unmatched market/commodity keys may affect Gold results | Validate reference-key coverage                       |

---

## 5. Evidence Added to GitHub

-docs/gold_metrics_definition.md
-weekly_logs/week07_log.md
-screenshots/Week07_gold_tables.png
-screenshots/Week07_gold_validation.png
-screenshots/Week07_gold_all_kpi_output.png
-screenshots/Week07_Gold_KPI_Metrics_Output.png

---

| Question                                | Response                                                                                                                                                                                                                              |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Where AI helped**                     | AI was used to help structure the Week 7 Gold-layer PySpark implementation, KPI calculations, validation queries, and evidence checklist.                                                                                             |
| **What we changed after AI suggestion** | The generated logic was adapted to the actual AgriPulse table names, Trusted Silver datasets, project grain, and available fields. KPI 8 was kept as `NOT_CONFIGURED` rather than inventing an event source or freshness threshold.   |
| **What we verified manually**           | We manually checked the Trusted Silver table names, column names, full-grain logic, KPI output tables, row counts, calculated values, and validation results in Databricks.                                                           |
| **What we can explain without AI**      | We can explain why Gold reads from Trusted Silver, how each KPI is calculated, why the full grain is important, how arrival quantities are converted to tonnes, how price change is calculated, and how Gold validation is performed. |


---

## 7. Next Week Preparation

-Review and validate the completed Gold KPI tables.
-Prepare Gold-layer outputs for downstream analytics and reporting.
-Confirm any remaining event/freshness requirements for KPI 8.
-Prepare the required Week 7 evidence and documentation for review.
-Review Gold data quality and ensure reproducible reruns.
