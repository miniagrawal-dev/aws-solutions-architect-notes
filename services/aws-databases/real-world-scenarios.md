# AWS Databases - Real World Scenarios

# 1. Banking Application

Requirements:

- Transactions
- ACID compliance
- Auditing

Database:

Aurora PostgreSQL

Reason:

Strong consistency and transactional support.

---

# 2. E-Commerce Product Catalog

Requirements:

- Product information
- Flexible schema
- JSON documents

Database:

DocumentDB

---

# 3. Shopping Cart

Requirements:

- Fast lookups
- Low latency
- Massive scale

Database:

DynamoDB

---

# 4. User Session Store

Requirements:

- Very fast reads/writes
- Temporary data

Database:

ElastiCache Redis

---

# 5. Social Network

Requirements:

- Friend relationships
- Followers
- Recommendations

Database:

Neptune

---

# 6. IoT Sensor Monitoring

Requirements:

- Millions of sensor readings
- Time-based queries

Database:

Timestream

---

# 7. Financial Audit System

Requirements:

- Immutable history
- Compliance
- Traceability

Database:

QLDB

---

# 8. Smart City Analytics

Requirements:

- Large-scale event storage
- High write throughput

Database:

Keyspaces

---

# 9. Online Learning Platform

Students

↓

Spring Boot

↓

Aurora

↓

Redis

↓

S3

Course progress is stored in Aurora, frequently accessed data is cached in Redis, and videos are stored in S3.

---

# 10. Recommendation Engine

Users

↓

Application

↓

Neptune

↓

Recommendations

↓

Redis Cache

Relationships between users and products are modeled in Neptune.

---

# Database Selection Guide

| Requirement | Database |
|-------------|----------|
| Banking | Aurora |
| Orders | Aurora |
| User Sessions | Redis |
| Shopping Cart | DynamoDB |
| Product Catalog | DocumentDB |
| Social Graph | Neptune |
| Audit Trail | QLDB |
| IoT Metrics | Timestream |
| Massive Writes | Keyspaces |

---

# Mapping to Your Experience

| Your Experience | AWS Equivalent |
|-----------------|----------------|
| Azure SQL | Aurora / RDS |
| Azure Cosmos DB | DynamoDB (or DocumentDB depending on the data model) |
| Redis Cache | ElastiCache Redis |
| IBM MQ Events | DynamoDB Streams + Lambda (event-driven processing) |

---

# Common Design Patterns

### Cache-Aside Pattern
Application → Redis → Aurora

### CQRS
Aurora for writes, DynamoDB or Redis for optimized reads where appropriate.

### Event-Driven Updates
Application → DynamoDB → Streams → Lambda

### Polyglot Persistence
Use multiple databases, each chosen for its strengths.

---

# Senior Backend Interview Questions

### Can one application use multiple databases?

Yes. This is called **polyglot persistence**. For example:
- Aurora for transactions
- Redis for caching
- S3 for file storage
- Neptune for recommendations

### Why not store everything in DynamoDB?

Because relational queries, joins, and complex transactions are not its strengths.

### Why not cache everything?

Cache memory is limited, and stale data can become an issue. Cache only frequently accessed data with an appropriate invalidation strategy.

---

# One-Line Revision

Modern cloud applications often use multiple AWS databases together, selecting each service based on the workload rather than relying on a single database for every use case.