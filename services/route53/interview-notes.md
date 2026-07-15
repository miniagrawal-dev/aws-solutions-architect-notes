# Route53 Interview Notes

# What is Route53?

AWS managed DNS service.

Converts domain names into IP addresses.

---

# Why Route53?

* Highly Available
* Global DNS
* Routing Policies
* Health Checks
* Domain Registration

---

# CNAME vs Alias

| CNAME                        | Alias                  |
| ---------------------------- | ---------------------- |
| Standard DNS                 | AWS Feature            |
| Cannot use Root Domain       | Works with Root Domain |
| Extra DNS Lookup             | No Extra Lookup        |
| Cannot point to ALB directly | Can point to ALB       |

---

# Routing Policies

Simple

Weighted

Latency

Failover

Geolocation

Multi-Value

---

# Interview Questions

## What happens when a user enters [www.company.com](http://www.company.com)?

Browser

↓

DNS Resolver

↓

Route53

↓

Returns ALB IP

↓

Browser connects to ALB

---

## Why use Alias instead of CNAME?

Alias supports AWS resources and root domains.

Recommended for ALB and CloudFront.

---

## When would you use Weighted Routing?

Canary deployment

Blue-Green deployment

A/B Testing

---

## When would you use Latency Routing?

Global applications with users in multiple continents.

---

## What is TTL?

Time DNS records stay cached.

Lower TTL:

Faster updates

Higher DNS queries

Higher TTL:

Better caching

Slower propagation

---

# Senior Backend Focus

Know:

* Alias vs CNAME
* Routing Policies
* Health Checks
* Global Applications
* Route53 + CloudFront + ALB architecture

---

# One-Line Revision

Route53 is AWS's managed DNS service that routes users to applications using intelligent routing policies and health checks.
