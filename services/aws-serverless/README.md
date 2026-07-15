# AWS Serverless (Lambda, API Gateway & Step Functions)

# Overview

Serverless computing allows developers to build applications without managing servers. AWS automatically provisions infrastructure, scales resources, and charges only for actual usage.

This section covers:

* AWS Lambda
* API Gateway
* Step Functions
* EventBridge
* Serverless Architectures

---

# Why Serverless?

Traditional Architecture:

Users

↓

EC2

↓

Application

Problems:

* Manage servers
* Auto Scaling
* Patching
* Idle cost

Serverless:

Users

↓

API Gateway

↓

Lambda

↓

Database

Benefits:

* No server management
* Automatic scaling
* Pay per execution
* Faster development

---

# AWS Lambda

Lambda is AWS's serverless compute service.

Runs code in response to events.

Supports:

* Java
* Python
* Node.js
* Go
* C#
* Ruby

AWS manages:

* Servers
* Scaling
* Availability
* Patching

---

# Lambda Invocation

Event

↓

Lambda Function

↓

Business Logic

↓

Response

Lambda can be triggered by:

* API Gateway
* S3
* SQS
* SNS
* EventBridge
* DynamoDB Streams
* CloudWatch Events

---

# API Gateway

Managed service to expose REST APIs and HTTP APIs.

Responsibilities:

* Authentication
* Authorization
* Rate Limiting
* Request Validation
* Routing
* Monitoring

Flow:

Client

↓

API Gateway

↓

Lambda

↓

Database

---

# Lambda Layers

Reusable code shared across multiple Lambda functions.

Example:

Logging Library

JWT Library

Common Utilities

---

# Lambda Environment Variables

Store:

* Configuration
* Database URL
* API Keys

Sensitive values should be stored in Secrets Manager or Parameter Store.

---

# AWS Step Functions

Workflow orchestration service.

Coordinates multiple Lambda functions.

Example:

Order Processing

↓

Payment

↓

Inventory

↓

Shipping

↓

Email

Provides retries, branching, waiting, and error handling.

---

# Amazon EventBridge

Event bus for event-driven architectures.

Publisher

↓

EventBridge

↓

Lambda

↓

SNS

↓

SQS

↓

Step Functions

Used for decoupled systems.

---

# Serverless Benefits

* No infrastructure management
* Automatic scaling
* High availability
* Pay only when executed
* Rapid development

---

# Limitations

* Cold starts
* Execution timeout
* Stateless
* Memory limits
* Vendor lock-in

---

# Hands-On

* Created Lambda Function
* Invoked Lambda
* Created API Gateway
* Connected API Gateway to Lambda
* Configured Environment Variables
* Created Step Function
* Created EventBridge Rule
* Triggered Lambda using events

---

# Best Practices

* Keep Lambda functions small.
* Make functions stateless.
* Use IAM Roles.
* Store secrets in Secrets Manager.
* Minimize cold starts.
* Use Provisioned Concurrency if required.
* Use CloudWatch Logs.

---

# Production Architecture

Users

↓

CloudFront

↓

API Gateway

↓

Lambda

↓

Aurora / DynamoDB

↓

S3

↓

CloudWatch

Suitable for event-driven and low-maintenance applications.
