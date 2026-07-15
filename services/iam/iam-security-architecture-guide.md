# IAM & Security Architecture Guide

> Production-grade IAM architecture and security design for AWS

---

# Security Principles

Every AWS architecture should follow:

- Least Privilege
- Defense in Depth
- Zero Trust
- Temporary Credentials
- Encryption Everywhere
- Audit Everything

---

# AWS Shared Responsibility

AWS

↓

Infrastructure

Networking

Hardware

Regions

Availability

Customer

↓

IAM

Application

OS (EC2)

Secrets

Encryption

Data

---

# IAM Architecture

Users

↓

IAM Identity Center (SSO)

↓

IAM Roles

↓

AWS Resources

Never give developers long-term Access Keys.

---

# Identity Types

IAM User

↓

Human

IAM Role

↓

Temporary Identity

AWS Service

↓

Service Role

Federated User

↓

Corporate Login

---

# IAM User vs Role

| IAM User | IAM Role |
|-----------|----------|
| Permanent | Temporary |
| Access Keys | STS Credentials |
| Human | Applications & AWS Services |
| Avoid for apps | Recommended |

Recommendation

Applications should always use IAM Roles.

---

# IAM Policy Types

Identity Policy

↓

Attached to

User

Group

Role

---

Resource Policy

↓

Attached to

S3

SQS

SNS

KMS

Lambda

---

Permission Boundary

↓

Maximum Permission Limit

---

Service Control Policy (SCP)

↓

Organizations

↓

Entire AWS Account

---

# IAM Evaluation

Request

↓

Explicit Deny?

↓

Yes

↓

Denied

↓

No

↓

Allowed?

↓

Yes

↓

Access Granted

---

# STS (Security Token Service)

Provides

Temporary Credentials

Used By

- IAM Roles
- Cross Account Access
- Federation

Benefits

- Short-lived
- Secure
- No stored credentials

---

# Cross Account Architecture

```

Account A

↓

Assume Role

↓

STS

↓

Temporary Credentials

↓

Account B

```

Use Cases

- CI/CD
- Central Security Account
- Shared Services

---

# ECS Security

```

Spring Boot

↓

ECS Task Role

↓

S3

↓

Aurora

↓

Secrets Manager

```

Never store

AWS_ACCESS_KEY

AWS_SECRET_KEY

Inside containers.

---

# Lambda Security

```

Lambda

↓

Execution Role

↓

S3

↓

DynamoDB

↓

CloudWatch

```

Lambda automatically receives temporary credentials.

---

# EC2 Security

```

EC2

↓

Instance Profile

↓

IAM Role

↓

AWS Services

```

No Access Keys.

---

# Secret Management

Application

↓

IAM Role

↓

Secrets Manager

↓

Database Password

Secrets never appear in

application.properties

---

# Parameter Store

Stores

- Configuration
- Feature Flags
- Environment Variables

Not recommended for rotating DB passwords.

---

# Encryption Architecture

Client

↓

HTTPS

↓

ALB

↓

Application

↓

KMS

↓

Aurora

↓

S3

Encryption

- In Transit
- At Rest

---

# KMS Architecture

```

Application

↓

KMS

↓

Encrypt

↓

S3

Aurora

EBS

Secrets Manager

```

---

# Cognito Architecture

Users

↓

Cognito

↓

JWT

↓

API Gateway

↓

Spring Boot

Used for

- Mobile Apps
- Web Apps

---

# Enterprise Authentication

Corporate User

↓

Azure AD

↓

SAML

↓

IAM Identity Center

↓

AWS Account

---

# Multi Account Security

```

AWS Organizations

↓

Production

↓

Development

↓

Testing

↓

Security Account

↓

Logging Account

```

Governed by

Service Control Policies

---

# Least Privilege

Example

Application needs

S3 Read

↓

Allow

s3:GetObject

Don't give

s3:*

---

# Resource Policy Example

S3 Bucket

↓

Only ECS Role

↓

Read Access

No Public Access

---

# Secure Spring Boot Architecture

```

Users

↓

CloudFront

↓

WAF

↓

ALB

↓

Spring Boot

↓

IAM Task Role

↓

Secrets Manager

↓

Aurora

↓

S3

↓

CloudTrail

↓

CloudWatch

```

---

# Cross Region Encryption

S3

↓

KMS

↓

Replication

↓

Destination Region

↓

Destination KMS Key

---

# Security Monitoring

CloudTrail

↓

CloudWatch

↓

SNS

↓

Security Team

---

# Production Checklist

✓ IAM Roles

✓ No Access Keys

✓ Least Privilege

✓ Secrets Manager

✓ KMS

✓ HTTPS

✓ WAF

✓ Shield

✓ CloudTrail

✓ Config

✓ CloudWatch

✓ MFA

✓ SSO

---

# Common Interview Questions

## Why IAM Role instead of IAM User?

IAM Roles provide temporary credentials and eliminate the need to store access keys.

---

## How do ECS containers access S3?

Using an IAM Task Role attached to the ECS Task Definition.

---

## How do Lambda functions access DynamoDB?

Using an Execution Role.

---

## Where should database passwords be stored?

AWS Secrets Manager.

---

## KMS vs Secrets Manager?

KMS manages encryption keys.

Secrets Manager stores credentials.

---

## Parameter Store vs Secrets Manager?

Parameter Store

↓

Configuration

Secrets Manager

↓

Credentials

↓

Automatic Rotation

---

## How do two AWS accounts communicate?

Using STS AssumeRole.

---

## How do you secure production?

- Private Subnets
- IAM Roles
- KMS
- Secrets Manager
- WAF
- Shield
- CloudTrail
- Config
- CloudWatch

---

# Common Mistakes

❌ Access Keys inside GitHub

❌ Access Keys inside Docker Images

❌ Public S3 Buckets

❌ AdminAccess everywhere

❌ No MFA

❌ Database Password in application.properties

---

# Senior Backend Tips

Always mention

IAM Roles

↓

Temporary Credentials

↓

Least Privilege

↓

Secrets Manager

↓

KMS

↓

CloudTrail

↓

CloudWatch

Interviewers expect this.

---

# One-Line Revision

Production AWS applications authenticate using **IAM Roles with temporary credentials**, store secrets in **Secrets Manager**, encrypt data using **KMS**, protect applications with **WAF and Shield**, and continuously audit activity using **CloudTrail**, **AWS Config**, and **CloudWatch**.