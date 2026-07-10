# AWS Interview Cheatsheet (Senior Backend Engineer)

> **Purpose:** Quick revision guide for AWS interviews. Focus on choosing the right service, understanding trade-offs, and explaining production use cases.

---

# Compute

## EC2 vs ECS vs EKS vs Lambda

| EC2               | ECS                   | EKS                   | Lambda            |
| ----------------- | --------------------- | --------------------- | ----------------- |
| Virtual Machine   | AWS Container Service | Kubernetes            | Serverless        |
| Manage OS         | Manage Containers     | Kubernetes Management | No Infrastructure |
| Long-running apps | Containerized Apps    | Kubernetes Apps       | Event-driven      |
| Highest Control   | Simple                | Most Flexible         | Simplest          |

**Use EC2 when:**

* Need OS-level control
* Legacy applications
* Custom software

**Use ECS when:**

* Running Docker containers on AWS
* Simpler than Kubernetes
* AWS-native deployments

**Use EKS when:**

* Kubernetes already used
* Multi-cloud strategy
* Advanced orchestration

**Use Lambda when:**

* Event-driven
* APIs
* Automation
* Scheduled jobs

---

# Storage

## S3 vs EBS vs EFS vs FSx

| S3             | EBS             | EFS                | FSx                     |
| -------------- | --------------- | ------------------ | ----------------------- |
| Object Storage | Block Storage   | Shared File System | Specialized File System |
| Unlimited      | Attached to EC2 | Shared across EC2  | Windows/HPC             |

Examples

Images → S3

Database Disk → EBS

Shared Linux Files → EFS

Windows File Share → FSx

---

# Databases

## RDS vs Aurora

| RDS                   | Aurora                |
| --------------------- | --------------------- |
| Managed Database      | Cloud Native Database |
| Standard Performance  | Higher Performance    |
| Limited Read Replicas | Up to 15 Replicas     |
| Lower Cost            | Higher Cost           |

Choose Aurora when:

* High traffic
* Mission critical
* Better availability

---

## Redis vs Memcached

| Redis           | Memcached      |
| --------------- | -------------- |
| Persistent      | No Persistence |
| Replication     | No             |
| Pub/Sub         | No             |
| Transactions    | No             |
| Rich Data Types | Key-Value Only |

Redis is the default choice.

---

# Networking

## ALB vs NLB

| ALB          | NLB     |
| ------------ | ------- |
| Layer 7      | Layer 4 |
| HTTP/HTTPS   | TCP/UDP |
| Path Routing | No      |
| Host Routing | No      |

Use ALB for:

* Spring Boot
* REST APIs
* Microservices

Use NLB for:

* Gaming
* Financial Systems
* TCP Applications

---

## CloudFront vs Global Accelerator

| CloudFront     | Global Accelerator   |
| -------------- | -------------------- |
| CDN            | Network Accelerator  |
| Caches Content | No Cache             |
| Static Files   | Dynamic Applications |
| Edge Cache     | AWS Backbone         |

CloudFront

↓

Images

Videos

CSS

Global Accelerator

↓

Gaming

Trading

APIs

---

## Route53 vs CloudFront

Route53

DNS

↓

Find Application

CloudFront

↓

Deliver Content Faster

---

# Messaging

## SQS vs SNS vs Kinesis vs Amazon MQ

| SQS        | SNS           | Kinesis          | MQ                 |
| ---------- | ------------- | ---------------- | ------------------ |
| Queue      | Pub/Sub       | Streaming        | Traditional Broker |
| Async Jobs | Notifications | Real-Time Events | JMS                |

Examples

Order Queue

↓

SQS

Notification

↓

SNS

IoT Events

↓

Kinesis

Legacy Java

↓

Amazon MQ

---

## Standard Queue vs FIFO

| Standard          | FIFO             |
| ----------------- | ---------------- |
| At-least-once     | Exactly-once     |
| Best Effort Order | Strict Order     |
| Higher Throughput | Lower Throughput |

FIFO

↓

Payments

Inventory

Orders

---

# Containers

