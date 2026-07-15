# AWS Data & Analytics Services

# Overview

AWS provides a rich set of analytics services to process, store, query, visualize, and analyze large amounts of data. These services help organizations build data lakes, real-time analytics pipelines, business intelligence dashboards, and machine learning workflows.

This section covers:

- Amazon Athena
- Amazon Redshift
- Amazon EMR
- Amazon OpenSearch Service
- Amazon QuickSight
- AWS Glue
- Amazon Kinesis Data Analytics
- Amazon Managed Service for Apache Kafka (MSK)

---

# Analytics Pipeline

Applications

↓

Kinesis / MSK

↓

Glue

↓

S3 (Data Lake)

↓

Athena

↓

QuickSight

This is one of the most common AWS analytics architectures.

---

# Amazon Athena

Serverless interactive query service.

Features:

- SQL Queries
- Serverless
- Queries data directly from S3
- Pay per query

Best For:

- Log analysis
- Ad-hoc reporting
- Data lake exploration

---

# Amazon Redshift

Managed Data Warehouse.

Features:

- Columnar Storage
- Petabyte Scale
- High Performance Analytics

Best For:

- Business Intelligence
- Reporting
- Historical Analysis

---

# Amazon EMR

Managed Hadoop and Spark cluster.

Supports:

- Apache Spark
- Hadoop
- Hive
- HBase
- Presto

Best For:

- Big Data Processing
- ETL
- Machine Learning

---

# AWS Glue

Serverless ETL service.

Functions:

- Extract
- Transform
- Load

Features:

- Data Catalog
- Schema Discovery
- Job Scheduling

Used to prepare data before analytics.

---

# Amazon OpenSearch Service

Managed search and analytics engine.

Based on:

- Elasticsearch
- OpenSearch

Best For:

- Full-text Search
- Log Analytics
- Monitoring
- Dashboards

---

# Amazon QuickSight

Business Intelligence (BI) service.

Creates:

- Dashboards
- Reports
- Charts
- KPIs

Consumes data from:

- Athena
- Redshift
- RDS
- S3

---

# Amazon MSK

Managed Apache Kafka.

Use Cases:

- Event Streaming
- Microservices
- Log Collection
- Real-Time Processing

---

# Kinesis Data Analytics

Processes streaming data using SQL or Apache Flink.

Use Cases:

- Fraud Detection
- Real-time Dashboards
- IoT Analytics

---

# Comparison

| Requirement | AWS Service |
|-------------|-------------|
| SQL on S3 | Athena |
| Data Warehouse | Redshift |
| Big Data Processing | EMR |
| ETL | Glue |
| Search | OpenSearch |
| Dashboards | QuickSight |
| Kafka | MSK |
| Stream Analytics | Kinesis Data Analytics |

---

# Best Practices

- Store raw data in S3.
- Use Glue for ETL.
- Query S3 using Athena.
- Use Redshift for BI workloads.
- Index searchable data in OpenSearch.
- Visualize reports using QuickSight.
- Stream events using Kinesis or MSK.

---

# Hands-On Summary

- Explored Athena queries
- Learned Redshift architecture
- Compared EMR with serverless analytics
- Understood Glue ETL
- Learned OpenSearch indexing
- Built QuickSight dashboards
- Reviewed Kinesis Analytics
- Explored MSK