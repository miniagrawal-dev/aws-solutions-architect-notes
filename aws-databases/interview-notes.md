# AWS Databases Interview Notes

# Database Selection

The first question should always be:

"What type of data am I storing?"

Choose the database based on data model and access patterns.

---

# RDS vs Aurora

| RDS | Aurora |
|------|---------|
| Managed relational database | Cloud-native relational database |
| Standard performance | Higher performance |
| Lower cost | Higher availability |

Choose Aurora for high-traffic production systems.

---

# Aurora vs DynamoDB

| Aurora | DynamoDB |
|----------|-----------|
| SQL | NoSQL |
| ACID Transactions | Key-Value |
| Joins | No Joins |
| Complex Queries | Simple Access Patterns |

---

# DynamoDB

Use Cases:

- Shopping Cart
- Gaming
- User Sessions
- IoT
- Leaderboards

Advantages:

- Serverless
- Automatic Scaling
- Single-digit millisecond latency

---

# Redis

Purpose:

Reduce database load.

Store:

- Sessions
- Frequently accessed data
- API responses

---

# DocumentDB

Best for:

JSON documents.

MongoDB-compatible applications.

---

# Neptune

Purpose:

Store relationships.

Examples:

- Friends
- Followers
- Product recommendations

---

# QLDB

Immutable ledger.

Every change is permanently recorded.

Used for:

- Financial auditing
- Compliance
- Asset tracking

---

# Timestream

Optimized for timestamped data.

Examples:

- CPU usage
- Temperature sensors
- Application metrics

---

# Keyspaces

Managed Cassandra.

Designed for:

- Massive write throughput
- Large distributed datasets

---

# Common Interview Questions

## How do you choose a database?

Consider:

- Data model
- Query patterns
- Transactions
- Scalability
- Consistency
- Cost

---

## When would you use DynamoDB instead of Aurora?

Choose DynamoDB for key-value access patterns with predictable low latency and massive scale.

---

## Why use Redis?

To cache frequently accessed data and reduce pressure on the primary database.

---

## When should Neptune be used?

When relationships between entities are central to the application.

---

## Why use QLDB instead of a relational database?

When an immutable audit trail is required.

---

## Senior Backend Focus

Know:

- SQL vs NoSQL
- Aurora vs DynamoDB
- Redis use cases
- Graph databases
- Time-series databases
- Document databases
- CAP theorem (conceptually)
- Eventual consistency vs strong consistency

---

# One-Line Revision

Choose the AWS database that best matches your data model and access patterns rather than trying to fit every workload into a relational database.