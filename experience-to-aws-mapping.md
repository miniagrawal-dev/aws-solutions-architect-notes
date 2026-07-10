# Mapping My Experience to AWS

> This document maps my real-world experience at Walmart, Amazon, and Samsung to equivalent AWS services and common interview discussions.

---

# Career Summary

## Walmart

Role:
Senior Software Engineer

Worked On:

- Spring Boot Microservices
- Azure Cosmos DB
- Azure SQL
- IBM MQ
- Kafka
- OpenObserve
- Prometheus
- Grafana
- GitHub
- Docker
- CI/CD

---

## Amazon

Worked with:

- AWS
- Java
- Distributed Systems
- Backend Services

---

## Samsung

Worked on backend application development using Java technologies.

---

# Azure Services → AWS Equivalent

| Current Experience | AWS Equivalent |
|--------------------|----------------|
| Azure Cosmos DB | DynamoDB |
| Azure SQL | RDS / Aurora |
| Azure Blob Storage | S3 |
| Azure Service Bus | SQS / SNS |
| Azure Functions | Lambda |
| Azure Monitor | CloudWatch |
| Azure Key Vault | Secrets Manager |
| Azure Kubernetes Service | EKS |

---

# Messaging

## Current Experience

IBM MQ

Kafka

Azure Service Bus

### AWS Equivalent

IBM MQ

↓

Amazon MQ

Kafka

↓

Amazon MSK / Kinesis

Azure Service Bus Queue

↓

SQS

Azure Pub/Sub

↓

SNS

---

# Spring Boot APIs

Current

Spring Boot REST APIs

↓

Azure SQL

↓

Kafka

AWS Equivalent

Route53

↓

Application Load Balancer

↓

ECS Fargate

↓

Spring Boot

↓

Aurora

↓

Redis

↓

SQS

---

# Database Experience

Current

Azure SQL

↓

Relational Database

AWS

↓

Aurora PostgreSQL

or

Amazon RDS

---

# Cache

Current

(If Redis was used)

↓

Redis

AWS

↓

ElastiCache Redis

---

# Monitoring

Current

OpenObserve

Prometheus

Grafana

AWS

↓

CloudWatch

↓

CloudWatch Logs

↓

X-Ray

---

# CI/CD

Current

GitHub

↓

Docker

↓

Deployment

AWS

↓

GitHub Actions

↓

Docker

↓

ECR

↓

ECS

---

# Logging

Current

Application Logs

↓

OpenObserve

AWS

↓

CloudWatch Logs

↓

CloudWatch Dashboard

---

# File Storage

Current

Azure Blob Storage

AWS

↓

Amazon S3

---

# Security

Current

Application Secrets

↓

Azure Key Vault

AWS

↓

Secrets Manager

---

# Interview Questions

## Tell me about your current architecture.

Current

Users

↓

Load Balancer

↓

Spring Boot

↓

Azure SQL

↓

Kafka

↓

Cosmos DB

↓

Monitoring

AWS Equivalent

Users

↓

Route53

↓

Application Load Balancer

↓

ECS

↓

Aurora

↓

Redis

↓

SQS

↓

CloudWatch

---

## How would you migrate your application to AWS?

Current Stack

Azure SQL

↓

Aurora

Azure Blob

↓

S3

Azure Service Bus

↓

SQS/SNS

AKS

↓

EKS

Azure Monitor

↓

CloudWatch

---

## Explain asynchronous communication.

Current

IBM MQ

Kafka

↓

Producer

↓

Consumer

AWS

↓

SQS

↓

Worker

or

SNS

↓

Multiple Consumers

---

## Explain high availability.

Current

Multiple service instances behind a load balancer.

AWS

↓

ALB

↓

Auto Scaling

↓

Multi-AZ Aurora

---

## Explain caching.

Current

Reduce database load.

AWS

↓

Redis

↓

ElastiCache

---

## Explain monitoring.

Current

Prometheus

Grafana

↓

Metrics

AWS

↓

CloudWatch

↓

Alarms

↓

Dashboards

---

## Explain container deployment.

Current

Docker

↓

Deployment

AWS

↓

Docker

↓

ECR

↓

ECS

---
