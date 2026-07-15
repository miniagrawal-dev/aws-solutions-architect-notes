# AWS Networking - VPC

# Overview

Amazon Virtual Private Cloud (VPC) allows you to create an isolated virtual network inside AWS where you can launch and manage AWS resources securely.

This section covers:

- VPC
- CIDR Blocks
- Public & Private Subnets
- Internet Gateway
- NAT Gateway
- Route Tables
- Security Groups
- Network ACLs
- Bastion Hosts
- VPC Peering
- VPC Endpoints
- Site-to-Site VPN
- Direct Connect
- Transit Gateway

---

# What is a VPC?

A VPC is your own private network inside AWS.

It allows you to control:

- IP Address Range
- Subnets
- Routing
- Internet Access
- Security
- Connectivity

---

# Basic VPC Architecture

Internet

↓

Internet Gateway

↓

Public Subnet

↓

Application Load Balancer

↓

Private Subnet

↓

ECS / EC2

↓

Private Subnet

↓

Aurora

Only the ALB is publicly accessible.

---

# CIDR Block

Defines IP range.

Example

10.0.0.0/16

Supports

65,536 IP addresses.

Example Subnets

10.0.1.0/24

10.0.2.0/24

10.0.3.0/24

---

# Public Subnet

Has route to Internet Gateway.

Used for:

- ALB
- Bastion Host
- NAT Gateway

---

# Private Subnet

No direct internet access.

Used for:

- ECS
- EC2
- RDS
- Redis

---

# Internet Gateway

Provides internet connectivity for public subnets.

Required for:

- Public EC2
- Public ALB

---

# NAT Gateway

Allows private subnet resources to access the internet without exposing them publicly.

Examples:

- Download OS updates
- Pull Docker images
- Access AWS APIs

---

# Route Tables

Control network traffic.

Example

Destination

0.0.0.0/0

↓

Internet Gateway

or

↓

NAT Gateway

---

# Security Groups

Instance-level firewall.

Features

- Stateful
- Allow rules only
- Attached to resources

---

# Network ACL (NACL)

Subnet-level firewall.

Features

- Stateless
- Allow and Deny rules
- Applies to entire subnet

---

# Security Group vs NACL

| Security Group | NACL |
|---------------|------|
| Stateful | Stateless |
| Instance Level | Subnet Level |
| Allow Only | Allow & Deny |

---

# Bastion Host

Jump server used to securely access private EC2 instances.

Internet

↓

Bastion Host

↓

Private EC2

---

# VPC Peering

Connects two VPCs.

Used when:

- Small environments
- Non-overlapping CIDR blocks

---

# Transit Gateway

Central hub connecting multiple VPCs.

Recommended for enterprise environments.

---

# VPC Endpoint

Connect privately to AWS services without using the internet.

Examples

Private EC2

↓

VPC Endpoint

↓

S3

---

# Site-to-Site VPN

Secure encrypted connection between on-premises data center and AWS VPC.

---

# AWS Direct Connect

Dedicated private network connection.

Provides:

- Lower latency
- Higher bandwidth
- Consistent performance

---

# Service Selection Guide

| Requirement | AWS Service |
|-------------|-------------|
| Private Network | VPC |
| Internet Access | Internet Gateway |
| Private Internet Access | NAT Gateway |
| Instance Firewall | Security Group |
| Subnet Firewall | NACL |
| Private AWS Access | VPC Endpoint |
| Connect Two VPCs | VPC Peering |
| Connect Many VPCs | Transit Gateway |
| On-Prem Connectivity | VPN / Direct Connect |

---

# Best Practices

- Place databases in private subnets.
- Deploy ALB in public subnets.
- Use NAT Gateway for outbound internet access.
- Use Security Groups as the primary firewall.
- Use multiple Availability Zones.
- Enable VPC Flow Logs.
- Use VPC Endpoints for S3 and DynamoDB.