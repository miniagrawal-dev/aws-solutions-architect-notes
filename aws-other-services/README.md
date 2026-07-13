# AWS Other Services

# Overview

AWS offers many managed services that simplify governance, deployment, auditing, notifications, cost optimization, and application integration.

This section covers:

- AWS CloudFormation
- AWS Cloud Development Kit (CDK)
- AWS Systems Manager (SSM)
- AWS Config
- AWS Trusted Advisor
- AWS Organizations
- AWS Control Tower
- AWS License Manager
- AWS Service Catalog
- AWS Cloud Map
- AWS OpsWorks
- AWS AppConfig
- AWS Backup
- AWS Elastic Beanstalk

These services reduce operational overhead and help build production-ready cloud environments.

---

# AWS CloudFormation

Infrastructure as Code (IaC).

Defines AWS resources using YAML or JSON templates.

Example Resources

- VPC
- EC2
- RDS
- ECS
- IAM
- Lambda

Benefits

- Repeatable deployments
- Version control
- Automation

---

# AWS CDK

Cloud Development Kit.

Infrastructure is defined using programming languages.

Supported Languages

- Java
- TypeScript
- Python
- C#
- Go

CDK

↓

Generates

↓

CloudFormation Templates

---

# AWS Systems Manager (SSM)

Centralized management service.

Features

- Run Commands
- Session Manager
- Patch Manager
- Parameter Store
- Automation

Benefits

- No SSH required
- Secure instance management

---

# AWS Config

Tracks AWS resource configurations.

Answers questions like:

- Who changed this Security Group?
- When was this bucket made public?
- Is this resource compliant?

---

# AWS Trusted Advisor

Provides recommendations for:

- Cost Optimization
- Security
- Performance
- Fault Tolerance
- Service Limits

---

# AWS Organizations

Manage multiple AWS accounts.

Features

- Consolidated Billing
- Organizational Units
- Service Control Policies (SCP)
- Centralized Governance

---

# AWS Control Tower

Automates multi-account AWS setup.

Creates:

- Landing Zone
- Guardrails
- Governance

---

# AWS License Manager

Tracks software licenses.

Examples

- Microsoft SQL Server
- Windows Server
- Oracle

---

# AWS Service Catalog

Allows organizations to publish approved AWS resources.

Developers launch only approved infrastructure.

---

# AWS Cloud Map

Service discovery.

Applications automatically discover services by name.

Useful for:

- ECS
- Microservices
- Containers

---

# AWS OpsWorks

Configuration management service.

Supports

- Chef
- Puppet

Mostly used in legacy environments.

---

# AWS AppConfig

Safely deploy application configuration.

Examples

- Feature Flags
- Configuration Changes
- Rollback

---

# AWS Backup

Centralized backup management.

Supports

- EBS
- RDS
- DynamoDB
- EFS
- FSx

---

# AWS Elastic Beanstalk

Platform-as-a-Service.

Deploy applications without managing infrastructure.

Supports

- Java
- Python
- Node.js
- .NET
- PHP

---

# Service Selection Guide

| Requirement | AWS Service |
|-------------|-------------|
| Infrastructure as Code | CloudFormation |
| Infrastructure using Java | CDK |
| Instance Management | Systems Manager |
| Configuration Auditing | AWS Config |
| Best Practice Recommendations | Trusted Advisor |
| Multiple AWS Accounts | Organizations |
| Landing Zone | Control Tower |
| License Tracking | License Manager |
| Approved Infrastructure | Service Catalog |
| Service Discovery | Cloud Map |
| Configuration Management | OpsWorks |
| Runtime Configuration | AppConfig |
| Backup | AWS Backup |
| Easy App Deployment | Elastic Beanstalk |

---

# Best Practices

- Use Infrastructure as Code.
- Store infrastructure in Git.
- Use Systems Manager instead of SSH.
- Enable AWS Config in production.
- Review Trusted Advisor regularly.
- Centralize backups.
- Separate AWS accounts using Organizations.