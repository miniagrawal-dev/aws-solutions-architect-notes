# AWS Elastic Load Balancer (ELB)

## Overview

Elastic Load Balancer (ELB) automatically distributes incoming application traffic across multiple EC2 instances, improving availability, scalability, and fault tolerance.

Instead of users connecting directly to EC2 instances, they connect to the Load Balancer, which forwards requests to healthy instances.

---

# Why Load Balancer?

Without a Load Balancer:

* Single EC2 instance becomes a bottleneck.
* If the instance fails, the application becomes unavailable.
* Manual traffic distribution is required.

With a Load Balancer:

* Automatic traffic distribution
* High Availability
* Health Checks
* SSL Termination
* Seamless scaling with Auto Scaling Groups

---

# Types of AWS Load Balancers

## 1. Application Load Balancer (ALB)

Layer 7 (HTTP/HTTPS)

Supports:

* Host-based routing
* Path-based routing
* Microservices
* Web Applications
* WebSockets

Example:

api.company.com  → API Service

admin.company.com → Admin Service

/company/orders → Order Service

---

## 2. Network Load Balancer (NLB)

Layer 4 (TCP/UDP)

Features:

* Extremely low latency
* Millions of requests/sec
* Static IP support
* Handles sudden traffic spikes

Use Cases:

* Gaming
* Financial applications
* Real-time systems

---

## 3. Gateway Load Balancer (GWLB)

Used for deploying network virtual appliances.

Examples:

* Firewall
* IDS
* IPS

---

## Health Checks

ELB periodically checks whether EC2 instances are healthy.

Healthy instance:
Receives traffic

Unhealthy instance:
Traffic is automatically stopped until recovery.

Example Health Check:

HTTP GET /health

Expected Response:

200 OK

---

## Cross Zone Load Balancing

Without Cross Zone:

Traffic is distributed per Availability Zone.

With Cross Zone:

Traffic is evenly distributed across all healthy instances in every Availability Zone.

Improves resource utilization.

---

## Sticky Sessions

Allows a user to continue communicating with the same EC2 instance.

Implemented using cookies.

Useful for:

* Shopping carts
* Session-based applications

Avoid when applications are fully stateless.

---

## SSL/TLS Termination

Instead of configuring HTTPS on every EC2 instance:

Client → HTTPS

↓

Load Balancer

↓

HTTP/HTTPS

↓

EC2

Benefits:

* Simplified certificate management
* Reduced CPU usage on EC2

---

## Hands-On Completed

* Created Application Load Balancer
* Configured Target Group
* Registered EC2 Instances
* Configured Health Checks
* Enabled Cross-Zone Load Balancing
* Tested traffic distribution
* Integrated with Auto Scaling Group

---

## Real-World Architecture

Internet Users

↓

Route53

↓

Application Load Balancer

↓

Auto Scaling Group

↓

EC2 Instances

↓

RDS

↓

S3

---

## Best Practices

* Use ALB for HTTP/HTTPS applications.
* Use NLB for ultra-low latency TCP applications.
* Enable Health Checks.
* Enable Cross-Zone Load Balancing.
* Place Load Balancer in public subnets.
* Deploy EC2 instances across multiple Availability Zones.
* Combine ELB with Auto Scaling Groups.

---

## Key Learnings

* ELB improves High Availability.
* ALB is used for web applications.
* NLB is used for TCP/UDP workloads.
* Health Checks remove failed instances automatically.
* ELB integrates seamlessly with Auto Scaling.
