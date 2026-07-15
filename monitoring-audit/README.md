# AWS Monitoring & Audit

# Overview

Monitoring and auditing are critical aspects of operating production systems on AWS. AWS provides managed services to collect metrics, logs, traces, configuration history, and API activity.

This section covers:

- Amazon CloudWatch
- AWS CloudTrail
- AWS Config

Together, these services help monitor application health, troubleshoot issues, audit API activity, maintain compliance, and improve operational visibility.

---

# Monitoring vs Logging vs Auditing

| Monitoring | Logging | Auditing |
|------------|----------|----------|
| Health & Metrics | Application Events | Who did What |
| CloudWatch Metrics | CloudWatch Logs | CloudTrail |
| CPU, Memory | Stack Traces | API Calls |

---

# Amazon CloudWatch

CloudWatch is AWS's monitoring and observability service.

It collects:

- Metrics
- Logs
- Events
- Dashboards
- Alarms

Supports monitoring for:

- EC2
- ECS
- Lambda
- RDS
- DynamoDB
- API Gateway
- ALB
- CloudFront
- Custom Applications

---

# CloudWatch Components

## Metrics

Numerical data collected over time.

Examples:

- CPU Utilization
- Memory Usage (Custom)
- Request Count
- Latency
- Network Traffic

---

## Logs

Stores application and infrastructure logs.

Examples:

- Spring Boot Logs
- Lambda Logs
- ECS Container Logs
- System Logs

---

## Dashboards

Visualize metrics.

Examples:

- CPU Usage
- API Latency
- Error Rate
- Request Count

---

## Alarms

Trigger actions when thresholds are crossed.

Examples:

CPU > 80%

↓

SNS Notification

↓

Operations Team

---

## Events / EventBridge

Automatically respond to AWS events.

Example

EC2 State Change

↓

EventBridge

↓

Lambda

---

# AWS CloudTrail

CloudTrail records AWS API activity.

Tracks:

- Console Login
- Resource Creation
- Resource Deletion
- IAM Changes
- Security Changes

Useful for:

- Auditing
- Compliance
- Security Investigation

---

# CloudTrail Events

Management Events

Examples:

- Create EC2
- Delete IAM User
- Modify Security Group

Data Events

Examples:

- S3 Object Access
- Lambda Invocation

Insights Events

Detect unusual API activity.

---

# AWS Config

Tracks resource configuration changes.

Records:

- Security Groups
- IAM
- S3
- EC2
- VPC
- RDS

Provides:

- Configuration History
- Compliance Evaluation
- Resource Timeline

---

# CloudWatch vs CloudTrail vs Config

| Service | Purpose |
|----------|----------|
| CloudWatch | Monitoring |
| CloudTrail | Audit API Activity |
| Config | Resource Configuration History |

---

# Service Selection Guide

| Requirement | AWS Service |
|-------------|-------------|
| Monitor CPU | CloudWatch |
| Store Logs | CloudWatch Logs |
| Create Alerts | CloudWatch Alarms |
| Audit API Calls | CloudTrail |
| Track Resource Changes | AWS Config |
| Compliance | AWS Config |
| Dashboard | CloudWatch Dashboard |

---

# Best Practices

- Enable CloudTrail in all AWS accounts.
- Store CloudTrail logs in S3.
- Enable CloudWatch Alarms for critical metrics.
- Send alarms to SNS.
- Monitor application logs using CloudWatch Logs.
- Enable AWS Config for compliance.
- Create dashboards for production systems.

---

# Hands-On Summary

- Created CloudWatch metrics
- Configured alarms
- Viewed application logs
- Explored CloudTrail event history
- Tracked configuration changes using AWS Config