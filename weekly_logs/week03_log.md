# Week 03 Log —  Databricks Setup & Data Exploration

**Week:** 3  
**Date range:** 24 July 2026 – 20 July 2026        
**Team:**Team 12  
**Project:** AgriPulse – Mandi Market Analytics


---

## 1. Sprint Goal

Set up the Databricks environment and load the AgriPulse datasets for exploration. Verify the schema, row counts, and basic data quality before starting data processing in the next sprint.


---

## 2. Work Completed

| Task | Owner | Status | Evidence |
|---|---|---|---|
| Created Databricks notebook for data exploration | Team 12 | Done | `notebooks/01_data_exploration.ipynb` |
| Loaded arrivals, commodities, markets, and prices datasets | Team 12 | Done | `week03_databricks_data_loaded.png` |
| Verified schema and row counts | Team 12 | Done | `week03_schema_and_row_count.png` |
| Created temporary SQL views for exploration | Team 12 | Done | `01_data_exploration.ipynb` |
| Performed basic data profiling | Team 12 | Done | `01_data_exploration.ipynb` |


---

## 3. Key Decisions

- Used Databricks with Apache Spark to process the AgriPulse datasets.
- Created temporary SQL views for each dataset to simplify SQL-based exploration.
---

## 4. Blockers / Risks

| Blocker | Impact | Help Needed |
|---|---|---|
| No major blockers encountered | None | Not required |

---

## 5. Evidence Added to GitHub

- Added `notebooks/01_data_exploration.ipynb`
- Added `screenshots/week03/week03_databricks_data_loaded.png`
- Added `screenshots/week03/week03_schema_and_row_count.png`
- Updated `weekly_logs/week03_log.md`
---

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | AI helped explain Databricks commands and Spark DataFrame operations. |
| What we changed after AI suggestion | Improved the notebook by organizing data loading, schema validation, and profiling steps. |
| What we verified manually | Verified dataset loading, schema, row counts, and notebook outputs in Databricks. |
| What we can explain without AI | We can explain the data loading process, Spark DataFrames, schema checking, row counts, and SQL views used in the notebook. |

---

---

## 7. Next Week Preparation

- Clean and validate the AgriPulse datasets.
- Begin the Bronze layer transformation and data quality checks for the pipeline.
