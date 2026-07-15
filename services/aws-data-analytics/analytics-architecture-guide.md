# Analytics Architecture Guide

> Purpose: Learn how to design analytics systems on AWS and choose the right service for different workloads.

---

# Analytics Pipeline Overview

Applications

↓

Data Collection

↓

Storage

↓

Processing

↓

Analytics

↓

Visualization

Typical AWS Architecture

Applications

↓

Kinesis / MSK

↓

Glue

↓

S3 Data Lake

↓

Athena / Redshift

↓

QuickSight

---

# Data Lake vs Data Warehouse

## Data Lake

Stores raw structured and unstructured data.

Example Storage

- CSV
- JSON
- Images
- Logs
- Videos

AWS Service

Amazon S3

Benefits

- Cheap
- Unlimited storage
- Flexible schema

Best For

- Machine Learning
- Big Data
- Log Storage
- Raw Data

---

## Data Warehouse

Stores processed and structured business data.

AWS Service

Amazon Redshift

Benefits

- Fast analytics
- Historical reporting
- BI dashboards

Best For

- Sales Reports
- Financial Reports
- KPIs
- Business Analytics

---

# Data Lake vs Data Warehouse

| Data Lake | Data Warehouse |
|------------|----------------|
| Raw Data | Processed Data |
| S3 | Redshift |
| Cheap Storage | Fast Analytics |
| Flexible | Structured |

---

# Batch Processing

Data collected.

↓

Stored in S3.

↓

Glue Job

↓

Redshift

↓

QuickSight

Examples

- Daily Sales Reports
- Payroll
- Billing
- Invoice Generation

Characteristics

- Large volume
- Scheduled
- High throughput
- Not real time

---

# Stream Processing

Application Events

↓

Kinesis

↓

Lambda

↓

Dashboard

Examples

- Fraud Detection
- Stock Prices
- IoT
- User Activity

Characteristics

- Low latency
- Continuous processing
- Real-time dashboards

---

# Batch vs Streaming

| Batch | Streaming |
|--------|-----------|
| Scheduled | Continuous |
| High Throughput | Low Latency |
| Minutes/Hours | Milliseconds |
| Reports | Live Dashboards |

---

# Log Analytics Platform

Applications

↓

CloudWatch Logs

↓

S3

↓

Athena

↓

QuickSight

Alternative

Applications

↓

CloudWatch

↓

OpenSearch

↓

Dashboards

Used For

- Error Analysis
- API Performance
- Exception Tracking

---

# Clickstream Analytics

Website

↓

MSK

↓

Glue

↓

S3

↓

Athena

↓

QuickSight

Tracks

- Page Views
- User Sessions
- Clicks
- Purchases

---

# Fraud Detection

Payments

↓

Kinesis

↓

Lambda

↓

Fraud Engine

↓

Alert

↓

Dashboard

Real-time processing required.

---

# IoT Analytics

Sensors

↓

Kinesis

↓

Glue

↓

S3

↓

Athena

↓

QuickSight

Used For

- Temperature
- GPS
- Smart Cities
- Manufacturing

---

# Recommendation System

Application Events

↓

Kafka (MSK)

↓

S3

↓

Glue

↓

ML Training

↓

Recommendation API

---

# Product Search

Products

↓

OpenSearch

↓

Spring Boot

↓

Users

Why OpenSearch?

- Full-text search
- Auto-complete
- Filters
- Ranking

---

# Executive Dashboard

Applications

↓

Aurora

↓

Glue

↓

Redshift

↓

QuickSight

Displays

- Revenue
- Orders
- Active Users
- KPIs

---

# Machine Learning Pipeline

Raw Data

↓

S3

↓

Glue

↓

Feature Engineering

↓

SageMaker

↓

Model

↓

Prediction API

---

# Real-Time Monitoring

Applications

↓

CloudWatch

↓

Kinesis

↓

Lambda

