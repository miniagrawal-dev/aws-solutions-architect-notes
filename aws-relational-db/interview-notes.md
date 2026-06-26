# AWS RDS, Aurora & ElastiCache - Interview Notes

# What is Amazon RDS?

Amazon RDS is a managed relational database service that automates database administration tasks such as backups, patching, monitoring, scaling, and failover.

---

# Why use RDS instead of installing MySQL on EC2?

RDS provides:

* Automatic backups
* Automatic patching
* High Availability
* Monitoring
* Easier scaling
* Reduced operational effort

EC2 requires managing everything manually.

---

# What is Multi-AZ?

Purpose:

High Availability

Characteristics:

* Synchronous replication
* Standby database
* Automatic failover
* Same Region

Used for production workloads.

---

# What are Read Replicas?

Purpose:

Read Scaling

Characteristics:

* Asynchronous replication
* Multiple replicas
* Read-only
* Used for analytics and reporting

No automatic failover.

---

# Multi-AZ vs Read Replica

| Feature            | Multi-AZ          | Read Replica |
| ------------------ | ----------------- | ------------ |
| Purpose            | High Availability | Read Scaling |
| Replication        | Synchronous       | Asynchronous |
| Writes             | Primary Only      | No           |
| Reads              | Primary           | Replica      |
| Automatic Failover | Yes               | No           |

---

# What is Amazon Aurora?

Aurora is AWS's managed relational database compatible with MySQL and PostgreSQL.

Advantages:

* Higher performance
* Shared distributed storage
* Automatic replication
* Self-healing storage
* Faster failover
* Up to 15 Read Replicas

---

# Why is Aurora faster?

Aurora separates compute from storage.

Storage is automatically replicated across multiple Availability Zones.

Database nodes only handle query processing.

---

# What is ElastiCache?

Managed in-memory cache.

Purpose:

Reduce database queries.

Improve application response time.

---

# Redis vs Memcached

| Redis                | Memcached        |
| -------------------- | ---------------- |
| Persistent           | No Persistence   |
| Replication          | No               |
| Pub/Sub              | No               |
| Transactions         | No               |
| Rich Data Structures | Simple Key-Value |

Redis is preferred in production.

---

# When should Redis be used?

* User Sessions
* Product Catalog
* API Responses
* Leaderboards
* Shopping Cart
* Rate Limiting
* Authentication Tokens

---

# Cache-Aside Pattern

Application receives request.

↓

Check Redis.

↓

Cache Hit?

Yes → Return Data.

No →

Query Database

↓

Store in Redis

↓

Return Response.

This is the most commonly used caching strategy.

---

# Common Interview Questions

## Q1. Multi-AZ or Read Replica?

Multi-AZ improves availability.

Read Replica improves read throughput.

---

## Q2. Why not cache everything?

Cache has limited memory.

Frequently changing data causes stale values.

Only cache frequently accessed and relatively stable data.

---

## Q3. Redis or Memcached?

Redis.

Because it supports persistence, replication, transactions, Pub/Sub, TTL, and advanced data structures.

---

## Q4. Why is Aurora preferred over MySQL?

Aurora offers better performance, automatic storage scaling, faster failover, and distributed storage with high availability.

---

## Q5. How would you scale a read-heavy application?

* Add Read Replicas
* Use Redis cache
* Use Application Load Balancer
* Use Auto Scaling for application servers

---

## Q6. What happens during RDS failover?

If the primary database becomes unavailable, AWS automatically promotes the standby instance in a Multi-AZ deployment. Applications reconnect using the same endpoint.

---

## Senior Backend Interview Focus

Know these thoroughly:

* Multi-AZ vs Read Replica
* Aurora Architecture
* Redis vs Memcached
* Cache-Aside Pattern
* Cache Invalidation
* TTL
* Connection Pooling
* RDS Proxy (conceptually)
* High Availability
* Scaling Read-Heavy Systems

---

# Production Architecture

Users

↓

CloudFront

↓

Application Load Balancer

↓

EC2 Auto Scaling

↓

Redis (Cache)

↓

Aurora Cluster

↓

S3

---

# One-Line Revision

Use RDS for managed relational databases, Aurora for high-performance cloud-native databases, Multi-AZ for high availability, Read Replicas for read scaling, and Redis to reduce database load and improve application performance.
