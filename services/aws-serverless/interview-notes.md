# AWS Serverless Interview Notes

# What is Serverless?

Serverless allows developers to run applications without managing infrastructure.

AWS provisions, scales, and maintains servers automatically.

---

# What is AWS Lambda?

AWS Lambda executes code in response to events.

Billing is based on:

* Number of requests
* Execution duration

---

# When should Lambda be used?

Good for:

* APIs
* Image Processing
* Scheduled Jobs
* File Processing
* Event Processing
* Automation

Avoid for:

* Long-running applications
* High-memory workloads
* Stateful applications

---

# What is API Gateway?

Managed API service that exposes REST and HTTP APIs.

Provides:

* Authentication
* Authorization
* Rate Limiting
* Request Validation
* Monitoring

---

# API Gateway vs Load Balancer

| API Gateway        | ALB                      |
| ------------------ | ------------------------ |
| Serverless APIs    | Traditional applications |
| Lambda Integration | EC2/ECS                  |
| Authentication     | Basic routing            |
| Rate Limiting      | No                       |

---

# What is EventBridge?

Managed event bus.

Routes events between AWS services.

Supports event filtering and scheduling.

---

# What are Step Functions?

Workflow orchestration service.

Coordinates multiple Lambda functions.

Supports:

* Retry
* Timeout
* Parallel Execution
* Error Handling

---

# Lambda Cold Start

First invocation may take longer because AWS initializes a new execution environment.

Reduce impact using:

* Provisioned Concurrency
* Smaller deployment packages
* Efficient runtime initialization

---

# Common Interview Questions

## Why choose Lambda over EC2?

No infrastructure management.

Automatic scaling.

Pay only for execution.

---

## Why not build everything using Lambda?

Limitations:

* Cold starts
* Execution time limits
* Stateless
* Unsuitable for long-running services

---

## When should you use ECS instead of Lambda?

Choose ECS when:

* Long-running Spring Boot applications
* Persistent connections
* Large memory requirements
* Full control over runtime

---

## How does API Gateway integrate with Lambda?

Client

↓

API Gateway

↓

Lambda

↓

Database

↓

Response

---

## How are secrets managed?

Do not store secrets in code.

Use:

* AWS Secrets Manager
* Systems Manager Parameter Store

---

## Senior Backend Interview Focus

Know these topics thoroughly:

* Lambda Lifecycle
* Cold Starts
* API Gateway
* Step Functions
* EventBridge
* Lambda Layers
* Environment Variables
* IAM Roles
* Serverless Security
* Monitoring with CloudWatch

---

# One-Line Revision

AWS Lambda executes event-driven code without managing servers, API Gateway securely exposes APIs, EventBridge routes events, and Step Functions orchestrate complex workflows.
