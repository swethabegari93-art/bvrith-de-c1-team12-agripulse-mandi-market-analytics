# Structured Streaming Design

**Week:** 10  
**Purpose:** Explain the streaming simulation.

---

## 1. Streaming Scenario

New JSON agricultural market event files are placed in the streaming
landing folder.

Databricks Auto Loader detects newly arriving JSON files and reads them
incrementally using Structured Streaming. The events are processed and
written into a Bronze Streaming Delta table.

The streaming flow is:

**JSON Event Files → Auto Loader → Structured Streaming → Bronze Streaming Table → Live Metric**

The simulation uses multiple batches of JSON files to demonstrate
incremental event processing.


---

## 2. Event Source

| Item | Description |
|---|---|
| Event file format | JSON |
| Input path | `/Volumes/agripulse/default/agri_raw_files/streaming_landing/` |
| Processing method | Databricks Auto Loader / Structured Streaming |
| Output table | `workspace.default.bronze_agripulse_market_events_stream` |
| Checkpoint path | `/Volumes/agripulse/default/agri_raw_files/streaming_checkpoint/` |

Each streaming event contains:

| Field | Type | Description |
|---|---|---|
| `event_id` | String | Unique identifier for the event |
| `event_timestamp` | Timestamp | Time at which the event occurred |
| `event_type` | String | Type of market event |
| `commodity_id` | Integer | Identifier of the commodity |
| `market_id` | Integer | Identifier of the market |
| `modal_price` | Double | Modal market price |

Additional ingestion metadata is added during streaming:

- `_source_file_path`
- `_source_file_name`
- `_ingested_at`
---

## 3. Near-Real-Time Metric

The main live metric used in the streaming simulation is:

| Metric | Formula | Use |
|---|---|---|
| Total Streaming Events | Count of streaming event records | Shows the number of events processed by the streaming pipeline |

The metric is calculated from the Bronze Streaming table.

As new JSON files are processed, the total number of streaming events
increases.

---

## 4. Limitations

- This is a student streaming simulation, not a production event platform.
- JSON files are used to simulate incoming streaming events.
- The streaming events are synthetic and educational.
- Kafka is documented as production architecture awareness only.
- Kafka is not implemented in this Week 10 simulation.
- `availableNow=True` is used to process currently available files and
  demonstrate incremental streaming in a controlled manner.
