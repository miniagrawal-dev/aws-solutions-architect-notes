# AWS Security Interview Notes

# Encryption

At Rest

↓

Stored Data

In Transit

↓

HTTPS

TLS

Client Side

↓

Encrypt before upload

Server Side

↓

AWS encrypts

---

# KMS

Purpose

Manage encryption keys.

Used by

- S3
- Aurora
- DynamoDB
- EBS
- Secrets Manager

---

# KMS vs Secrets Manager

| KMS | Secrets Manager |
|------|-----------------|
| Encryption Keys | Secrets |
| Encrypts Data | Stores Passwords |
| Key Rotation | Secret Rotation |

---

# Secrets Manager vs Parameter Store

| Secrets Manager | Parameter Store |
|----------------|----------------|
| Secrets | Config |
| Auto Rotation | No Rotation |
| Paid | Standard tier free |
| KMS Encryption | Optional SecureString |

---

# WAF

Protects against

- SQL Injection
- XSS
- Bad Bots
- Rate Abuse

---

# Shield

Purpose

DDoS Protection.

Standard

↓

Automatic

Advanced

↓

Enterprise

---

# ACM

Provides SSL certificates.

Used with

- ALB
- CloudFront
- API Gateway

---

# Firewall Manager

Manage security policies across multiple AWS accounts.

---

# Common Interview Questions

### What is KMS?

AWS Key Management Service used to create and manage encryption keys for AWS services and applications.

---

### KMS vs Secrets Manager?

KMS manages encryption keys.

Secrets Manager securely stores and rotates credentials.

---

### Secrets Manager vs Parameter Store?

Use Secrets Manager for sensitive credentials with automatic rotation. Use Parameter Store for application configuration and less complex secret management.

---

### What is AWS WAF?

Protects web applications from common Layer 7 attacks such as SQL injection and cross-site scripting.

---

### WAF vs Shield?

WAF protects web applications from HTTP-based attacks.

Shield protects infrastructure from DDoS attacks.

---

### What is ACM?

Managed SSL/TLS certificate service with automatic renewal.

---

### Senior Backend Focus

Know

- Encryption at Rest
- Encryption in Transit
- KMS
- Secrets Manager
- Parameter Store
- ACM
- WAF
- Shield
- IAM Roles

---

# One-Line Revision

KMS manages encryption keys, Secrets Manager stores credentials, Parameter Store manages configuration, ACM provides certificates, WAF protects applications, and Shield mitigates DDoS attacks.