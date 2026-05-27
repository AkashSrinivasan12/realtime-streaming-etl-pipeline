# Real-Time Streaming ETL Pipeline

> **🔄 Repository Status: Code upload in progress — full implementation being added. Star this repo to get notified when complete.**

---

A scalable real-time data pipeline using Apache Kafka and PySpark Structured Streaming for ingesting, processing, and routing high-volume operational event streams to cloud data lakes — enabling live analytics and automated alerting.

---

## What This Project Does

Processes continuous streams of operational events (bookings, updates, errors) with low latency — transforming raw event data into structured analytics-ready datasets while simultaneously triggering alerts on anomalies or threshold breaches.

---

## Architecture

```
Event Sources
(Applications / REST APIs / Databases)
        │
        ▼
[Apache Kafka — Event Bus]
  Topic: raw-events       (all incoming)
  Topic: processed-events (cleaned)
  Topic: alerts           (threshold breaches)
        │
        ▼
[PySpark Structured Streaming]
  ├── Schema validation & type casting
  ├── Deduplication (watermarking)
  ├── Windowed aggregations (5-min, 1-hr)
  └── Anomaly detection rules
        │
        ├──► [AWS S3 / Azure Data Lake]
        │     Raw layer + processed layer
        │     Partitioned by date/source
        │
        └──► [Alert Engine]
              Downstream notifications
              Dashboard refresh triggers
```

---

## Tech Stack

| Component | Tool |
|---|---|
| Event Streaming | Apache Kafka |
| Stream Processing | PySpark Structured Streaming |
| Cloud Storage | AWS S3 / Azure Data Lake |
| Alternative Ingestion | AWS Kinesis |
| Distributed Processing | Databricks |
| Containerization | Docker |
| Language | Python |

---

## Project Structure *(uploading)*

```
realtime-streaming-etl-pipeline/
├── producer/
│   └── event_producer.py    ← Kafka producer (simulated events)
├── consumer/
│   └── stream_processor.py  ← PySpark streaming job
├── alerts/
│   └── alert_engine.py      ← Threshold-based alert rules
├── config/
│   └── kafka_config.py      ← Topic and broker configuration
├── docker-compose.yml        ← Kafka + Zookeeper local setup
├── Dockerfile
└── requirements.txt
```

---

## Author

**Akash Srinivasan** — [LinkedIn](https://linkedin.com/in/akashsrinivasan12) | [GitHub](https://github.com/akashsrinivasan12)
