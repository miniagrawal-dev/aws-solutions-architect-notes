# Classic AWS Architecture Interview Notes

# Typical Production Architecture

Users

↓

Route53

↓

CloudFront

↓

Application Load Balancer

↓

Auto Scaling Group

↓

EC2

↓

Redis

↓

Aurora

↓

S3

---

# Why CloudFront?

* CDN
* Lower latency
* Cache static assets
* Reduce ALB traffic

---

# Why ALB?

* Load distribution
* SSL Termination
* Health Checks
* High Availability

---

# Why Auto Scaling?

Automatically adjusts EC2 instances based on demand.

---

# Why Redis?

Reduce database load.

Improve response time.

---

# Why Aurora?

Managed relational database with high availability and read scalability.

---

# Common Interview Questions

## Design a scalable e-commerce application.

Expected answer:

Route53

↓

CloudFront

↓

ALB

↓

Auto Scaling EC2

↓

Redis

↓

Aurora

↓

S3

---

## How do you achieve High Availability?

* Multi-AZ
* ALB
* Auto Scaling
* Aurora Multi-AZ
* Health Checks

---

## How do you reduce database load?

* Redis
* Read Replicas
* Cache-Aside Pattern

---

## How do you secure the architecture?

* IAM Roles
* Security Groups
* HTTPS
* ACM
* Secrets Manager
* Private Subnets

---

# Senior Backend Focus

Understand the purpose and trade-offs of every component instead of memorizing the diagram.

Be able to explain:

* Why this service?
* What problem does it solve?
* What happens if it fails?
* How does the system recover?

---

# One-Line Revision

A production AWS architecture combines Route53, CloudFront, ALB, Auto Scaling, EC2, Redis, Aurora, and S3 to build scalable, fault-tolerant, and highly available backend applications.
