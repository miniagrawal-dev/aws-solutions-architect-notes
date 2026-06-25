# AWS Load Balancer - Interview Notes

# What is a Load Balancer?

A Load Balancer distributes incoming client requests across multiple backend servers (EC2 instances) to improve:

* High Availability
* Scalability
* Fault Tolerance
* Performance

Without a Load Balancer, all traffic goes to a single server, creating a single point of failure.

---

# Why do we need a Load Balancer?

Problems without Load Balancer:

* One server gets overloaded.
* Application goes down if EC2 crashes.
* Difficult to scale.
* Manual traffic distribution.

Benefits:

* Automatic traffic distribution
* Zero downtime deployments
* Health monitoring
* SSL termination
* High Availability

---

# Types of AWS Load Balancers

## 1. Application Load Balancer (ALB)

OSI Layer: 7

Protocols:

* HTTP
* HTTPS
* WebSocket
* HTTP/2

Supports:

* Host-based routing
* Path-based routing
* Redirects
* Authentication
* Microservices

Example:

api.company.com → API Service

admin.company.com → Admin Portal

/orders → Order Service

/users → User Service

Most commonly used for Spring Boot applications.

---

## 2. Network Load Balancer (NLB)

OSI Layer: 4

Protocols:

* TCP
* UDP
* TLS

Features:

* Static IP
* Millions of requests/sec
* Ultra-low latency

Use Cases:

* Gaming
* Financial Trading
* IoT
* High-performance APIs

---

## 3. Gateway Load Balancer (GWLB)

Used for network security appliances.

Examples:

* Firewall
* IDS
* IPS

---

# ALB vs NLB

| Feature      | ALB        | NLB                         |
| ------------ | ---------- | --------------------------- |
| OSI Layer    | Layer 7    | Layer 4                     |
| Protocol     | HTTP/HTTPS | TCP/UDP                     |
| Path Routing | ✅          | ❌                           |
| Host Routing | ✅          | ❌                           |
| Static IP    | ❌          | ✅                           |
| Latency      | Low        | Very Low                    |
| Best For     | Web Apps   | High-performance networking |

---

# Target Group

A Target Group contains backend resources that receive traffic.

Supported Targets:

* EC2
* IP Address
* Lambda

One Load Balancer can have multiple Target Groups.

---

# Health Checks

ELB periodically checks backend instances.

Healthy:
Receives traffic.

Unhealthy:
Automatically removed from rotation.

Example:

GET /health

Response:

200 OK

---

# Sticky Sessions

Also called Session Affinity.

Ensures the same client is routed to the same backend server.

Useful for:

* Shopping Cart
* Legacy Applications

Avoid for stateless microservices.

---

# Cross-Zone Load Balancing

Without Cross-Zone:

Traffic is balanced equally across Availability Zones.

Can overload one AZ if it has fewer instances.

With Cross-Zone:

Traffic is evenly distributed across every healthy instance.

Recommended for most applications.

---

# SSL Termination

HTTPS connection ends at the Load Balancer.

Flow:

Client (HTTPS)

↓

ALB

↓

EC2 (HTTP)

Benefits:

* Simpler certificate management
* Lower CPU usage on EC2
* Integrates with AWS Certificate Manager (ACM)

---

# Interview Questions

## Q1. Why use ALB instead of exposing EC2 directly?

Answer:

* Security
* High Availability
* Health Checks
* SSL Termination
* Auto Scaling Integration

---

## Q2. What happens if an EC2 instance crashes?

Answer:

The Health Check fails.

ALB marks the instance unhealthy.

Traffic automatically shifts to healthy instances.

Users experience little or no downtime.

---

## Q3. Why combine ALB with Auto Scaling?

Answer:

ALB distributes traffic.

Auto Scaling automatically launches or terminates EC2 instances based on demand.

Together they provide both scalability and availability.

---

## Q4. Difference between Security Group and Load Balancer?

Security Group:

Controls network access.

Load Balancer:

Distributes traffic.

They solve different problems.

---

## Q5. Can one ALB serve multiple applications?

Yes.

Using:

* Host-based routing
* Path-based routing

Example:

api.company.com

↓

API Service

admin.company.com

↓

Admin Portal

---

## Q6. Where should SSL certificates be installed?

Recommended:

On the Application Load Balancer using AWS Certificate Manager (ACM).

---

## Production Architecture

Users

↓

Route53

↓

CloudFront (Optional)

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

# Senior Backend Interview Focus

Be able to explain:

* Why ALB instead of Nginx?
* Why ALB + Auto Scaling?
* Health Checks
* Target Groups
* Sticky Sessions
* SSL Termination
* Blue/Green Deployments
* Rolling Deployments
* High Availability across Multiple Availability Zones

---

# One-Line Revision

ALB is a Layer 7 load balancer used for web applications. It distributes traffic across healthy EC2 instances, supports path/host-based routing, performs health checks, terminates SSL, and integrates with Auto Scaling to build highly available and scalable applications.
