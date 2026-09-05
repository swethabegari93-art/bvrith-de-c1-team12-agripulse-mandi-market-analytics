# Gold Metrics Definition

**Week:** 7  
**Purpose:** Define dashboard-ready Gold tables and KPI formulas.

---

## 1. Gold Table Catalog

| Gold Table Name | Grain | Source Table(s) | Purpose |
|---|---|---|---|
| `gold_trusted_observation_count` | Market + Report Date | `silver_prices_trusted`, `silver_markets_trusted` | Count trusted price observations by market and date |
| `gold_average_modal_price` | Commodity + Variety + Year + Month | `silver_prices_trusted`, `silver_commodities_trusted` | Calculate average trusted modal price |
| `gold_total_arrival_tonnes` | Commodity + Variety + Year + Month | `silver_arrivals_trusted`, `silver_commodities_trusted` | Calculate total arrivals converted to tonnes |
| `gold_average_price_spread` | Market + Commodity + Variety + Year + Month | `silver_prices_trusted`, `silver_markets_trusted`, `silver_commodities_trusted` | Calculate average difference between maximum and minimum price |
| `gold_market_coverage_rate` | Report Date | `silver_prices_trusted`, `silver_markets_trusted` | Measure trusted market coverage |
| `gold_price_change_pct` | Market + Commodity + Variety + Report Date | `silver_prices_trusted`, `silver_markets_trusted`, `silver_commodities_trusted` | Calculate percentage change in modal price |
| `gold_volatility_index` | Market + Commodity + Variety + Year + Month | `silver_prices_trusted`, `silver_markets_trusted`, `silver_commodities_trusted` | Measure modal-price volatility |
| `gold_fresh_trusted_event_rate` | Report Date | Approved Trusted Event Source | Measure fresh trusted events within the approved threshold |

## 2. KPI Definitions

| KPI Name | Formula | Grain | Dashboard Page | Notes |
|---|---|---|---|---|
| **Trusted Observation Count** | `COUNT(DISTINCT price_record_id)` | Market + Date | Market Analytics | Counts trusted price observations |
| **Average Modal Price** | `SUM(modal_price) / COUNT(modal_price)` | Commodity + Variety + Month | Commodity Analytics | Uses trusted priced observations |
| **Total Arrival Tonnes** | `SUM(arrival_quantity × arrival_to_tonne_factor)` | Commodity + Variety + Month | Arrival Analytics | Converts arrival quantity into tonnes |
| **Average Price Spread** | `AVG(maximum_price - minimum_price)` | Market + Commodity + Variety + Month | Price Analytics | Measures average price range |
| **Market Coverage Rate** | `Markets with trusted observations / Active eligible markets` | Date | Market Coverage | Measures daily market coverage |
| **Price Change %** | `(Current Modal Price - Previous Modal Price) / Previous Modal Price` | Market + Commodity + Variety + Date | Price Trend | Null and zero previous prices are guarded |
| **Volatility Index** | `STDDEV_SAMP(modal_price)` | Market + Commodity + Variety + Month | Volatility Analytics | Measures modal-price variation |
| **Fresh Trusted Event Rate** | `Fresh trusted events / Processed valid events` | Date | Event Monitoring | Requires approved event source and freshness threshold |
---

## 3. Validation Checks
Before using Gold tables for downstream analytics, verify:

- Gold tables are created successfully.
- Gold row counts are reasonable.
- Gold uses **Trusted Silver data only**.
- The approved observation grain is maintained:
  `market_id + commodity_id + variety_id + report_date`.
- No unexpected nulls exist in key dashboard fields.
- No duplicate groups exist at the defined Gold grain.
- Market coverage rates remain between `0` and `1`.
- Volatility values are non-negative.
- Price change calculations correctly handle null and zero previous prices.
- Arrival quantities use the approved `arrival_to_tonne_factor`.
- KPI totals are checked against manual spot calculations.
- Rerunning the Gold transformations produces consistent results.
- Power BI connects to Gold outputs only.
