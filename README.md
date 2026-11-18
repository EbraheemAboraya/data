# Amazon E-Commerce Data Lakehouse 📊

> An end-to-end data engineering project combining batch processing, event streaming, orchestration and lakehouse storage.

**Stack:** Apache Spark · Apache Kafka · Apache Iceberg · Apache Airflow · MinIO · PostgreSQL · Docker · Python

## Overview
This project models e-commerce analytics across user events, catalog data, orders and other business datasets. It demonstrates the challenge of bringing together **batch** and **streaming** workloads into a shared data platform.

## Architecture
```text
 Batch data -----------------------+
                                   |
 Kafka event stream ---> Spark ----+---> Iceberg tables on MinIO
                                              |
                                           Analytics
                                   ^
                                   |
                             Airflow DAGs
```

## Key engineering capabilities
- **Streaming ingestion:** ingest events produced through Kafka.
- **Batch processing:** process business datasets using Spark.
- **Lakehouse modeling:** manage datasets through Apache Iceberg with object storage.
- **Orchestration:** schedule and coordinate workloads with Airflow.
- **Containerization:** run coordinated services using Docker Compose.
- **Data quality and lineage materials:** project includes validation and lineage-related artifacts.

## Quickstart
Prerequisite: Docker Desktop / Docker Compose v2 with adequate memory. See the full documentation in `docs/` for service configuration, port requirements and architecture details.

**Linux / macOS / WSL**
```bash
bash start.sh
```

**Windows PowerShell**
```powershell
.\start.ps1
```

The startup scripts provision the project stacks and trigger the Airflow pipelines described in the original project documentation.

## Explore
| Location | Contents |
| --- | --- |
| `processing/` | Spark, storage and batch processing |
| `streaming/` | Kafka and event production |
| `orchestration/` | Airflow workflows |
| `docs/` | Architecture and data-model details |
| `README_DATA_DICTIONARY.md` | Dataset dictionary |
| `EXPLAIN_THE_CODE.md` | Implementation walkthrough |

## Why it stands out
This isn't only an ETL script: it combines infrastructure, orchestration, event streams, analytical modeling and data quality into one reproducible engineering environment.

**Security:** local service usernames/passwords in development documentation are examples only; use different credentials for any externally accessible deployment.

---
*Designed to demonstrate data engineering from raw events to usable analytics.*
