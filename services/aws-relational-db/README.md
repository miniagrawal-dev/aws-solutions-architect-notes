# AWS RDS, Aurora & ElastiCache

# Overview

This section covers AWS managed database services and caching solutions used to build scalable, highly available backend applications.

Topics Covered:

* Amazon RDS
* Amazon Aurora
* Amazon ElastiCache
* Read Replicas
* Multi-AZ Deployments
* Backups & Snapshots
* Database Security
* Redis
* Memcached

---

# Amazon RDS

Amazon Relational Database Service (RDS) is a fully managed relational database service.

Supported Databases:

* MySQL
* PostgreSQL
* MariaDB
* Oracle
* SQL Server

AWS manages:

* Installation
* Patching
* Automated Backups
* Monitoring
* Failover
* Maintenance

Developers focus only on application development.

---

# Benefits of RDS

* Fully Managed
* Automatic Backups
* Multi-AZ High Availability
* Read Replicas
* Automatic Patching
* Easy Scaling
* Monitoring using CloudWatch

---

# Multi-AZ Deployment

Purpose:

High Availability

Architecture:

Application

↓

Primary Database

↓

Synchronous Replication

↓

Standby Database

If Primary fails:

AWS automatically promotes Standby.

Application reconnects automatically.

Used for:

* Disaster Recovery
* Production Databases

---

# Read Replicas

Purpose:

Improve Read Performance

Architecture:

Primary Database

↓

Asynchronous Replication

↓

Read Replica

Read Queries

Write Queries

Application can distribute read traffic to replicas.

Supports multiple Read Replicas.

---

# Multi-AZ vs Read Replica

| Multi-AZ           | Read Replica          |
| ------------------ | --------------------- |
| High Availability  | Read Scaling          |
| Synchronous        | Asynchronous          |
| Automatic Failover | No Automatic Failover |
| Same Region        | Same or Cross Region  |

---

# Amazon Aurora

Aurora is AWS's cloud-native relational database.

Compatible with:

* MySQL
* PostgreSQL

Benefits:

* Faster than standard MySQL/PostgreSQL
* Highly Available
* Self-healing Storage
* Automatic Replication
* Up to 15 Read Replicas
* Storage automatically grows

Aurora is generally recommended for new production workloads requiring high performance.

---

# Aurora Architecture

Application

↓

Aurora Writer

↓

Shared Distributed Storage

↓

Aurora Readers

Storage replicated across multiple Availability Zones.

---

# Amazon ElastiCache

Managed in-memory caching service.

Supported Engines:

* Redis
* Memcached

Purpose:

Reduce database load.

Improve response time.

Store frequently accessed data in memory.

---

# Redis

Features:

* Persistent
* Replication
* Pub/Sub
* Transactions
* Sorted Sets
* TTL
* Distributed Cache

Common Use Cases:

* Session Storage
* Rate Limiting
* Leaderboards
* Distributed Locking
* API Cache

---

# Memcached

Features:

* Very Simple
* Extremely Fast
* No Persistence
* No Replication
* Multi-threaded

Best for:

Temporary Cache

---

# Redis vs Memcached

| Redis                | Memcached      |
| -------------------- | -------------- |
| Persistence          | No Persistence |
| Replication          | No             |
| Rich Data Structures | Key-Value Only |
| Pub/Sub              | No             |
| Distributed Lock     | No             |

Redis is the preferred choice for most production applications.

---

# Cache Flow

User

↓

Application

↓

Redis Cache

↓

RDS

If data exists in Redis:

Return immediately.

Otherwise:

Read from RDS

↓

Store in Redis

↓

Return Response

---

# Hands-On Completed

* Created RDS instance
* Configured Multi-AZ
* Created Read Replica
* Connected to database
* Learned Aurora architecture
* Explored Redis and Memcached
* Understood caching strategies

---

# Best Practices

* Use Multi-AZ for production databases.
* Use Read Replicas for read-heavy workloads.
* Use Aurora for high-performance applications.
* Cache frequently accessed data using Redis.
* Never cache everything blindly.
* Monitor cache hit ratio.
* Set proper TTL values.
* Avoid storing sensitive data in cache.

---

# Real-World Example

Spring Boot

↓

Application Load Balancer

↓

EC2 Auto Scaling

↓

Redis

↓

Aurora

↓

S3

This architecture provides scalability, high availability, and low latency for production applications.
