# System Design on AWS

> A collection of common System Design interview problems mapped to AWS services.

---

# 1. Design an E-Commerce Platform

## Requirements

- Browse products
- Place orders
- Payments
- Image storage
- Notifications
- High availability
- Scalability

## AWS Architecture

```

Users
│
Route53
│
CloudFront
│
Application Load Balancer
│
ECS (Fargate)
│
Spring Boot Microservices
│
├── Product Service
├── Order Service
├── Inventory Service
├── Payment Service
├── Notification Service
│
SNS
│
SQS
│
Aurora PostgreSQL
│
Redis
│
S3
│
CloudWatch

```

### Why these services?

| Requirement | AWS Service |
|-------------|-------------|
| Images | S3 |
| Product Cache | Redis |
| Orders | Aurora |
| Notifications | SNS |
| Async Processing | SQS |
| Containers | ECS |
| CDN | CloudFront |

---

# 2. Design Instagram

## Requirements

- Upload images
- News Feed
- Likes
- Comments
- Notifications

## AWS Architecture

```

Users

↓

CloudFront

↓

ALB

↓

ECS

↓

Spring Boot

↓

Redis

↓

Aurora

↓

S3

↓

Lambda

```

Image Upload Flow

```

Mobile App

↓

Spring Boot

↓

Generate Presigned URL

↓

S3

↓

Lambda

↓

Generate Thumbnail

↓

CloudFront

```

### AWS Services Used

- S3
- Lambda
- CloudFront
- Redis
- Aurora
- ECS

---

# 3. Design YouTube

## Requirements

- Upload videos
- Video transcoding
- Streaming
- Global delivery

## AWS Architecture

```

Users

↓

CloudFront

↓

S3

↓

SQS

↓

Video Workers

↓

Generate 240p

480p

720p

1080p

↓

CloudFront

```

### AWS Services

- S3
- CloudFront
- SQS
- ECS
- Lambda

---

# 4. Design WhatsApp

## Requirements

- Real-time chat
- Image sharing
- Notifications

```

Users

↓

ALB

↓

Chat Service

↓

Redis Pub/Sub

↓

Aurora

↓

S3

↓

SNS

```

### AWS Services

- ECS
- Redis
- Aurora
- SNS
- S3

---

# 5. Design Uber

## Requirements

- Book ride
- Driver matching
- Payments
- Notifications

```

Users

↓

API Gateway

↓

Ride Service

↓

SNS

↓

Driver Matching

↓

Payment

↓

Notification

↓

Aurora

↓

Redis

```

---

# 6. Design Netflix

## Requirements

- Video streaming
- Recommendations
- Authentication

```

Users

↓

CloudFront

↓

S3

↓

Recommendation Service

↓

Redis

↓

Aurora

```

---

# 7. Design URL Shortener

## Requirements

- Short URL
- Fast redirect
- Millions of requests

```

Users

↓

API Gateway

↓

Lambda

↓

DynamoDB

```

Why DynamoDB?

- Key-value lookup
- Very low latency
- Massive scale

---

# 8. Design Notification System

```

Application

↓

SNS

↓

Email Queue

↓

SMS Queue

↓

Push Queue

↓

Lambda

↓

SES

```

---

# 9. Design Payment System

```

Checkout

↓

FIFO Queue

↓

Payment Service

↓

Aurora

↓

SNS

↓

Email

```

Why FIFO?

- Exactly once processing
- Ordered transactions

---

# 10. Design Order Processing

```

Order API

↓

SNS

↓

Inventory Queue

↓

Shipping Queue

↓

Billing Queue

↓

Consumers

↓

Aurora

```

---

# 11. Design Logging Platform

```

Applications

↓

CloudWatch

↓

Kinesis

↓

Lambda

↓

S3

↓

Athena

↓

QuickSight

```

---

# 12. Design Analytics Platform

```

Applications

↓

Kinesis

↓

Lambda

↓

S3

↓

Athena

↓

QuickSight

```

---

# 13. Design Image Processing

```

User Upload

↓

S3

↓

Lambda

↓

Resize Image

↓

CloudFront

```

---

# 14. Design Resume Processing

```

Candidate Upload

↓

S3

↓

Lambda

↓

Textract

↓

Aurora

↓

OpenSearch

```

---

# 15. Design Banking Application

```

Users

↓

Route53

↓

Global Accelerator

↓

ALB

↓

Spring Boot

↓

Aurora Multi-AZ

↓

Redis

↓

CloudWatch

↓

CloudTrail

```

---

# 16. Design AI Chat Application

```

Users

↓

API Gateway

↓

Spring Boot

↓

Amazon Bedrock

↓

Redis

↓

Aurora

↓

S3

```

---

# 17. Design CI/CD Pipeline

```

GitHub

↓

GitHub Actions

↓

Docker Build

↓

ECR

↓

ECS

↓

ALB

↓

Users

```

---

# 18. Design Event-Driven Microservices

```

Order Service

↓

SNS

↓

Inventory

↓

Shipping

↓

Notification

↓

Analytics

↓

Billing

```

---

# 19. Design Multi-Region Application

```

Users

↓

Global Accelerator

↓

Region A

↓

ALB

↓

Aurora Global

↓

Region B

```

---

# 20. Design Enterprise Spring Boot Platform

```

Users

↓

Route53

↓

CloudFront

↓

ALB

↓

ECS (Fargate)

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

↓

CloudTrail

↓

Secrets Manager

```

---

# AWS Services Used by Problem

| Problem | AWS Services |
|-----------|--------------|
| Image Upload | S3 + Lambda |
| Video Streaming | S3 + CloudFront |
| REST API | ALB + ECS |
| Serverless API | API Gateway + Lambda |
| Notifications | SNS |
| Async Processing | SQS |
| Payments | FIFO Queue |
| Cache | Redis |
| SQL Database | Aurora |
| Global Routing | Global Accelerator |
| CDN | CloudFront |
| Containers | ECS |
| Kubernetes | EKS |
| Monitoring | CloudWatch |
| Logging | CloudTrail |
| Authentication | IAM |

---

# Common Interview Questions

### Why ECS instead of EC2?

Containerized deployments with less operational overhead.

---

### Why Aurora instead of RDS?

Better performance and higher availability.

---

### Why SNS + SQS?

SNS broadcasts events, while SQS allows each consumer to process messages independently and reliably.

---

### Why Redis?

Reduce database load and improve response times.

---

### Why CloudFront?

Reduce latency and cache static content globally.

---

### Why S3?

Highly durable, scalable object storage for files, images, and videos.

---

# AWS Architecture Patterns

- Monolithic Application
- Microservices
- Event-Driven Architecture
- Serverless Architecture
- CQRS
- Saga Pattern
- Fan-Out Pattern
- Cache-Aside Pattern
- Retry Pattern
- Dead Letter Queue Pattern
- Blue-Green Deployment
- Rolling Deployment

---

# Senior Backend Interview Strategy

When designing any system:

1. Define functional requirements.
2. Identify non-functional requirements (availability, scalability, latency, security).
3. Choose AWS services based on the problem, not familiarity.
4. Explain trade-offs (e.g., ECS vs Lambda, Aurora vs DynamoDB).
5. Discuss failure handling, monitoring, and security.
6. Mention observability (CloudWatch, CloudTrail, X-Ray) and CI/CD (ECR + ECS).

---

# One-Line Revision

Design systems by mapping business requirements to AWS managed services, choosing components that provide scalability, high availability, fault tolerance, security, and operational simplicity.