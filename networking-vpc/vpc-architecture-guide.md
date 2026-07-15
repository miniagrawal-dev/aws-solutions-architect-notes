# AWS VPC Architecture Guide

> Production-ready VPC architectures for Backend and System Design interviews.

---

# VPC Design Principles

A well-designed VPC should provide:

- High Availability
- Scalability
- Security
- Fault Tolerance
- Private Networking
- Least Privilege Access

Golden Rule

Never expose application servers or databases directly to the internet.

Only the Load Balancer should be public.

---

# Basic Three-Tier Architecture

```
                    Internet
                        │
                  Internet Gateway
                        │
        ┌────────────────────────────┐
        │      Public Subnets        │
        │                            │
        │  ALB (Multi-AZ)            │
        └────────────┬───────────────┘
                     │
      ┌──────────────┴──────────────┐
      │                             │
┌──────────────┐             ┌──────────────┐
│ Private AZ1  │             │ Private AZ2  │
│ ECS / EC2    │             │ ECS / EC2    │
└──────┬───────┘             └──────┬───────┘
       │                            │
       └──────────────┬─────────────┘
                      │
              Aurora Multi-AZ
                      │
                   ElastiCache
```

### Characteristics

- ALB in Public Subnets
- ECS in Private Subnets
- Aurora in Private Subnets
- Redis in Private Subnets

---

# Production Spring Boot Architecture

```
Users
   │
Route53
   │
CloudFront
   │
AWS WAF
   │
Application Load Balancer
   │
ECS (Spring Boot)
   │
Redis
   │
Aurora
   │
S3
```

### Why?

- CloudFront caches static assets
- WAF blocks malicious traffic
- ALB distributes requests
- ECS hosts backend services
- Redis caches data
- Aurora stores transactions

---

# Multi-AZ Architecture

```
               ALB
                │
     ┌──────────┴──────────┐
     │                     │
 Availability Zone A   Availability Zone B

 ECS Task             ECS Task

 Aurora Primary       Aurora Standby
```

Benefits

- High Availability
- Automatic Failover
- No Single Point of Failure

---

# Internet Access Architecture

```
Private ECS

↓

Route Table

↓

NAT Gateway

↓

Internet Gateway

↓

Internet
```

Use Cases

- Docker Image Pull
- Software Updates
- Calling External APIs

---

# Private AWS Access

```
Private ECS

↓

VPC Endpoint

↓

Amazon S3
```

Benefits

- No Internet
- Lower Latency
- Better Security

Use VPC Endpoints for:

- S3
- DynamoDB
- ECR
- CloudWatch
- Secrets Manager
- SSM

---

# Security Group Architecture

```
Internet

↓

ALB SG

↓

Application SG

↓

Database SG
```

Rules

ALB

↓

Port 443

↓

Application

Application

↓

5432

↓

Aurora

Aurora accepts traffic only from Application SG.

---

# Security Group vs NACL

Security Group

- Instance level
- Stateful
- Allow rules only

NACL

- Subnet level
- Stateless
- Allow & Deny

Recommendation

Use Security Groups for almost all application security.

Use NACLs for additional subnet protection.

---

# ECS Networking

```
Internet

↓

ALB

↓

ECS Service

↓

Task

↓

Aurora
```

Tasks receive ENIs and Security Groups.

---

# Microservices Architecture

```
ALB

↓

API Gateway

↓

Order Service

↓

Inventory Service

↓

Payment Service

↓

Notification Service
```

Communication

- REST
- Kafka
- SQS

All inside Private Subnets.

---

# Hybrid Cloud Architecture

```
Corporate Data Center

↓

Site-to-Site VPN

↓

AWS VPC
```

Best For

- Initial migration
- Enterprise connectivity

---

# Direct Connect Architecture

```
Corporate Data Center

↓

Direct Connect

↓

AWS Region
```

Advantages

- Dedicated network
- Low latency
- High bandwidth

Used by

- Banks
- Healthcare
- Financial institutions

---

# Multi-VPC Architecture

```
Transit Gateway

├── Development VPC

├── QA VPC

├── Production VPC

└── Shared Services VPC
```

Advantages

- Central routing
- Easy management
- Enterprise scale

---

# Bastion Host vs Session Manager

## Bastion Host

```
Admin

↓

Public EC2

↓

Private EC2
```

## Session Manager

```
Admin

↓

AWS Console

↓

SSM

↓

Private EC2
```

Recommendation

Prefer Session Manager.

No SSH.

No public IP.

---

# VPC Flow Logs

```
Network Traffic

↓

VPC Flow Logs

↓

CloudWatch

↓

Dashboard
```

Used For

- Troubleshooting
- Security Investigation
- Compliance

---

# Common Production Architecture

```
Users

↓

Route53

↓

CloudFront

↓

AWS WAF

↓

ALB

↓

Private ECS

↓

Redis

↓

Aurora

↓

S3 (VPC Endpoint)

↓

CloudWatch
```

---

# Interview Questions

### Why keep ECS in a private subnet?

Containers should never be directly accessible from the internet. Public traffic should terminate at the ALB.

---

### Why is Aurora in a private subnet?

To prevent direct internet access and reduce the attack surface.

---

### Why use NAT Gateway?

To allow outbound internet access while blocking inbound traffic.

---

### Why use VPC Endpoints?

To keep traffic to AWS services within the AWS network.

---

### Security Group vs NACL?

Security Groups are stateful instance-level firewalls.

NACLs are stateless subnet-level firewalls.

---

### VPC Peering vs Transit Gateway?

Use VPC Peering for a few VPCs.

Use Transit Gateway for enterprise environments with many VPCs.

---

# Production Checklist

✓ Multi-AZ deployment

✓ Public ALB only

✓ Private ECS

✓ Private Aurora

✓ Private Redis

✓ Security Groups

✓ NAT Gateway

✓ VPC Endpoints

✓ CloudWatch

✓ CloudTrail

✓ AWS Config

✓ WAF

✓ Shield

✓ Secrets Manager

✓ KMS Encryption

---

# Common Mistakes

❌ Placing databases in public subnets.

❌ Opening port 22 to the internet.

❌ Allowing 0.0.0.0/0 on database security groups.

❌ Hardcoding credentials.

❌ Not using Multi-AZ.

❌ Ignoring VPC Flow Logs.

---

# Senior Backend Tips

When explaining a VPC design:

1. Explain the subnet layout.
2. Describe traffic flow.
3. Justify why each component is public or private.
4. Explain Security Groups.
5. Mention NAT Gateway.
6. Mention VPC Endpoints.
7. Discuss monitoring and logging.
8. Explain high availability.
9. Mention disaster recovery.
10. Explain security best practices.

---

# One-Line Revision

A production-ready AWS VPC exposes only the load balancer to the internet while placing application servers, caches, and databases in private subnets protected by Security Groups, NAT Gateways, VPC Endpoints, and Multi-AZ deployment for security and high availability.