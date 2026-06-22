# AWS EC2 (Elastic Compute Cloud)

## Overview

Amazon EC2 is AWS's Infrastructure as a Service (IaaS) offering that provides virtual servers in the cloud.

EC2 allows us to launch, manage, and scale virtual machines without maintaining physical hardware.

---

## Why EC2?

Before cloud computing:

* Buy physical servers
* Install operating systems
* Manage hardware failures
* Predict capacity requirements

With EC2:

* Provision servers in minutes
* Pay only for usage
* Scale up/down on demand
* Deploy applications globally

---

## Core Concepts

### AMI (Amazon Machine Image)

Template used to launch EC2 instances.

Contains:

* Operating System
* Software packages
* Configurations

Examples:

* Amazon Linux
* Ubuntu
* Windows Server

---

### Instance Types

Different CPU, memory, and storage combinations.

Examples:

| Type      | Use Case           |
| --------- | ------------------ |
| t2.micro  | Learning           |
| t3.medium | Small Applications |
| m5.large  | General Purpose    |
| c5.large  | Compute Intensive  |
| r5.large  | Memory Intensive   |

---

### Security Groups

Acts as a virtual firewall.

Controls:

* Inbound traffic
* Outbound traffic

Example:

Allow:

* SSH (22)
* HTTP (80)
* HTTPS (443)

---

### Key Pair

Used for SSH access.

Components:

* Public Key (stored in AWS)
* Private Key (.pem file)

Example:

ssh -i mykey.pem ec2-user@public-ip

---

### Elastic IP

Static public IPv4 address.

Benefits:

* Remains unchanged during instance restart
* Useful for fixed endpoints

Limitation:

* AWS encourages using Load Balancers instead

---

### User Data

Bootstrapping script executed during first launch.

Example:

* Install Java
* Install Docker
* Start application

---

## Storage Options

### EBS (Elastic Block Store)

Persistent storage.

Characteristics:

* Network attached
* Survives instance restart
* Can create snapshots

Use Cases:

* Databases
* Application data

---

### Instance Store

Temporary storage.

Characteristics:

* Very fast
* Lost when instance stops

Use Cases:

* Cache
* Temporary processing

---

## High Availability

### Placement Groups

Control physical placement of EC2 instances.

Types:

1. Cluster
2. Spread
3. Partition

Used for:

* Low latency
* Fault tolerance

---

## EC2 Purchasing Options

### On-Demand

Pay per usage.

Best For:

* Development
* Testing
* Unpredictable workloads

---

### Reserved Instances

Commitment:

* 1 Year
* 3 Years

Benefits:

* Significant cost savings

---

### Spot Instances

Unused AWS capacity.

Benefits:

* Up to 90% cheaper

Drawback:

* Can be terminated anytime

Use Cases:

* Batch processing
* Big data jobs

---

### Dedicated Hosts

Physical server dedicated to one customer.

Use Cases:

* Compliance
* Licensing requirements

---

## Hands-On Completed

* Launched EC2 instances
* Connected using SSH
* Configured Security Groups
* Created Elastic IP
* Used User Data scripts
* Created and attached EBS volumes
* Created EBS snapshots
* Learned EC2 purchasing models
* Explored Placement Groups

---

## Real World Example

Spring Boot Application Architecture

User
|
ALB
|
EC2 Auto Scaling Group
|
RDS Database

Benefits:

* High Availability
* Scalability
* Fault Tolerance

---

## Key Learnings

* EC2 provides virtual servers
* Security Groups act as firewalls
* EBS provides persistent storage
* Spot Instances reduce costs
* User Data automates provisioning
* Auto Scaling improves availability
