# AWS VPC Interview Notes

# Public vs Private Subnet

Public Subnet

- Route to Internet Gateway
- Public IP
- Internet Accessible

Private Subnet

- No Internet Gateway route
- No Public IP
- Internal Resources

---

# Internet Gateway vs NAT Gateway

| Internet Gateway | NAT Gateway |
|------------------|-------------|
| Public Internet | Outbound Only |
| Public Subnet | Public Subnet |
| Incoming + Outgoing | Outgoing Only |

---

# Security Group

Acts as a virtual firewall.

Characteristics

- Stateful
- Allow rules only
- Resource level

---

# Network ACL

Subnet firewall.

Characteristics

- Stateless
- Allow and Deny
- Evaluated in order

---

# Security Group vs NACL

Security Group

↓

Instance

NACL

↓

Subnet

---

# Bastion Host

Purpose

SSH into private EC2 instances securely.

Modern alternative

AWS Systems Manager Session Manager.

---

# VPC Endpoint

Purpose

Private access to AWS services.

Example

EC2

↓

VPC Endpoint

↓

S3

No internet required.

---

# VPC Peering vs Transit Gateway

VPC Peering

- One-to-one connection
- Simpler
- Small environments

Transit Gateway

- Hub-and-spoke
- Many VPCs
- Enterprise scale

---

# VPN vs Direct Connect

VPN

- Internet
- Encrypted
- Lower Cost

Direct Connect

- Dedicated Line
- Private Network
- Lower Latency

---

# Common Interview Questions

### What is a VPC?

A logically isolated virtual network in AWS where resources are deployed securely.

---

### Public vs Private Subnet?

Public subnets have a route to an Internet Gateway.

Private subnets do not.

---

### Why is RDS deployed in a private subnet?

To prevent direct internet access and improve security.

---

### Security Group vs NACL?

Security Groups are stateful instance-level firewalls.

NACLs are stateless subnet-level firewalls.

---

### Why use a NAT Gateway?

To allow private resources to access the internet for updates while remaining inaccessible from the internet.

---

### VPC Peering vs Transit Gateway?

Use VPC Peering for a small number of VPCs.

Use Transit Gateway for large enterprise networks.

---

### Senior Backend Focus

Know

- Public vs Private Subnets
- NAT Gateway
- Security Groups
- NACL
- Route Tables
- VPC Endpoints
- VPC Flow Logs
- Transit Gateway

---

# One-Line Revision

A secure AWS architecture places internet-facing components in public subnets and application and database resources in private subnets protected by Security Groups and route tables.