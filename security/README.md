# AWS Security Services

# Overview

Security is a shared responsibility between AWS and the customer. AWS provides multiple services for identity management, encryption, secret management, web application protection, DDoS mitigation, and compliance.

This section covers:

- AWS KMS
- AWS Secrets Manager
- AWS Systems Manager (Parameter Store)
- AWS Certificate Manager (ACM)
- AWS WAF
- AWS Shield
- AWS Firewall Manager
- Encryption Concepts
- Client-side vs Server-side Encryption

---

# AWS Shared Responsibility Model

AWS Responsibilities

- Physical Security
- Networking
- Hardware
- Data Centers
- Managed Services

Customer Responsibilities

- IAM Permissions
- Data Encryption
- Operating System (EC2)
- Application Security
- Network Configuration
- Secret Management

---

# Encryption Types

## Encryption at Rest

Data stored on disk is encrypted.

Examples

- S3
- EBS
- Aurora
- DynamoDB

Typically uses AWS KMS.

---

## Encryption in Transit

Data moving over a network.

Uses

HTTPS

TLS

SSL

Example

Browser

↓

HTTPS

↓

Application

---

## Client-side Encryption

Application encrypts data before sending to AWS.

Only the client can decrypt the data.

---

## Server-side Encryption

AWS encrypts the data after receiving it.

Examples

- SSE-S3
- SSE-KMS
- SSE-C

---

# AWS KMS

Key Management Service.

Purpose

Create and manage encryption keys.

Supports

- Customer Managed Keys (CMK)
- AWS Managed Keys
- Automatic Key Rotation
- IAM Integration
- CloudTrail Logging

Used by

- S3
- EBS
- Aurora
- Lambda
- Secrets Manager

---

# AWS Secrets Manager

Stores

- Database Passwords
- API Keys
- OAuth Tokens
- JWT Signing Keys

Features

- Automatic Rotation
- Encryption using KMS
- IAM Integration

Never store secrets inside source code.

---

# Systems Manager Parameter Store

Stores

- Configuration
- Environment Variables
- Feature Flags
- Secrets (basic)

Comparison

Parameter Store

↓

Simple

↓

Free

Secrets Manager

↓

Advanced

↓

Automatic Rotation

---

# AWS Certificate Manager (ACM)

Manages SSL/TLS certificates.

Used with

- ALB
- CloudFront
- API Gateway

Benefits

- Free certificates
- Automatic renewal

---

# AWS WAF

Web Application Firewall.

Protects against

- SQL Injection
- Cross-Site Scripting (XSS)
- IP Blocking
- Geo Blocking
- Rate Limiting

Works with

- CloudFront
- ALB
- API Gateway

---

# AWS Shield

Protects against DDoS attacks.

Shield Standard

Included for all AWS customers.

Shield Advanced

Additional protection and advanced monitoring.

---

# AWS Firewall Manager

Centralized management of:

- WAF Rules
- Shield Policies
- Security Policies

Useful for organizations with multiple AWS accounts.

---

# Security Architecture

Users

↓

CloudFront

↓

AWS WAF

↓

Shield

↓

ALB

↓

Spring Boot

↓

Secrets Manager

↓

Aurora (KMS)

↓

S3 (KMS)

---

# Service Selection Guide

| Requirement | AWS Service |
|-------------|-------------|
| Encryption Keys | KMS |
| Secrets | Secrets Manager |
| Configuration | Parameter Store |
| SSL Certificates | ACM |
| Web Firewall | WAF |
| DDoS Protection | Shield |
| Central Security Policies | Firewall Manager |

---

# Best Practices

- Enable encryption at rest.
- Enforce HTTPS.
- Store secrets in Secrets Manager.
- Rotate encryption keys.
- Use IAM Roles instead of access keys.
- Enable CloudTrail.
- Enable WAF for internet-facing applications.
- Use Shield for DDoS protection.