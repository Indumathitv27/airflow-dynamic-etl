# Dynamic Airflow ETL – YAML-Driven Data Pipeline

This project demonstrates a production-style, configurable ETL framework built with Apache Airflow. 
Pipelines are defined using YAML and dynamically generate DAGs to ingest, transform, validate, and monitor data.

## Architecture
- Apache Airflow (LocalExecutor)
- Docker Compose
- PostgreSQL (Raw + Staging + Metrics layers)
- Python, YAML

## Pipeline Flow
1. Initialize tables (idempotent)
2. Extract data from external API
3. Load raw JSON into warehouse
4. Transform into analytics-ready staging tables
5. Perform data quality checks
6. Log pipeline metrics for observability

## Key Features
- Dynamic DAG generation from YAML config
- Raw → Staging layered data model
- Data quality validation (row counts, null checks)
- Pipeline observability with metrics logging
- Fully containerized with Docker

## Results
- Loaded raw API payloads into `raw_weather`
- Transformed into 96 structured hourly records
- Logged pipeline metrics with DQ status = true

## How to Run
```bash
docker compose up -d
