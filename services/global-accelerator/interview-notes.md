# AWS Global Accelerator Interview Notes

# What is Global Accelerator?

AWS networking service that routes traffic through AWS's global network to improve performance and availability.

It does not cache content.

---

# Why use Global Accelerator?

Benefits:

* Lower latency
* Static IP addresses
* Better network performance
* Regional failover
* Improved availability

---

# How is it different from CloudFront?

CloudFront

* CDN
* Caches content
* Best for static assets

Global Accelerator

* Networking service
* No caching
* Best for dynamic applications

---

# What is Anycast IP?

A single static IP advertised from multiple AWS edge locations.

Users automatically connect to the nearest edge location.

---

# What are Endpoint Groups?

Logical grouping of endpoints in a specific AWS Region.

Allows traffic control by region.

---

# What is Traffic Dial?

Controls the percentage of traffic sent to a region.

Useful for:

* Canary Deployment
* Blue/Green Deployment
* Disaster Recovery

---

# Health Checks

Global Accelerator monitors endpoint health.

If an endpoint becomes unhealthy:

Traffic is automatically redirected.

---

# Common Interview Questions

## When would you use CloudFront?

For static content:

* Images
* CSS
* JavaScript
* Videos

---

## When would you use Global Accelerator?

For dynamic applications:

* Gaming
* Banking
* APIs
* Real-time applications

---

## Can Global Accelerator cache files?

No.

It only optimizes network routing.

---

## Does Global Accelerator replace Route53?

No.

Route53 resolves DNS.

Global Accelerator improves network routing.

---

## Senior Backend Focus

Know:

* Anycast IP
* Health Checks
* Endpoint Groups
* Traffic Dial
* Global Failover
* CloudFront vs Global Accelerator
* Multi-Region Architecture

---

# One-Line Revision

Global Accelerator improves application availability and network performance by routing traffic through AWS's global backbone using static Anycast IP addresses.
