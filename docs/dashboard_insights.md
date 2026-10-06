# Dashboard Insights

**Week:** 9  
**Purpose:** Explain what the Power BI dashboard shows.

---

## 1. Dashboard Pages

| Page | Purpose | Main Visuals |
|---|---|---|
| Page 1: AgriPulse Agricultural Market Overview | Provides a high-level view of agricultural market performance | KPI cards, Average Modal Price Trend, Average Modal Price by Commodity, Total Arrival Tonnes by Commodity |
| Page 2: AgriPulse Market Analysis | Provides deeper analysis using commodity and time-based filters | Commodity slicer, Year/Month slicers, Average Modal Price by Commodity, Total Arrival Tonnes by Commodity, Price Change by Commodity, Market Coverage Rate by Month |

---

## 2. Key Insights

1. The dashboard provides a high-level overview of agricultural market performance using Average Modal Price, Total Arrival Tonnes, Market Coverage Rate, and Price Change.

2. The Average Modal Price Trend visual helps users understand how agricultural prices change over time.

3. Average Modal Price by Commodity allows comparison of price levels across different commodities.

4. Total Arrival Tonnes by Commodity helps identify differences in the quantity of agricultural arrivals between commodities.

5. The Price Change (%) visual helps users compare price movement across commodities.

6. Market Coverage Rate can be analyzed across months to understand market coverage over time.

7. The Commodity slicer allows users to focus the dashboard on a specific commodity.

8. Year and Month filters allow users to analyze the dashboard for a selected time period.

> Note: The dashboard insights are based on the visuals and metrics implemented in Power BI. Specific numerical trends should be added only when supported by the dashboard data.


---

## 3. How the Dashboard Uses Gold Tables

| Dashboard Page | Gold Table Used | Important Fields |
|---|---|---|
| Page 1: Agricultural Market Overview | `gold_average_modal_price` | `report_date`, `commodity_id`, `average_modal_price` |
| Page 1: Agricultural Market Overview | `gold_total_arrival_tonnes` | `report_date`, `commodity_id`, `total_arrival_tonnes` |
| Page 1: Agricultural Market Overview | `gold_market_coverage_rate` | `report_date`, `market_coverage_rate` |
| Page 1: Agricultural Market Overview | `gold_price_change_pct` | `report_date`, `commodity_id`, `price_change_pct` |
| Page 2: Market Analysis | `gold_average_modal_price` | `report_date`, `commodity_id`, `average_modal_price` |
| Page 2: Market Analysis | `gold_total_arrival_tonnes` | `report_date`, `commodity_id`, `total_arrival_tonnes` |
| Page 2: Market Analysis | `gold_price_change_pct` | `report_date`, `commodity_id`, `price_change_pct` |
| Page 2: Market Analysis | `gold_market_coverage_rate` | `report_date`, `market_coverage_rate` |

---

## 4. Power BI Validation

- [x] Dashboard connects to Gold outputs.
- [x] Commodity filter works correctly.
- [x] Year and Month filters work correctly.
- [x] Average Modal Price uses Average aggregation.
- [x] Total Arrival Tonnes uses Sum aggregation.
- [x] Market Coverage Rate uses Average aggregation.
- [x] Price Change (%) is displayed as a percentage.
- [x] KPI totals and visual aggregations were checked against Gold outputs.
- [ ] Dashboard screenshots are saved in `screenshots/`.
- [x] Dashboard story is explainable by all students.
