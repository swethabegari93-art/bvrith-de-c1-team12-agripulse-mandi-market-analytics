# Week 05 Log — Silver Layer Development

**Week:** 5  
**Date range:** 7-08-20206  
**Team:** Team-12 
**Project:** AgriPulse Market Mandi Analysis

---

## 1. Sprint Goal

The goal for Week 5 was to build and validate the Silver layer of the AgriPulse data pipeline.

The Bronze tables were cleaned, standardized, validated, and transformed into Silver candidate tables for arrivals, commodities, markets, and prices.
---

## 2. Work Completed

| Task                                            | Owner   | Status | Evidence                                    |
| ----------------------------------------------- | ------- | ------ | ------------------------------------------- |
| Read Bronze arrivals table                      | Student | Done   | Week 5 Databricks notebook                  |
| Clean and standardize arrivals data             | Student | Done   | Silver arrivals code / screenshot           |
| Create `silver_arrivals_candidate` table        | Student | Done   | Databricks table                            |
| Clean and standardize commodities data          | Student | Done   | Silver commodities code                     |
| Create `silver_commodities_candidate` table     | Student | Done   | Databricks table                            |
| Clean and standardize markets data              | Student | Done   | Silver markets code                         |
| Create `silver_markets_candidate` table         | Student | Done   | Databricks table                            |
| Clean and standardize prices data               | Student | Done   | Silver prices code                          |
| Create `silver_prices_candidate` table          | Student | Done   | Databricks table                            |
| Standardize string columns using trim/uppercase | Student | Done   | Silver transformation code                  |
| Convert date fields to proper date types        | Student | Done   | Silver transformation code                  |
| Handle invalid date values                      | Student | Done   | Databricks error resolution                 |
| Verify Silver table schemas and outputs         | Student | Done   | `display()` and `printSchema()` screenshots |

---

## 3. Key Decisions

-Standardized string fields using trim() and upper() and converted valid date fields into proper DATE types.
-Created separate Silver candidate tables for arrivals, commodities, markets, and prices while preserving important Bronze metadata.

---

## 4. Blockers / Risks

| Blocker                                                                           | Impact                                                     | Help Needed                                       |
| --------------------------------------------------------------------------------- | ---------------------------------------------------------- | ------------------------------------------------- |
| Invalid `report_date` value such as `31-31-2025` was present in the arrivals data | Silver table write initially failed during date conversion | Used safe date parsing and validation             |
| Different data types and formats existed in the raw Bronze data                   | Could cause transformation or table-write failures         | Standardized columns during Silver transformation |
| Some fields required cleaning before being used in Silver                         | Could lead to inconsistent values                          | Used `trim()` and `upper()` transformations       |


---

## 5. Evidence Added to GitHub

-Week 5 Silver-layer Databricks notebook/code.
-Screenshots of Silver transformations and outputs for Arrivals, Commodities, Markets, and Prices.
-Screenshots of Silver table schemas using printSchema().
-Screenshots showing successful validation of the Silver tables.
---

## 6. AI Transparency Note

| Question                            | Response                                                                                                                                                                                                 |
| ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Where AI helped                     | AI was used to help structure the Silver-layer transformation code, identify suitable Spark functions, and troubleshoot errors during date conversion and table creation.                                |
| What we changed after AI suggestion | The suggested transformations were adapted to match the actual Bronze table schemas and the columns available in the AgriPulse data.                                                                     |
| What we verified manually           | Table names, column names, data types, output records, date formats, and successful creation of the Silver candidate tables were verified manually in Databricks.                                        |
| What we can explain without AI      | We can explain the Bronze-to-Silver transformation process, data cleaning, string standardization, date conversion, metadata preservation, Delta table creation, and validation of the resulting tables. |


---

## 7. Next Week Preparation
-Validate the completed Silver tables more thoroughly using row counts, null checks, duplicate checks, and data-quality checks.
-Prepare the cleaned Silver data for the next stage of the AgriPulse pipeline, including the Gold layer / business-level transformations.