## ECS vs Fargate

| ECS EC2      | Fargate         |
| ------------ | --------------- |
| Manage EC2   | Serverless      |
| Lower Cost   | Easier          |
| More Control | Less Management |

---

## ECS vs Kubernetes

ECS

* AWS only
* Easier

Kubernetes

* Multi-cloud
* More powerful
* Higher complexity

---

# Serverless

## API Gateway vs ALB

| API Gateway    | ALB      |
| -------------- | -------- |
| Lambda         | EC2/ECS  |
| Rate Limiting  | No       |
| Authentication | Basic    |
| REST APIs      | Web Apps |

---

## Lambda vs ECS

Lambda

* Event Driven
* Short Running
* No Server

ECS

* Long Running
* Spring Boot
* Containers

---

# Security

## IAM User vs IAM Role

User

Permanent Identity

Role

Temporary Identity

Use Roles for:

* EC2
* Lambda
* ECS

Never store AWS Access Keys inside applications.

---

## Bucket Policy vs IAM Policy

IAM Policy

↓

User Permission

Bucket Policy

↓

Bucket Permission

---

# Scaling

## Multi-AZ vs Read Replica

| Multi-AZ           | Read Replica |
| ------------------ | ------------ |
| High Availability  | Read Scaling |
| Synchronous        | Asynchronous |
| Automatic Failover | No           |

---

## Auto Scaling vs Load Balancer

Load Balancer

↓

Distributes Traffic

Auto Scaling

↓

Creates More Servers

Usually used together.

---

# Common Production Architecture

Users

↓

Route53

↓

CloudFront

↓

Application Load Balancer

↓

ECS Fargate

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

# Which Service Should I Choose?

Store Images?

→ S3

Run Containers?

→ ECS

Need Kubernetes?

→ EKS

Need Serverless?

→ Lambda

Background Jobs?

→ SQS

Notifications?

→ SNS

Streaming?

→ Kinesis

SQL Database?

→ Aurora

Cache?

→ Redis

DNS?

→ Route53

CDN?

→ CloudFront

Global Routing?

→ Global Accelerator

Container Images?

→ ECR

Secrets?

→ Secrets Manager

Workflow?

→ Step Functions

Events?

→ EventBridge

---

# Top 20 Interview Questions

1. EC2 vs ECS?
2. ECS vs EKS?
3. Lambda vs ECS?
4. RDS vs Aurora?
5. Redis vs Memcached?
6. SQS vs SNS?
7. SNS vs EventBridge?
8. CloudFront vs Global Accelerator?
9. ALB vs NLB?
10. S3 vs EBS?
11. EFS vs FSx?
12. IAM User vs Role?
13. Multi-AZ vs Read Replica?
14. API Gateway vs ALB?
15. Fargate vs EC2?
16. Route53 vs CloudFront?
17. Storage Gateway vs DataSync?
18. Kinesis vs Kafka?
19. Standard Queue vs FIFO?
20. When not to use Lambda?

---

# 10 AWS Golden Rules

1. Store files in S3, not the database.
2. Use IAM Roles instead of Access Keys.
3. Put CloudFront in front of S3.
4. Use ALB with Auto Scaling.
5. Cache frequently accessed data using Redis.
6. Use Multi-AZ for production databases.
7. Use SQS to decouple microservices.
8. Prefer Fargate if you don't need server management.
9. Use CloudWatch for monitoring and CloudTrail for auditing.
10. Design applications to be stateless whenever possible.

---

# 5-Minute Revision Before Interview

Compute

EC2 → ECS → EKS → Lambda

Storage

S3 → EBS → EFS → FSx

Database

RDS → Aurora → Redis

Messaging

SQS → SNS → Kinesis

Networking

Route53 → CloudFront → ALB

Containers

ECR → ECS → Fargate → EKS

Serverless

Lambda → API Gateway → EventBridge → Step Functions

---

# One-Line Revision

Choose AWS services based on the problem you're solving, understand the trade-offs between similar services, and always explain your choice using a real production scenario rather than just definitions.
