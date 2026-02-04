# Real-Time + Batch Customer Behavior Intelligence Platform

## Goal
Kafka - (real-time) + Spark (batch) - + NoSQL, orchestrated by Airflow, modeled by dbt, analyzed with pandas/Python/R.
# Real-Time + Batch Customer Behavior Intelligence Platform

## One-line pitch (for README / interviews)

A production-style data platform that ingests real-time events via Kafka, processes them with Flink (real-time) and Spark/Databricks (batch), stores curated analytics in a cloud warehouse (Snowflake/BigQuery/Redshift), keeps raw and high-velocity data in NoSQL (MongoDB/Cassandra), models metrics with dbt, orchestrates with Airflow, and runs data science & ML analysis using pandas and R.

---

## The Use Case (Simple but realistic)

Track user activity events from a web or mobile application, such as:

- `page_view`
- `search`
- `add_to_cart`
- `purchase`
- `session_start`
- `session_end`

### Business questions answered

- **“What’s happening right now?”**  
  Real-time dashboards and rolling metrics

- **“What happened yesterday?”**  
  Batch reporting and historical analysis

- **“Who is likely to purchase?”**  
  ML-based user scoring and behavioral analysis

---

## Tool Mapping (Aligned exactly to project stack)

### Pipeline

- **Kafka**  
  Event ingestion layer (stream of user actions)

- **Airflow**  
  Orchestration of batch jobs, dbt runs, and data quality checks

- **dbt**  
  Warehouse transformations, metrics modeling, and tests

---

### Compute

- **Flink**  
  Real-time stream processing  
  - Rolling active users (5-minute windows)  
  - Conversion rates by traffic source  
  - Anomaly detection on purchase spikes  

- **Spark**  
  Batch processing  
  - Daily aggregates  
  - Sessionization  
  - Feature generation for ML  

- **Databricks** (optional, portfolio enhancement)  
  Managed Spark environment, notebooks, and scheduled jobs

---

### Storage (Data Warehouse)

Choose **one primary warehouse** for the project:

- Snowflake **or**
- BigQuery **or**
- Redshift  

> The platform is portable across warehouses using **dbt**, demonstrating vendor-agnostic design.

---

### NoSQL Stores

Each NoSQL database serves a **distinct role**:

- **MongoDB**  
  - Raw JSON event storage  
  - Session documents  
  - Flexible schema for evolving event formats  

- **Cassandra**  
  - High-speed time-series metrics  
  - Optimized for fast writes  
  - Partitioned by day and user  

---

### Analysis & Data Science

- **Python (pandas)**  
  - Exploratory data analysis (EDA)  
  - Feature validation  
  - Model training  

- **R**  
  - Statistical testing  
  - Forecasting  
  - Model comparison reports  

---

## Architecture (High-level Flow)

### Event Producer

A small event generator (or simulated app logs) produces user activity events and publishes them to a Kafka topic:


