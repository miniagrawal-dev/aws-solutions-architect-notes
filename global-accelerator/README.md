# AWS Global Accelerator

# Overview

AWS Global Accelerator is a networking service that improves the availability and performance of applications by routing user traffic through AWS's global private network instead of the public internet.

Unlike CloudFront, Global Accelerator does **not cache content**. Instead, it finds the optimal network path to your application.

---

# Why Global Accelerator?

Without Global Accelerator

User

↓

Public Internet

↓

Application

Problems:

* Variable latency
* Network congestion
* Packet loss
* Slower failover

With Global Accelerator

User

↓

Nearest AWS Edge Location

↓

AWS Global Network

↓

Application

Benefits:

* Lower latency
* Faster failover
* Improved availability
* Static Anycast IPs

---

# How It Works

Client

↓

Anycast IP Address

↓

Nearest AWS Edge Location

↓

AWS Global Network

↓

Regional Endpoint

↓

Application

Traffic stays on AWS's high-performance backbone for most of its journey.

---

# Supported Endpoints

Global Accelerator supports:

* Application Load Balancer (ALB)
* Network Load Balancer (NLB)
* EC2 Instances
* Elastic IP Addresses

---

# Anycast IP

Global Accelerator provides two static Anycast IP addresses.

Users connect to the nearest edge location using the same IP regardless of their geographic location.

Benefits:

* Static IP
* Simpler DNS management
* Faster routing

---

# Health Checks

Global Accelerator continuously monitors endpoint health.

If one region becomes unavailable:

Traffic is automatically redirected to another healthy region.

---

# Traffic Dial

Allows sending a percentage of traffic to a specific region.

Example:

US-East

80%

Europe

20%

Useful for:

* Blue/Green Deployments
* Canary Releases
* Disaster Recovery Testing

---

# Endpoint Groups

Endpoints are grouped by AWS Region.

Example:

Asia Endpoint Group

↓

Mumbai ALB

Singapore ALB

Europe Endpoint Group

↓

Frankfurt ALB

Ireland ALB

---

# Global Accelerator vs CloudFront

| CloudFront     | Global Accelerator   |
| -------------- | -------------------- |
| CDN            | Network Accelerator  |
| Caches Content | No Caching           |
| Static Content | Dynamic Applications |
| HTTP/HTTPS     | TCP/UDP              |
| Edge Cache     | AWS Global Network   |

---

# Hands-On

* Created Global Accelerator
* Added ALB Endpoint
* Configured Health Checks
* Tested Traffic Routing
* Configured Traffic Dial
* Simulated Regional Failover

---

# Best Practices

* Use CloudFront for static content.
* Use Global Accelerator for dynamic applications.
* Deploy applications in multiple regions.
* Enable Health Checks.
* Use Traffic Dial for gradual rollouts.
* Combine with Route53 when appropriate.

---

# Production Architecture

Users

↓

Global Accelerator

↓

AWS Global Network

↓

Regional ALBs

↓

ECS / EC2

↓

Aurora Global Database

↓

S3

This architecture provides low latency and regional failover for global users.
