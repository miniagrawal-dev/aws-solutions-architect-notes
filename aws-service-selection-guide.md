# AWS Service Selection Guide

> **Purpose:** Quickly decide which AWS service to use for a particular requirement.

---

# Compute Services

| Requirement             | AWS Service | Why?                                 |
| ----------------------- | ----------- | ------------------------------------ |
| Virtual Machine         | EC2         | Full control over OS and runtime     |
| Container Orchestration | ECS         | Simple AWS-native container platform |
| Kubernetes              | EKS         | Managed Kubernetes                   |
| Serverless Containers   | Fargate     | No server management                 |
| Event-driven Compute    | Lambda      | Pay per execution                    |

---

# Storage Services

| Requirement        | AWS Service | Why?                              |
| ------------------ | ----------- | --------------------------------- |
| Object Storage     | S3          | Unlimited scalable storage        |
| Block Storage      | EBS         | Persistent storage for EC2        |
| Shared File System | EFS         | Linux shared file storage         |
| Windows File Share | FSx Windows | SMB & Active Directory            |
| HPC Storage        | FSx Lustre  | High-performance parallel storage |

---

# Database Services

| Requirement          | AWS Service       | Why?                             |
| -------------------- | ----------------- | -------------------------------- |
| Relational Database  | RDS               | Managed SQL database             |
| High Performance SQL | Aurora            | Cloud-native relational database |
| NoSQL                | DynamoDB          | Serverless key-value database    |
| Cache                | ElastiCache Redis | Reduce database load             |

---

# Messaging Services

| Requirement       | AWS Service | Why?                                |
| ----------------- | ----------- | ----------------------------------- |
| Background Jobs   | SQS         | Queue-based asynchronous processing |
| Publish-Subscribe | SNS         | Fan-out notifications               |
| Event Streaming   | Kinesis     | Real-time data streaming            |
| Legacy Messaging  | Amazon MQ   | JMS/ActiveMQ compatibility          |

---

# Networking Services

| Requirement                 | AWS Service        | Why?                                    |
| --------------------------- | ------------------ | --------------------------------------- |
| DNS                         | Route53            | Managed DNS                             |
| CDN                         | CloudFront         | Cache content globally                  |
| Global Network Optimization | Global Accelerator | Faster routing for dynamic applications |
| Internal VPC Network        | VPC                | Isolated cloud network                  |

---

# Security Services

| Requirement                    | AWS Service     | Why?                      |
| ------------------------------ | --------------- | ------------------------- |
| Authentication & Authorization | IAM             | Access management         |
| Secret Storage                 | Secrets Manager | Secure credentials        |
| SSL Certificates               | ACM             | Free managed certificates |
| DDoS Protection                | AWS Shield      | Network protection        |
| Web Firewall                   | AWS WAF         | Protect web applications  |

---

# Monitoring Services

| Requirement         | AWS Service        | Why?                  |
| ------------------- | ------------------ | --------------------- |
| Logs                | CloudWatch Logs    | Centralized logging   |
| Metrics             | CloudWatch Metrics | Resource monitoring   |
| Distributed Tracing | AWS X-Ray          | Request tracing       |
| Audit               | CloudTrail         | API activity tracking |

---

# Migration Services

| Requirement            | AWS Service     | Why?                    |
| ---------------------- | --------------- | ----------------------- |
| Large Offline Transfer | Snowball        | Physical device         |
| Continuous Data Sync   | DataSync        | Online synchronization  |
| Hybrid Storage         | Storage Gateway | On-premises integration |
| Managed SFTP           | Transfer Family | FTP/SFTP service        |

---

# Which Compute Service?

Need complete server control?

→ EC2

Need containers?

→ ECS

Already using Kubernetes?

→ EKS

Don't want servers?

→ Fargate

Need event-driven execution?

→ Lambda

---

# Which Storage Service?

Images

Videos

Backups

↓

S3

Database Disk

↓

EBS

Shared Linux Files

↓

EFS

Windows File Server

↓

FSx

---

# Which Database?

SQL

↓

RDS

Need higher performance

↓

Aurora

Key-Value

↓

DynamoDB

Reduce database load

↓

Redis

---

# Which Messaging Service?

Asynchronous Processing

↓

SQS

Broadcast Event

↓

SNS

Real-Time Stream

↓

Kinesis

Legacy JMS

↓

Amazon MQ

---

# Which Networking Service?

Need DNS?

↓

Route53

Need CDN?

↓

CloudFront

Need Global Low-Latency Routing?

↓

Global Accelerator

---

# Which Serverless Service?

REST API

↓

API Gateway

↓

Lambda

Workflow

↓

Step Functions

Events

↓

EventBridge

---

# Common Production Stack

Route53

↓

CloudFront

↓

ALB

↓

ECS/Fargate

↓

Spring Boot

↓

Redis

↓

Aurora

↓

S3

↓

CloudWatch

---

# Senior Backend Cheat Sheet

| Requirement     | Best AWS Service |
| --------------- | ---------------- |
| Store Images    | S3               |
| Background Jobs | SQS              |
| Notifications   | SNS              |
| Cache           | Redis            |
| SQL Database    | Aurora           |
| Global CDN      | CloudFront       |
| Containers      | ECS              |
| Kubernetes      | EKS              |
| Serverless API  | Lambda           |
| Workflow        | Step Functions   |
| Monitoring      | CloudWatch       |
| Authentication  | IAM              |

---

# One-Line Revision

Choose AWS services based on the problem they solve rather than memorizing the service names. Focus on understanding the trade-offs between similar services.
