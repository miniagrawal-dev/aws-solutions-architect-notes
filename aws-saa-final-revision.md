# AWS Solutions Architect Associate - Final Revision Guide

> Ultimate AWS Interview Revision for Backend Engineers & Solution Architects

---

# Table of Contents

1. AWS Service Selection Guide
2. Top 50 Service Comparisons
3. Core Architectures
4. Security Cheat Sheet
5. Networking Cheat Sheet
6. Database Selection Guide
7. Messaging Selection Guide
8. Serverless Cheat Sheet
9. Containers Cheat Sheet
10. Monitoring Cheat Sheet
11. Analytics Cheat Sheet
12. AI/ML Cheat Sheet
13. Storage Cheat Sheet
14. Top 100 Interview Questions
15. System Design Mapping
16. Production Checklist
17. One-Line Revision

---

# AWS Service Selection Guide

| Need | Service |
|--------|---------|
| Virtual Machine | EC2 |
| Containers | ECS |
| Kubernetes | EKS |
| Serverless | Lambda |
| SQL Database | Aurora |
| NoSQL | DynamoDB |
| Cache | ElastiCache Redis |
| Object Storage | S3 |
| File Storage | EFS |
| Block Storage | EBS |
| Queue | SQS |
| Notification | SNS |
| Event Bus | EventBridge |
| Streaming | Kinesis |
| Kafka | MSK |
| Search | OpenSearch |
| Monitoring | CloudWatch |
| Audit | CloudTrail |
| Configuration History | Config |
| CDN | CloudFront |
| DNS | Route53 |
| Secrets | Secrets Manager |
| Encryption | KMS |
| Firewall | WAF |
| DDoS | Shield |
| ETL | Glue |
| SQL on S3 | Athena |
| Data Warehouse | Redshift |
| BI | QuickSight |
| OCR | Textract |
| GenAI | Bedrock |
| ML Platform | SageMaker |

---

# Top 50 Service Comparisons

## EC2 vs Lambda

EC2

- Long-running applications
- Full OS control
- Manual scaling

Lambda

- Event-driven
- Serverless
- Auto scaling

---

## ECS vs EKS

ECS

- AWS native
- Easier
- Less operational overhead

EKS

- Kubernetes
- Portable
- More flexibility

---

## ECS vs Fargate

ECS EC2

↓

Manage servers

Fargate

↓

Serverless containers

---

## RDS vs Aurora

RDS

↓

Managed Database

Aurora

↓

Cloud-native

↓

Higher Performance

↓

Faster Failover

---

## Aurora vs DynamoDB

Aurora

↓

Relational

↓

SQL

↓

ACID

DynamoDB

↓

NoSQL

↓

Massive Scale

---

## S3 vs EBS vs EFS

S3

↓

Object Storage

EBS

↓

Block Storage

EFS

↓

Shared File Storage

---

## ALB vs NLB

ALB

↓

HTTP/HTTPS

↓

Layer 7

NLB

↓

TCP/UDP

↓

Layer 4

---

## Security Group vs NACL

Security Group

↓

Stateful

↓

Instance

NACL

↓

Stateless

↓

Subnet

---

## Internet Gateway vs NAT Gateway

Internet Gateway

↓

Inbound + Outbound

Public Resources

NAT Gateway

↓

Outbound Only

Private Resources

---

## CloudWatch vs CloudTrail vs Config

CloudWatch

↓

Monitoring

CloudTrail

↓

API Audit

Config

↓

Configuration History

---

## Secrets Manager vs Parameter Store

Secrets Manager

↓

Secrets

↓

Rotation

Parameter Store

↓

Configuration

---

## WAF vs Shield

WAF

↓

SQL Injection

↓

XSS

Shield

↓

DDoS

---

## Athena vs Redshift

Athena

↓

SQL on S3

Redshift

↓

Data Warehouse

---

## Glue vs EMR

Glue

↓

Serverless ETL

EMR

↓

Big Data Cluster

---

## Bedrock vs SageMaker

Bedrock

↓

Foundation Models

SageMaker

↓

Train Models

---

# Production Architecture

Users

↓

Route53

↓

CloudFront

↓

AWS WAF

↓

ALB

↓

ECS

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

---

# Security Checklist

✓ IAM Roles

✓ Least Privilege

✓ MFA

✓ KMS

✓ Secrets Manager

✓ HTTPS

✓ WAF

✓ Shield

