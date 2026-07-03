# AWS ECS, Fargate, ECR & EKS Interview Notes

# What is Amazon ECR?

AWS managed Docker image registry.

Stores Docker images securely.

Used by ECS and EKS.

---

# What is ECS?

AWS managed container orchestration service.

Deploys and manages Docker containers.

Simpler than Kubernetes.

---

# ECS Components

Task Definition

↓

Task

↓

Service

↓

Cluster

---

# What is Fargate?

Serverless compute engine for containers.

No EC2 management.

AWS manages infrastructure.

Ideal for most modern applications.

---

# ECS EC2 vs Fargate

| ECS EC2         | Fargate               |
| --------------- | --------------------- |
| Manage EC2      | No EC2                |
| Lower Cost      | Higher Simplicity     |
| Greater Control | Less Operational Work |

---

# What is EKS?

AWS managed Kubernetes service.

Provides:

Managed Kubernetes Control Plane.

Compatible with standard Kubernetes.

---

# ECS vs EKS

Choose ECS when:

* AWS-only environment
* Smaller teams
* Simpler operations

Choose EKS when:

* Kubernetes already used
* Multi-cloud strategy
* Advanced Kubernetes features required

---

# What is a Task Definition?

Template describing container configuration.

Includes:

* Image
* CPU
* Memory
* Ports
* Environment Variables
* IAM Role

---

# What is an ECS Service?

Maintains desired number of Tasks.

Automatically replaces failed containers.

Supports rolling deployments.

---

# Common Interview Questions

## Why use containers?

Consistency across environments.

Faster deployments.

Simpler scaling.

Isolation.

---

## Why use ECR?

Secure image storage integrated with IAM and AWS services.

---

## Why choose Fargate?

No server management.

Ideal for teams wanting to focus on applications instead of infrastructure.

---

## Why choose ECS over Kubernetes?

Simpler.

Less operational overhead.

Tightly integrated with AWS.

---

## Why choose EKS?

Industry-standard Kubernetes.

Useful for hybrid or multi-cloud deployments.

---

## How does deployment work?

Developer

↓

Docker Build

↓

Push Image to ECR

↓

ECS Service pulls image

↓

Container starts

↓

ALB routes traffic

---

## How do containers access AWS services?

Using IAM Task Roles.

Never store AWS credentials inside containers.

---

## How do you deploy a new version?

Push new Docker image.

↓

Register new Task Definition Revision.

↓

Update ECS Service.

↓

Rolling Deployment.

No downtime.

---

# Senior Backend Interview Focus

Know these topics thoroughly:

* ECS Components
* Task Definition
* Service
* Cluster
* ECR
* ECS vs EKS
* Fargate vs EC2
* IAM Task Roles
* Rolling Deployment
* Blue/Green Deployment
* Container Health Checks
* ALB Integration

---

# One-Line Revision

Store Docker images in ECR, deploy them using ECS or EKS, and run them on EC2 or Fargate depending on the level of infrastructure management required.
