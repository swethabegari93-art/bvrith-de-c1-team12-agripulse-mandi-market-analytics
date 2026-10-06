# Week 10 Log — Streaming Simulation

**Week:** 10  
**Date range:** 1-10-2026 to 6-10-2026  
**Team:** 12  
**Project:** AgriPulse Market Mandi Analysis

---

## 1. Sprint Goal

The goal of Week 10 was to simulate incoming agricultural market events using JSON files and Databricks Structured Streaming.

The team implemented Auto Loader, incremental file processing, checkpointing, a streaming Bronze table, and a live streaming metric.

---

## 2. Work Completed

| Task                                         | Owner   | Status | Evidence                                   |
| -------------------------------------------- | ------- | ------ | ------------------------------------------ |
| Created JSON market event files              | Team 12 | Done   | Streaming input JSON files                 |
| Created streaming landing folder             | Team 12 | Done   | `streaming/` path                          |
| Implemented Databricks Auto Loader           | Team 12 | Done   | `notebooks/07_streaming_simulation.ipynb`  |
| Implemented Structured Streaming             | Team 12 | Done   | `notebooks/07_streaming_simulation.ipynb`  |
| Added checkpoint for incremental processing  | Team 12 | Done   | Streaming checkpoint path                  |
| Created Bronze Streaming Delta table         | Team 12 | Done   | `bronze_agripulse_market_events_stream`    |
| Tested incremental file processing           | Team 12 | Done   | Streaming output screenshot                |
| Tested no-new-file behaviour                 | Team 12 | Done   | Notebook validation                        |
| Created live streaming metric                | Team 12 | Done   | `week10_live_metric.png`                   |
| Created Structured Streaming design document | Team 12 | Done   | `streaming/structured_streaming_design.md` |
| Created Kafka event schema                   | Team 12 | Done   | `streaming/kafka_event_schema.json`        |


---

## 3. Key Decisions

-Used JSON files to simulate incoming agricultural market events instead of implementing Kafka.
-Used Databricks Auto Loader with Structured Streaming for incremental file processing.
-Used a checkpoint to track processed files and prevent already processed files from being processed again.
-Used availableNow=True to run the streaming simulation in controlled batches.
-Stored the streaming output in the Bronze Streaming Delta table:
-workspace.default.bronze_agripulse_market_events_stream.
-Kafka was documented only as a production architecture awareness/design, as Kafka implementation is not mandatory for the internship.
---

## 4. Blockers / Risks

| Blocker                                                                             | Impact                                                | Help Needed                                                              |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------- | ------------------------------------------------------------------------ |
| Initial streaming paths pointed to non-existing Unity Catalog volumes               | Streaming folders could not be created                | Resolved by using subfolders inside the existing `agri_raw_files` volume |
| Streaming must demonstrate incremental processing rather than a simple batch reload | Required additional validation using multiple batches | Resolved by testing Batch 1, Batch 2, and Batch 3 processing             |
| Kafka implementation was not required for the sprint                                | Implementing Kafka could add unnecessary complexity   | Kafka kept as design-only                                                |

---

## 5. Evidence Added to GitHub
-notebooks/07_streaming_simulation.ipynb
-streaming/structured_streaming_design.md
-streaming/kafka_event_schema.json
-weekly_logs/week10_log.md
-screenshots/week10_streaming_input_files.png
-screenshots/week10_streaming_output.png
-screenshots/week10_live_metric.png
---

## 6. AI Transparency Note

| Question                            | Response                                                                                                                                                                         |
| ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Where AI helped                     | AI was used for guidance on Databricks Auto Loader, Structured Streaming, checkpoint concepts, streaming simulation, documentation structure, and troubleshooting.               |
| What we changed after AI suggestion | We adapted the streaming paths, event schema, Bronze table name, folder structure, and implementation to match the AgriPulse project and the existing Unity Catalog volume.      |
| What we verified manually           | The team manually verified the JSON input files, streaming output, event counts, checkpoint-based incremental processing, no-new-file behaviour, and live metric.                |
| What we can explain without AI      | The team can explain the JSON event flow, Auto Loader, Structured Streaming, checkpoints, Bronze streaming table, incremental processing, and the total streaming events metric. |


---

## 7. Next Week Preparation

-Review and refine the complete AgriPulse pipeline and documentation.
-Prepare the final project presentation and demonstration.
-Verify that all required notebooks, documentation, logs, and evidence screenshots are available in GitHub.
-Prepare to explain the project architecture, data quality, Gold KPIs, Power BI dashboard, and streaming simulation.
