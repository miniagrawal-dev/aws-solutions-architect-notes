# AWS Data & Analytics Interview Notes

# Analytics Workflow

Applications

↓

Streaming

↓

Storage

↓

Processing

↓

Visualization

---

# Athena

Purpose:

Run SQL directly on S3.

Advantages:

- Serverless
- No infrastructure
- Pay per query

Best for:

- Log analysis
- Reports
- Data lakes

---

# Redshift

Purpose:

Enterprise Data Warehouse.

Advantages:

- High-performance analytics
- Columnar storage
- Compression

Best for:

- BI
- Historical reports
- Data analytics

---

# Athena vs Redshift

| Athena | Redshift |
|----------|-----------|
| Serverless | Managed Cluster |
| Query S3 | Store Data |
| Ad-hoc Queries | Enterprise Analytics |
| Pay per Query | Pay for Cluster |

---

# EMR

Purpose:

Run Hadoop and Spark.

Best for:

- Large-scale ETL
- Machine Learning
- Big Data

---

# Glue

Purpose:

ETL Pipeline.

Functions:

- Discover schema
- Transform data
- Catalog datasets

---

# OpenSearch

Purpose:

Search Engine.

Examples:

- Product Search
- Log Search
- Error Analysis

---

# QuickSight

Purpose:

Business dashboards.

Used by:

- Product Managers
- Business Teams
- Executives

---

# MSK

Managed Kafka.

Use Cases:

- Event Streaming
- Microservices
- Clickstream

---

# Kinesis Analytics

Processes live streams.

Examples:

- Fraud Detection
- Live Metrics
- IoT

---

# Common Interview Questions

## Athena vs Redshift?

Athena queries data stored in S3 without managing infrastructure.

Redshift stores data in a warehouse optimized for complex analytical workloads.

---

## Why OpenSearch instead of a database?

Databases are optimized for transactions.

OpenSearch is optimized for fast full-text search.

---

## When should Glue be used?

When building ETL pipelines.

---

## Why QuickSight?

To create dashboards without building custom reporting applications.

---

## Senior Backend Focus

Know:

- Data Lake vs Data Warehouse
- Athena vs Redshift
- Kafka vs Kinesis
- OpenSearch vs SQL Search
- ETL concepts
- BI dashboards
- Streaming analytics

---

# One-Line Revision

Athena analyzes data in S3, Redshift powers data warehouses, Glue performs ETL, OpenSearch enables search, QuickSight builds dashboards, and Kinesis/MSK process streaming data.