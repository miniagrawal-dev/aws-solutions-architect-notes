# AWS Container Services (ECS, Fargate, ECR & EKS)

# Overview

AWS provides multiple services for building, deploying, and managing containerized applications.

This section covers:

* Amazon ECS
* AWS Fargate
* Amazon ECR
* Amazon EKS

These services simplify deploying Docker containers in production.

---

# Why Containers?

Traditional Deployment:

Application

↓

Install Java

↓

Install Dependencies

↓

Deploy JAR

Problems:

* Environment differences
* Dependency conflicts
* Difficult deployments

Container Deployment:

Application

↓

Docker Image

↓

Container

↓

Runs consistently everywhere

Benefits:

* Portable
* Reproducible
* Easy deployment
* Faster scaling

---

# Amazon ECR (Elastic Container Registry)

AWS managed Docker image repository.

Stores:

* Docker Images
* Container Images

Features:

* Private repositories
* Public repositories
* IAM integration
* Image scanning
* Lifecycle policies

Typical Flow:

Developer

↓

Docker Build

↓

Docker Push

↓

Amazon ECR

↓

ECS / EKS Pulls Image

---

# Amazon ECS (Elastic Container Service)

AWS managed container orchestration service.

Runs Docker containers without managing Kubernetes.

Components:

* Cluster
* Task Definition
* Task
* Service

---

## Task Definition

Blueprint describing:

* Docker image
* CPU
* Memory
* Ports
* Environment Variables

---

## Task

Running instance of a Task Definition.

Equivalent to:

Container Instance

---

## Service

Maintains desired number of running Tasks.

Automatically replaces failed Tasks.

Supports:

* Auto Scaling
* Load Balancer integration

---

# ECS Launch Types

## EC2 Launch Type

You manage EC2 instances.

Pros:

* Lower cost
* More control

Cons:

* Manage servers

---

## AWS Fargate

Serverless container platform.

No EC2 management.

AWS manages:

* Servers
* Scaling
* Patching

You manage only containers.

Benefits:

* Simpler operations
* Faster deployment
* Pay per usage

---

# ECS vs Fargate

| ECS EC2      | ECS Fargate          |
| ------------ | -------------------- |
| Manage EC2   | No Server Management |
| More Control | Fully Managed        |
| Lower Cost   | Easier Operations    |

---

# Amazon EKS (Elastic Kubernetes Service)

Managed Kubernetes service.

AWS manages:

* Kubernetes Control Plane

You manage:

* Worker Nodes (or use Fargate)

Ideal for organizations already using Kubernetes.

Supports:

* Helm
* kubectl
* Kubernetes APIs

---

# ECS vs EKS

| ECS             | EKS               |
| --------------- | ----------------- |
| AWS Native      | Kubernetes        |
| Easier          | More Complex      |
| Faster Learning | Industry Standard |
| AWS Only        | Multi-Cloud       |

---

# Typical Deployment Flow

Developer

↓

GitHub

↓

CI/CD Pipeline

↓

Docker Build

↓

Push Image to ECR

↓

ECS / EKS Deployment

↓

Application Load Balancer

↓

Users

---

# Hands-On

* Built Docker Image
* Created ECR Repository
* Pushed Docker Image
* Created ECS Cluster
* Created Task Definition
* Deployed ECS Service
* Explored AWS Fargate
* Created EKS Cluster
* Connected using kubectl

---

# Best Practices

* Store images in ECR.
* Use Fargate for serverless deployments.
* Use ECS for AWS-only workloads.
* Use EKS when Kubernetes expertise already exists.
* Scan Docker images.
* Avoid running containers as root.
* Use IAM Roles for Tasks.
* Use Auto Scaling.

---

# Production Architecture

Users

↓

Route53

↓

Application Load Balancer

↓

ECS Service (Fargate)

↓

Spring Boot Containers

↓

Aurora

↓

Redis

↓

S3

This architecture is fully managed, scalable, and highly available.