↓

Dashboard

↓

Alerts

---

# ETL Pipeline

Source Database

↓

Glue

↓

Transform

↓

S3

↓

Redshift

↓

QuickSight

---

# Search Platform

Applications

↓

OpenSearch

↓

REST API

↓

Users

Used For

- Product Search
- Resume Search
- Log Search

---

# Choosing the Right Service

Need SQL on S3?

↓

Athena

Need BI Reports?

↓

Redshift

Need ETL?

↓

Glue

Need Search?

↓

OpenSearch

Need Dashboards?

↓

QuickSight

Need Kafka?

↓

MSK

Need Stream Processing?

↓

Kinesis

---

# Athena vs Redshift

| Athena | Redshift |
|----------|-----------|
| Serverless | Managed Cluster |
| Query S3 | Stores Data |
| Ad-hoc Queries | BI Analytics |
| Pay Per Query | Cluster Cost |

---

# Kafka vs Kinesis

| Kafka | Kinesis |
|---------|----------|
| Open Source | AWS Managed |
| Multi Cloud | AWS Only |
| Self Managed/MSK | Fully Managed |
| Flexible | AWS Integrated |

---

# OpenSearch vs Database Search

Database

LIKE '%phone%'

↓

Slow

OpenSearch

Index

↓

Milliseconds

↓

Ranking

↓

Autocomplete

---

# Common Design Patterns

### Data Lake

Applications

↓

S3

↓

Athena

---

### Data Warehouse

Applications

↓

Glue

↓

Redshift

↓

QuickSight

---

### Search

Applications

↓

OpenSearch

---

### Streaming

Applications

↓

Kinesis

↓

Lambda

---

### ETL

Database

↓

Glue

↓

Redshift

---

# Real Interview Questions

## How would you analyze application logs?

CloudWatch

↓

S3

↓

Athena

↓

QuickSight

---

## How would you build a product search?

Spring Boot

↓

OpenSearch

↓

Users

---

## How would you process one million events per second?

MSK / Kinesis

↓

Consumers

↓

S3

↓

Analytics

---

## How would you build business dashboards?

Aurora

↓

Glue

↓

Redshift

↓

QuickSight

---

## How would you process IoT events?

Devices

↓

Kinesis

↓

Lambda

↓

Timestream

↓

Dashboard

---

# Mapping to My Experience

| My Experience | AWS Equivalent |
|----------------|----------------|
| Kafka | Amazon MSK |
| IBM MQ | Amazon MQ |
| Azure SQL | Aurora |
| Cosmos DB | DynamoDB |
| OpenObserve | OpenSearch + CloudWatch |
| Grafana | QuickSight / CloudWatch Dashboard |
| Spring Boot | ECS |
| GitHub | GitHub Actions + ECR |

---

# Senior Backend Cheat Sheet

| Problem | AWS Service |
|----------|-------------|
| Search | OpenSearch |
| Reports | Redshift |
| SQL on Files | Athena |
| ETL | Glue |
| Dashboards | QuickSight |
| Kafka | MSK |
| Streams | Kinesis |
| Raw Data | S3 |
| Metrics | CloudWatch |
| IoT | Timestream |

---

# Golden Rules

1. Store raw data in S3.
2. Use Glue for ETL.
3. Query raw files with Athena.
4. Use Redshift for BI reporting.
5. Use OpenSearch for search, not SQL LIKE.
6. Use QuickSight for dashboards.
7. Use Kinesis for real-time analytics.
8. Use Kafka (MSK) when Kafka compatibility is required.
9. Separate OLTP databases from analytics databases.
10. Design analytics pipelines based on latency requirements.

---

# One-Line Revision

Store raw data in **S3**, transform it with **Glue**, analyze it using **Athena** or **Redshift**, visualize it with **QuickSight**, search using **OpenSearch**, and process streaming events using **Kinesis** or **MSK** depending on the use case.