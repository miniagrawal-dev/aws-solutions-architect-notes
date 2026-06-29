# AWS Classic Solution Architecture

# Overview

This section combines multiple AWS services into production-ready architectures.

Goal:

Build scalable, highly available, secure applications.

---

# Basic Web Architecture

Users

↓

Route53

↓

Application Load Balancer

↓

Auto Scaling Group

↓

EC2

↓

RDS

---

# Highly Available Architecture

Users

↓

CloudFront

↓

ALB

↓

EC2 (AZ-1)

EC2 (AZ-2)

↓

Aurora Multi-AZ

Benefits:

* High Availability
* Fault Tolerance
* Horizontal Scaling

---

# Static Website

Users

↓

CloudFront

↓

S3

Benefits:

* Low Cost
* Global CDN
* Highly Available

---

# Dynamic Web Application

Users

↓

Route53

↓

CloudFront

↓

ALB

↓

EC2 Auto Scaling

↓

Redis

↓

Aurora

Benefits:

* Low latency
* Read scalability
* High Availability

---

# Disaster Recovery

Primary Region

↓

Multi-AZ

↓

Route53 Health Check

↓

Secondary Region

Automatic failover during outages.

---

# Security

IAM

Security Groups

NACL

HTTPS

ACM

Secrets Manager

Least Privilege

---

# Best Practices

* Never expose EC2 directly.
* Always use ALB.
* Use Multi-AZ databases.
* Cache using Redis.
* Use CloudFront for static assets.
* Enable Auto Scaling.
* Store secrets securely.

---

# Hands-On

* Designed production architecture
* Understood service integrations
* Reviewed scaling patterns
* Learned high availability principles
* Built fault-tolerant architecture
