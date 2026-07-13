# Database Selection Guide

> Purpose: Learn **which database to choose and why**. Focus on trade-offs, production use cases, and interview scenarios.

---

# Step 1: Ask These Questions

Before choosing any database, ask:

- Is the data relational?
- Do I need joins?
- Do I need ACID transactions?
- How much data?
- Read-heavy or write-heavy?
- Expected latency?
- Does schema change frequently?
- Need horizontal scaling?
- Need graph relationships?
- Need caching?

---

# SQL vs NoSQL

| SQL | NoSQL |
|------|--------|
| Structured Schema | Flexible Schema |
| ACID Transactions | BASE/Eventual Consistency |
| Joins | No Joins |
| Vertical Scaling | Horizontal Scaling |
| Banking | Social Media |

Choose SQL when:

- Orders
- Payments
- Banking
- Inventory

Choose NoSQL when:

- Shopping Cart
- User Sessions
- IoT
- Gaming
- Large Scale

---

# RDS vs Aurora

| RDS | Aurora |
|------|---------|
| Managed DB | Cloud Native |
| Standard Performance | Up to 5x MySQL / 3x PostgreSQL (AWS benchmark) |
| Lower Cost | Higher Performance |
| Standard Storage | Distributed Storage |

Choose Aurora when:

- High traffic
- Production applications
- High Availability
- Read-heavy systems

Choose RDS when:

- Small applications
- Cost-sensitive workloads
- Simpler deployments

---

# Aurora vs DynamoDB

| Aurora | DynamoDB |
|----------|-----------|
| SQL | NoSQL |
| ACID | Key-Value |
| Joins | No Joins |
| Complex Queries | Simple Queries |
| Transactions | Massive Scale |

Aurora

Examples:

- Banking
- Order Management
- ERP

DynamoDB

Examples:

- Shopping Cart
- Gaming
- User Sessions
- IoT

---

# DynamoDB vs DocumentDB

| DynamoDB | DocumentDB |
|------------|------------|
| Key-Value | JSON Documents |
| Extremely Fast | Flexible Documents |
| Shopping Cart | Product Catalog |
| User Sessions | CMS |

Choose DocumentDB if your application already uses MongoDB.

---

# Redis vs Memcached

| Redis | Memcached |
|--------|------------|
| Persistence | No |
| Replication | No |
| Pub/Sub | No |
| Transactions | No |
| Rich Data Types | Key-Value Only |

Redis is preferred for most production applications.

---

# Redis vs DynamoDB

Redis

- Cache
- Temporary Data
- Millisecond Access
- Data can be rebuilt

DynamoDB

- Primary Database
- Persistent Storage

---

# Neptune vs Aurora

Aurora

Stores:

Orders

Customers

Invoices

Neptune

Stores:

Friends

Followers

Recommendations

Dependencies

---

# QLDB vs Aurora

Aurora

Data can change.

QLDB

Changes are permanently recorded.

Used for:

- Banking
- Auditing
- Compliance

---

# Timestream vs Aurora

Aurora

General SQL Database

Timestream

Time-Series Database

Examples:

- CPU Usage
- Server Metrics
- IoT Sensors
- Temperature

---

# Keyspaces vs DynamoDB

Keyspaces

Apache Cassandra

Massive Writes

Distributed

DynamoDB

Serverless

AWS Native

---

# Polyglot Persistence

Modern applications use multiple databases.

Example

Spring Boot

↓

Aurora

Transactions

↓

Redis

Cache

↓

S3

Images

↓

OpenSearch

Search

↓

Neptune

Recommendations

Never try to use one database for everything.

---

# CAP Theorem

Choose any two:

Consistency

Availability

Partition Tolerance

Distributed databases make trade-offs.

Example:

Aurora

High Consistency

DynamoDB

Highly Available

Partition Tolerant

---

# ACID vs BASE

## ACID

Atomicity

Consistency

Isolation

Durability

Examples

Aurora

RDS

---

## BASE

Basically Available

Soft State

Eventually Consistent

Examples

DynamoDB

Cassandra

---

# Which Database Should I Choose?

Need SQL?

↓

Aurora

Need Key-Value?

↓

DynamoDB

Need JSON?

↓

DocumentDB

Need Graph?

↓

Neptune

Need Cache?

↓

Redis

Need Time-Series?

↓

Timestream

Need Ledger?

↓

QLDB

Need Massive Cassandra Workload?

↓

Keyspaces

---

# Real System Design Examples

## Banking

Aurora

↓

Redis

↓

S3

---

## Shopping Cart

DynamoDB

↓

Redis

---

## Instagram

Aurora

↓

Redis

↓

S3

---

## Netflix

Aurora

↓

Redis

↓

S3

↓

CloudFront

---

## Amazon

Aurora

↓

Redis

↓

OpenSearch

↓

S3

---

## IoT

Kinesis

↓

Lambda

↓

Timestream

---

## Facebook

Neptune

↓

Redis

↓

Aurora

---

## Audit System

QLDB

↓

S3

---

# Top Interview Questions

### Why not use DynamoDB everywhere?

Because relational data, joins, and complex transactions are better handled by relational databases.

---

### Why not use Aurora everywhere?

Aurora is excellent for relational workloads, but applications like shopping carts or gaming often require the horizontal scalability and predictable low latency of DynamoDB.

---

### Why use Redis?

To reduce database load.

Improve response time.

Store sessions.

Cache expensive queries.

---

### Why use multiple databases?

Each database solves different problems.

Example

Orders

↓

Aurora

Sessions

↓

Redis

Images

↓

S3

Recommendations

↓

Neptune

---

### What is Polyglot Persistence?

Using different databases in the same application based on workload requirements.

---

# Senior Backend Cheat Sheet

| Requirement | Database |
|-------------|----------|
| Banking | Aurora |
| Orders | Aurora |
| Shopping Cart | DynamoDB |
| Cache | Redis |
| Product Catalog | DocumentDB |
| Recommendations | Neptune |
| Audit | QLDB |
| Metrics | Timestream |
| Large Writes | Keyspaces |
| Images | S3 |

---

# Golden Rules

1. Don't use one database for everything.
2. Cache frequently accessed data.
3. Choose the database based on access patterns.
4. Separate transactional and analytical workloads.
5. Use SQL for relationships.
6. Use NoSQL for scale.
7. Keep large files in S3, not the database.
8. Design for backups and disaster recovery.
9. Monitor database performance.
10. Understand the trade-offs before selecting a database.

---

# One-Line Revision

Choose the database that best matches the application's data model, query patterns, scalability requirements, and consistency needs. Modern systems commonly use **polyglot persistence**, combining multiple databases where each excels.