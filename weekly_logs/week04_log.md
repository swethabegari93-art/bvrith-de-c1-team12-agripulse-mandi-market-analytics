# Week 04 Log — [Bronze Data Ingestion]

**Week:** 4  
**Date range:** [31-07-2026]  
**Team:** [Team 12]  
**Project:** [AgriPulse Market Mandi Analysis]

---

## 1. Sprint Goal

The goal of this sprint was to ingest the raw AgriPulse datasets into the Bronze layer using Databricks. The data was loaded from the Unity Catalog Volume, metadata columns were added, and Delta tables were created for further processing.
---

## 2. Work Completed

| Task                                                               | Owner       | Status | Evidence                     |
| ------------------------------------------------------------------ | ----------- | ------ | ---------------------------- |
| Created AgriPulse Volume and verified raw files                    | Hari Gopika | Done   | Databricks Volume screenshot |
| Loaded arrivals.csv into Spark DataFrame                           | Hari Gopika | Done   | Notebook                     |
| Created Bronze Arrivals Delta table                                | Hari Gopika | Done   | `bronze_arrivals` table      |
| Loaded commodities.csv and created Bronze table                    | Hari Gopika | Done   | `bronze_commodities` table   |
| Loaded markets.csv and created Bronze table                        | Hari Gopika | Done   | `bronze_markets` table       |
| Loaded prices.csv and created Bronze table                         | Hari Gopika | Done   | `bronze_prices` table        |
| Added metadata columns (`source_file`, `ingestion_time`, `run_id`) | Hari Gopika | Done   | Notebook                     |
| Validated record counts between source and Bronze tables           | Hari Gopika | Done   | Output screenshots           |


---

## 3. Key Decisions

-Used Delta format for storing Bronze tables.
-Added metadata columns (source_file, ingestion_time, and run_id) to support data lineage and pipeline tracking.
---

## 4. Blockers / Risks

| Blocker                                                            | Impact                                   | Help Needed                                                                    |
| ------------------------------------------------------------------ | ---------------------------------------- | ------------------------------------------------------------------------------ |
| Incorrect file path and `saveAsTable()` usage during initial setup | Bronze tables were not created correctly | Resolved by using the correct Databricks Volume path and table creation method |


---

## 5. Evidence Added to GitHub

-Updated Week 4 Bronze Ingestion notebook.
-Added screenshots of Bronze table creation and validation.
-Added screenshots of Delta data stored in the AgriPulse Volume.

---

## 6. AI Transparency Note

| Question                                | Response                                                                                                                                                 |
| --------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Where AI helped**                     | AI helped in fixing Databricks path errors, implementing Bronze ingestion, adding metadata columns, and creating Delta tables.                           |
| **What we changed after AI suggestion** | Updated the file paths, corrected table creation commands, added `source_file`, `ingestion_time`, and `run_id`, and validated row counts.                |
| **What we verified manually**           | Verified that all four Bronze tables were created successfully, checked schemas, and confirmed source and Bronze row counts matched.                     |
| **What we can explain without AI**      | The Bronze ingestion workflow, reading CSV files into Spark DataFrames, adding metadata columns, writing Delta tables, and validating the ingested data. |


## 7. Next Week Preparation

-Start developing the Silver layer by cleaning and transforming Bronze data.
-Apply data quality checks, standardization, and validation before loading the Silver tables.
