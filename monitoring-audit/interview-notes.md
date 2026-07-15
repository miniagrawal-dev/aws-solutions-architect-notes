# AWS Monitoring & Audit Interview Notes

# CloudWatch

Purpose

Monitor AWS resources and applications.

Provides:

- Metrics
- Logs
- Dashboards
- Alarms

---

# Metrics

Examples

- CPU Utilization
- Memory Usage
- Request Count
- Error Rate
- Latency

---

# CloudWatch Logs

Stores:

- Spring Boot Logs
- Lambda Logs
- ECS Logs
- System Logs

Useful for debugging production issues.

---

# Dashboards

Visual representation of:

- CPU
- Memory
- Requests
- Errors

---

# Alarms

Monitor metrics.

Trigger:

SNS

↓

Email

↓

Lambda

↓

Auto Scaling

---

# CloudTrail

Records AWS API activity.

Examples

Who launched EC2?

Who deleted S3 bucket?

Who modified IAM policy?

---

# CloudTrail Event Types

Management Events

↓

Infrastructure Operations

Data Events

↓

S3 Objects

Lambda Invocations

Insights

↓

Detect unusual activity

---

# AWS Config

Tracks infrastructure configuration.

Examples

- Security Group changed
- Bucket became public
- IAM Policy modified

Supports compliance rules.

---

# CloudWatch vs CloudTrail

| CloudWatch | CloudTrail |
|-------------|------------|
| Metrics | API Logs |
| Monitoring | Auditing |
| Dashboards | Event History |

---

# CloudTrail vs Config

CloudTrail

↓

Who changed?

Config

↓

What changed?

---

# Common Interview Questions

### What is CloudWatch?

AWS monitoring and observability service that collects metrics, logs, dashboards, and alarms.

---

### What is CloudTrail?

Records AWS API activity for auditing and security.

---

### What is AWS Config?

Tracks configuration history and evaluates compliance of AWS resources.

---

### How do you monitor a Spring Boot application on AWS?

Application

↓

CloudWatch Logs

↓

CloudWatch Metrics

↓

Dashboard

↓

Alarm

---

### How do you investigate a deleted EC2 instance?

CloudTrail Event History.

---

### How do you know when a Security Group changed?

AWS Config timeline.

---

### Senior Backend Focus

Know:

- CloudWatch Metrics
- CloudWatch Logs
- Dashboards
- Alarms
- CloudTrail
- Config
- EventBridge integration

---

# One-Line Revision

CloudWatch monitors applications, CloudTrail audits AWS API activity, and AWS Config tracks infrastructure configuration changes.