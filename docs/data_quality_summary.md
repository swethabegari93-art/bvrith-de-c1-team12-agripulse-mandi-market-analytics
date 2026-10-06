# Data Quality Summary

**Week:** 6  
**Purpose:**Summarize the data quality rules, failures, handling approach, and business impact.

---

## 1. Quality Rule Results



The Week 6 Data Quality process evaluated Silver Candidate records using checks covering identity and duplicate safety, reference integrity, date scope, price validity, arrival validity, and unit consistency.

The verified Candidate, Trusted, and Quarantine reconciliation results are:

| Dataset | Candidate Count | Trusted Count | Quarantine / Failed Count | Reconciliation |
|---|---:|---:|---:|---|
| Arrivals | 88,220 | 87,137 | 1,083 | PASS |
| Commodities | 164 | 156 | 8 | PASS |
| Markets | 606 | 594 | 12 | PASS |
| Prices | 96,125 | 94,908 | 1,217 | PASS |
| **Total** | **185,115** | **182,795** | **2,320** | **PASS** |

### Reconciliation

The Candidate records reconcile correctly:


Candidate = Trusted + Quarantine

185,115 = 182,795 + 2,320

---

## 2. Failed Record Examples

## 2. Failed Record Examples

| Rule ID | Sample Record ID | Failure Reason | Action / Handling |
|---|---|---|---|
| DQ-OBS-001 | `[from Week 6 DQ output]` | Duplicate or missing physical/business key | Routed to Quarantine |
| DQ-REF-001 | `[from Week 6 DQ output]` | Required market/commodity/variety reference missing or invalid | Routed to Quarantine |
| DQ-DAT-001 | `[from Week 6 DQ output]` | Report date outside approved date scope | Routed to Quarantine |
| DQ-PRC-001 | `[from Week 6 DQ output]` | Invalid price value or price ordering | Routed to Quarantine |
| DQ-ARR-001 | `[from Week 6 DQ output]` | Missing or negative arrival quantity | Routed to Quarantine |
| DQ-UNT-001 | `[from Week 6 DQ output]` | Missing or invalid unit | Routed to Quarantine |
---

## 3. What Should Block Gold Metrics?

The following should block or flag Gold metrics:

-DQ-OBS-001 — duplicates or missing identifiers can cause incorrect counts and double-counting.
-DQ-REF-001 — invalid reference keys can produce incorrect or incomplete joins.
-DQ-DAT-001 — invalid dates can place data outside the intended reporting period.
-DQ-PRC-001 — invalid prices can make price analytics unreliable.
-DQ-ARR-001 — invalid arrival quantities can affect supply metrics.
-DQ-UNT-001 — inconsistent units can make comparisons and conversions unreliable.

Gold tables should therefore be built from Trusted Silver records only, not from Quarantine records.
---

## 4. Quality Summary

The Week 6 Data Quality process evaluated the Silver Candidate records using the approved DQ rule families.
The checks covered identity and duplicates, reference integrity, date scope, price validity, arrival validity and unit consistency.
Records that passed the applicable checks were routed to the Trusted Silver tables, while failed records were retained in Quarantine with their failure reasons.
Duplicate records are important because they can lead to double-counting in business metrics.
Invalid references can affect joins between markets, commodities, varieties and transactional data.
Invalid prices, arrival quantities and units can directly affect business dashboards and analytical metrics.
The mentor should carefully review the actual failed-record counts, sample quarantine records, configured thresholds and reference mappings before accepting the final Gold metrics. The notebook explicitly requires these items to be independently verified.

Prompts:

-Which rule failed the most?
The rule with the highest number of failed records should be reported here after checking the DQ results summary. We should not assume the highest failure without the actual counts.
-Which failures matter most for dashboards?
Price validity (DQ-PRC-001), arrival validity (DQ-ARR-001), duplicate/grain issues (DQ-OBS-001), and invalid references (DQ-REF-001) are particularly important because they can distort prices, supply metrics, record counts, and joins.
-Did the team fix, flag, or exclude bad records?
Bad records were flagged and routed to Quarantine, while records passing the applicable checks were routed to Trusted Silver.
-What should the mentor review carefully?
The mentor should review the actual DQ failure counts, sample quarantined records and failure reasons, approved configuration values such as bounds/unit lists, and the reconciliation between Candidate, Trusted, and Quarantine records. The notebook specifically says these results must be independently verified.
-What should the mentor review carefully?
The mentor should carefully review the actual DQ failed counts, sample quarantined records, failure reasons, configured validation thresholds and reference mappings.
The mentor should also verify that Candidate records reconcile correctly into Trusted and Quarantine records, that Quarantine records are excluded from Gold metrics, and that Gold tables are built only from validated Trusted Silver records.
