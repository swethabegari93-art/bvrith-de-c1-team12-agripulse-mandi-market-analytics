# Data Dictionary

**Week:** 2  
**Purpose:** Define raw, reference, Silver, and streaming fields.

---

## 1. Source File Catalog

| File Name            | Grain                      | Purpose                   | Approx. Rows | Notes                 |
| -------------------- | -------------------------- | ------------------------- | ------------ | --------------------- |
| `commodities.csv`    | One row per commodity      | Stores commodity details  | 50           | Master commodity list |
| `markets.csv`        | One row per market         | Stores market information | 100          | Market master         |
| `arrivals.csv`       | One row per arrival record | Daily commodity arrivals  | 5000         | Transactional data    |
| `prices.csv`         | One row per price record   | Daily mandi prices        | 5000         | Transactional data    |
| `market_events.json` | One row per event          | Streaming simulation      | 1000         | JSON event data       |


---

## 2. Raw File Schema: `commodities.csv`

| Field Name     | Data Type | Required? | Example | Description         |
| -------------- | --------- | --------- | ------- | ------------------- |
| commodity_id   | Integer   | Yes       | 101     | Unique commodity ID |
| commodity_name | String    | Yes       | Rice    | Commodity name      |
| category       | String    | Yes       | Cereals | Commodity category  |

---

## 3. Raw File Schema: `market.csv`

| Field Name  | Data Type | Required? | Example           | Description      |
| ----------- | --------- | --------- | ----------------- | ---------------- |
| market_id   | Integer   | Yes       | 201               | Unique market ID |
| market_name | String    | Yes       | Bowenpally Market | Market name      |
| district    | String    | Yes       | Hyderabad         | District         |
| state       | String    | Yes       | Telangana         | State            |


---

## 4. Reference File Schema

| Field Name    | Data Type | Required? | Example | Description        |
| ------------- | --------- | --------- | ------- | ------------------ |
| category_id   | Integer   | Yes       | 1       | Category ID        |
| category_name | String    | Yes       | Cereals | Commodity category |

---

## 5. Canonical Silver Table Design

Final Silver table name:

```text
silver_market_prices
```

| Silver Field | Data Type | Source Mapping | Business Meaning      |
| ------------ | --------- | -------------- | --------------------- |
| record_id    | Integer   | price_id       | Unique price record   |
| commodity_id | Integer   | commodity_id   | Commodity identifier  |
| market_id    | Integer   | market_id      | Market identifier     |
| price_date   | Date      | price_date     | Date of observation   |
| modal_price  | Float     | modal_price    | Standard market price |
| quantity     | Float     | quantity       | Arrival quantity      |


---

## 6. Streaming Event Schema

| Field Name      | Data Type | Required? | Example                   | Description          |
| --------------- | --------- | --------- | ------------------------- | -------------------- |
| event_id        | String    | Yes       | EVT-0001                  | Unique event ID      |
| event_timestamp | Timestamp | Yes       | 2026-07-03T10:15:00+05:30 | Event timestamp      |
| event_type      | String    | Yes       | PRICE_UPDATE              | Type of event        |
| commodity_id    | Integer   | Yes       | 101                       | Commodity ID         |
| market_id       | Integer   | Yes       | 201                       | Market ID            |
| modal_price     | Float     | Yes       | 2650.50                   | Updated market price |
