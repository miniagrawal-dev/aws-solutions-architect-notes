# AWS Other Services Interview Notes

# CloudFormation vs CDK

| CloudFormation | CDK |
|----------------|-----|
| YAML/JSON | Java, TypeScript, Python |
| Declarative | Programming Language |
| Native IaC | Generates CloudFormation |

Choose CDK if your team prefers writing infrastructure in code.

---

# Systems Manager

Purpose

Manage EC2 instances without SSH.

Common Features

- Session Manager
- Patch Manager
- Parameter Store
- Run Command

---

# AWS Config

Tracks resource configuration history.

Useful for

- Compliance
- Auditing
- Governance

---

# Trusted Advisor

Checks

- Cost
- Security
- Performance
- Fault Tolerance

---

# Organizations

Used for

- Multiple AWS Accounts
- Central Billing
- Security Policies

---

# Control Tower

Creates enterprise-ready AWS environments.

Ideal for large organizations.

---

# AppConfig

Safely deploys configuration changes.

Supports gradual rollout and rollback.

---

# AWS Backup

Central backup service.

Supports multiple AWS services using one backup policy.

---

# Elastic Beanstalk

Simplifies deployment.

AWS manages

- EC2
- Load Balancer
- Auto Scaling

Developer uploads application.

---

# Common Interview Questions

### CloudFormation vs CDK?

CloudFormation uses templates.

CDK allows developers to define infrastructure using programming languages.

---

### Why Systems Manager instead of SSH?

More secure.

Auditable.

No inbound SSH ports.

---

### What is AWS Config?

Tracks resource changes and evaluates compliance.

---

### Why Trusted Advisor?

To improve cost, security, and reliability.

---

### What is AWS Organizations?

Centralized management for multiple AWS accounts.

---

### Why AppConfig?

To deploy configuration changes without redeploying applications.

---

### Senior Backend Focus

Know:

- CloudFormation
- CDK
- Systems Manager
- AWS Config
- Organizations
- AppConfig
- Backup