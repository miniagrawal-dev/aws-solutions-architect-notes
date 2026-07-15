# AWS Databases Overview

# Overview

AWS provides multiple database services optimized for different workloads. Choosing the right database depends on data structure, scalability, latency, consistency, and access patterns.

This section covers:

- Amazon RDS
- Amazon Aurora
- Amazon DynamoDB
- Amazon ElastiCache
- Amazon DocumentDB
- Amazon Neptune
- Amazon Keyspaces
- Amazon QLDB
- Amazon Timestream

---

# Database Categories

## Relational Databases

Services:

- Amazon RDS
- Amazon Aurora

Best For:

- Banking
- ERP
- Order Management
- Inventory
- Payment Systems

Supports SQL and ACID transactions.

---

## Key-Value / NoSQL

Service:

Amazon DynamoDB

Best For:

- Shopping Cart
- User Profiles
- Session Storage
- Gaming
- IoT

Features:

- Serverless
- Auto Scaling
- Millisecond latency

---

## In-Memory Cache

Service:

Amazon ElastiCache

Engines:

- Redis
- Memcached

Purpose:

- Reduce database load
- Improve response time

---

## Document Database

Service:

Amazon DocumentDB

MongoDB compatible.

Best For:

- JSON documents
- Product Catalog
- CMS
- User Profiles

---

## Graph Database

Service:

Amazon Neptune

Stores relationships between entities.

Best For:

- Social Networks
- Recommendation Systems
- Fraud Detection
- Knowledge Graphs

---

## Wide Column Database

Service:

Amazon Keyspaces

Apache Cassandra compatible.

Best For:

- Massive write workloads
- IoT
- Event Storage

---

## Ledger Database

Service:

Amazon QLDB

Immutable transaction log.

Best For:

- Banking
- Financial Auditing
- Compliance
- Supply Chain

---

## Time Series Database

Service:

Amazon Timestream

Best For:

- IoT
- Monitoring
- Metrics
- Sensor Data
- DevOps

Optimized for timestamped data.

---

# Choosing the Right Database

| Requirement | AWS Service |
|-------------|-------------|
| SQL Database | Aurora / RDS |
| NoSQL | DynamoDB |
| Cache | ElastiCache |
| JSON Documents | DocumentDB |
| Graph Relationships | Neptune |
| Time-Series Data | Timestream |
| Ledger / Audit | QLDB |
| Cassandra Workloads | Keyspaces |

---

# Best Practices

- Use Aurora for mission-critical relational workloads.
- Use DynamoDB for serverless applications requiring predictable low latency.
- Cache frequently accessed data with Redis.
- Choose the database based on access patterns, not familiarity.
- Monitor performance and scaling using CloudWatch.
- Enable backups and encryption.

---

# Hands-On Summary

- Explored AWS database services
- Compared relational vs NoSQL databases
- Learned use cases for specialized databases
- Understood service selection criteria
- Reviewed scaling and availability options

---

# Production Architecture

Users

↓

Application Load Balancer

↓

Spring Boot

↓

Aurora

↓

Redis

↓

S3

↓

CloudWatch

Additional databases like DynamoDB, Neptune, or Timestream can be introduced based on specific application requirements.