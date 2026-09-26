# Week 08 Log — [Sprint Name]

**Week:** 8  
**Date range:** 11-09-2026 to 16-09-2026  
**Team:** Team 12  
**Project:** AgriPulse Market Mandi Analysis

---

## 1. Sprint Goal

Prepare the approved Gold-layer outputs for Power BI and build the first AgriPulse dashboard.

Create KPI cards, charts, slicers, and a dashboard layout using Gold outputs only, while validating that the Power BI visuals match the Gold data.

---

## 2. Work Completed

| Task                                    | Owner   | Status | Evidence                                                          |
| --------------------------------------- | ------- | ------ | ----------------------------------------------------------------- |
| Verified Week 7 Gold outputs            | Team 12 | Done   | `05_gold_aggregations.ipynb`                                      |
| Created Power BI export notebook        | Team 12 | Done   | `06_powerbi_export.ipynb`                                         |
| Loaded Gold KPI tables                  | Team 12 | Done   | `06_powerbi_export.ipynb`                                         |
| Validated Gold data and schemas         | Team 12 | Done   | `week08_gold_connection.png`, `week08_gold_schema_validation.png` |
| Connected Gold outputs to Power BI      | Team 12 | Done   | `week08_gold_connection.png`                                      |
| Created AgriPulse Overview dashboard    | Team 12 | Done   | `week08_powerbi_draft.png`                                        |
| Created KPI cards                       | Team 12 | Done   | Power BI dashboard                                                |
| Created Average Modal Price trend/chart | Team 12 | Done   | Power BI dashboard                                                |
| Created commodity-level charts          | Team 12 | Done   | Power BI dashboard                                                |
| Added Commodity and Year slicers        | Team 12 | Done   | Power BI dashboard                                                |
| Created Market Analysis page            | Team 12 | Done   | Power BI dashboard                                                |


---

## 3. Key Decisions

-Power BI uses Gold outputs only as the approved reporting layer.
-The dashboard was divided into an AgriPulse Overview page and a Market Analysis page.
-Commodity and Year slicers were added to allow interactive filtering.
-KPI cards and charts were created from the available Gold aggregation tables.

---

## 4. Blockers / Risks

| Blocker                                                            | Impact                               | Help Needed       |
| ------------------------------------------------------------------ | ------------------------------------ | ----------------- |
| No major blocker during dashboard creation                         | None                                 | None              |
| Power BI automatically applied some aggregations to numeric fields | Required checking of visual settings | Manual validation |


---

## 5. Evidence Added to GitHub

-notebooks/05_gold_aggregations.ipynb
-notebooks/06_powerbi_export.ipynb
-dashboard/powerbi_dashboard.pbix
-screenshots/week08_powerbi_draft.png
-screenshots/week08_gold_connection.png
-screenshots/week08_gold_kpi_outputs.png
-screenshots/week08_gold_schema_validation.png
-weekly_logs/week08_log.md

---

## 6. AI Transparency Note

| Question                                | Response                                                                                                                                                                                                  |
| --------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Where AI helped**                     | AI was used to provide guidance on the Week 8 Power BI workflow, dashboard structure, Gold-output usage, visual selection, slicers, and step-by-step Power BI instructions.                               |
| **What we changed after AI suggestion** | The suggested dashboard structure was adapted to the actual Gold tables and fields available in the project. Visual placement, chart titles, slicers, and page layout were adjusted manually in Power BI. |
| **What we verified manually**           | Gold tables, schemas, Power BI fields, KPI values, charts, slicers, and dashboard layout were checked manually.                                                                                           |
| **What we can explain without AI**      | We can explain the Gold-to-Power-BI flow, the purpose of each KPI, the fields used in the charts, how the Commodity and Year slicers work, and how the dashboard represents the Gold data.                |

---

## 7. Next Week Preparation

-Continue improving the Power BI dashboard with interactive features and clearer visual presentation.
-Add and verify data labels and other dashboard formatting.
-Validate that filtered dashboard values remain consistent with the Gold outputs.
-Document the completed dashboard work and prepare the required evidence.
