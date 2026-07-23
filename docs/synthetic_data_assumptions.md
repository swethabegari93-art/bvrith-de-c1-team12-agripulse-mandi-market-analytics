# Synthetic Data Assumptions

**Week:** 2  
**Purpose:** Document how educational data is created.


---

## 1. Synthetic Data Boundary

This project uses synthetic educational data only. It must not be presented as real company, customer, citizen, player, patient, government, or platform data.

---

## 2. Domain Assumptions

| Area | Assumption |
|------|------------|
| Geography / scope | Agricultural markets (mandis) across Telangana and nearby regions |
| Time period | July 2026 to September 2026 |
| Source systems | Commodity, Market, Arrivals, and Prices datasets |
| Event types | Commodity arrival, Price update, Market transaction |
| Reference data | Commodities, Markets, Districts, States |

---

## 3. Data Volume Assumptions

| File | Approximate Rows | Reason |
|------|------------------:|--------|
| `commodities.csv` | 50 | Contains the master list of agricultural commodities |
| `markets.csv` | 100 | Contains market (mandi) information across regions |
| `arrivals.csv` | 5,000 | Simulates daily commodity arrivals for analysis |
| `prices.csv` | 5,000 | Simulates daily commodity price records |
| `market_events.json` | 1,000 | Simulates streaming market and price update events |
---

## 4. Controlled Data Quality Issues

| Issue Type | Approx. Share | Why Include It |
|---|---:|---|
| Duplicate IDs | 0.2%–0.5% | Tests uniqueness |
| Missing values | 1%–3% | Tests completeness |
| Invalid reference keys | 0.5%–1% | Tests referential integrity |
| Negative / impossible values | 0.1%–0.5% | Tests range rules |
| Timestamp inconsistencies | 0.1%–0.3% | Tests chronology |

---

## 5. Manual Verification

Before using generated data, the team must check:

- Row counts are reasonable.
- Key fields exist.
- Dates and numeric values look realistic.
- Controlled defects exist but do not dominate the dataset.
- Source files are different enough to require real standardization.