✓ CloudTrail

✓ Config

✓ CloudWatch

---

# Networking Checklist

✓ VPC

✓ Public Subnet

✓ Private Subnet

✓ Multi AZ

✓ NAT Gateway

✓ Internet Gateway

✓ Route Tables

✓ Security Groups

✓ VPC Endpoint

✓ Transit Gateway

---

# Database Selection

| Need | Database |
|------|----------|
| SQL | Aurora |
| NoSQL | DynamoDB |
| Cache | Redis |
| Ledger | QLDB |
| Graph | Neptune |
| Time Series | Timestream |
| Documents | DocumentDB |

---

# Messaging Selection

Need Queue?

↓

SQS

Need Pub/Sub?

↓

SNS

Need Kafka?

↓

MSK

Need Event Bus?

↓

EventBridge

Need Streaming?

↓

Kinesis

---

# Monitoring Stack

Metrics

↓

CloudWatch

Logs

↓

CloudWatch Logs

Tracing

↓

X-Ray

Auditing

↓

CloudTrail

Configuration

↓

Config

---

# AI Services

OCR

↓

Textract

Chatbot

↓

Lex

Speech

↓

Transcribe

Translation

↓

Translate

Recommendations

↓

Personalize

Search

↓

Kendra

GenAI

↓

Bedrock

---

# Top Interview Questions

- ECS vs EKS?
- Lambda vs ECS?
- Aurora vs DynamoDB?
- RDS vs Aurora?
- SQS vs SNS?
- SNS vs EventBridge?
- Kinesis vs Kafka?
- ALB vs NLB?
- Security Group vs NACL?
- WAF vs Shield?
- Secrets Manager vs Parameter Store?
- CloudWatch vs CloudTrail?
- CloudTrail vs Config?
- Athena vs Redshift?
- Bedrock vs SageMaker?

---

# System Design Mapping

Notification System

↓

SNS

↓

SQS

↓

Lambda

Chat Application

↓

API Gateway

↓

ECS

↓

DynamoDB

↓

WebSocket

Video Upload

↓

S3

↓

Lambda

↓

CloudFront

Image Sharing

↓

CloudFront

↓

S3

↓

Lambda

E-commerce

↓

ALB

↓

ECS

↓

Aurora

↓

Redis

↓

SQS

↓

SNS

Logging Platform

↓

CloudWatch

↓

OpenSearch

Analytics

↓

Kinesis

↓

Glue

↓

Athena

↓

QuickSight

---

# Golden Rules

1. Prefer managed services.
2. Keep databases private.
3. Use IAM Roles.
4. Store secrets in Secrets Manager.
5. Encrypt using KMS.
6. Monitor with CloudWatch.
7. Audit with CloudTrail.
8. Use Multi-AZ.
9. Cache with Redis.
10. Use Auto Scaling.

---

# One-Line Revision

## Compute

EC2 = VM

Lambda = Serverless

ECS = Containers

EKS = Kubernetes

---

## Storage

S3 = Object

EBS = Block

EFS = Shared File

---

## Database

Aurora = SQL

DynamoDB = NoSQL

Redis = Cache

---

## Messaging

SQS = Queue

SNS = Pub/Sub

Kinesis = Streaming

MSK = Kafka

---

## Networking

Route53 = DNS

CloudFront = CDN

ALB = HTTP

NLB = TCP

---

## Security

IAM = Identity

KMS = Encryption

Secrets Manager = Secrets

WAF = Web Firewall

Shield = DDoS

---

## Monitoring

CloudWatch = Monitor

CloudTrail = Audit

Config = Compliance

---

## Analytics

Athena = SQL on S3

Redshift = Warehouse

Glue = ETL

QuickSight = BI

---

## AI

Textract = OCR

Lex = Chatbot

Rekognition = Vision

Bedrock = GenAI

SageMaker = ML

---

# Interview Strategy

For every AWS service answer:

1. What is it?
2. Why is it needed?
3. When would you use it?
4. When would you not use it?
5. What are the alternatives?
6. What are the trade-offs?
7. Give a real-world example.
8. Mention scaling.
9. Mention security.
10. Mention monitoring.

---

# Final Message

AWS interviews are not about memorizing 250+ services.

Focus on:
- Understanding the problem.
- Choosing the right service.
- Explaining trade-offs.
- Designing scalable and secure systems.
- Relating AWS concepts to your real backend experience.

Think like an architect, not just a service user.