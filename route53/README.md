# AWS Route 53

# Overview

Amazon Route 53 is AWS's highly available and scalable Domain Name System (DNS) service.

It is responsible for translating human-readable domain names into IP addresses.

Example:

[www.company.com](http://www.company.com)

↓

54.210.xxx.xxx

---

# Why Route 53?

Without DNS:

Users would have to remember IP addresses.

With Route 53:

* Human-friendly domain names
* Highly available DNS
* Global routing
* Health checks
* Traffic routing
* Domain registration

---

# Components

## Hosted Zone

Stores DNS records for a domain.

Example:

company.com

Contains:

* A Record
* AAAA Record
* CNAME
* Alias

---

## DNS Records

### A Record

Maps hostname to IPv4 address.

Example:

api.company.com

↓

52.14.10.20

---

### AAAA Record

Maps hostname to IPv6 address.

---

### CNAME

Maps one hostname to another hostname.

Example:

api.company.com

↓

backend.company.com

Cannot be used for root domains.

---

### Alias Record

AWS-specific feature.

Can point to:

* Application Load Balancer
* CloudFront
* S3 Static Website
* API Gateway

Unlike CNAME, Alias works for root domains.

---

# Routing Policies

## Simple Routing

Single resource.

---

## Weighted Routing

Traffic split by percentage.

Example:

90% → Version 1

10% → Version 2

Useful for canary deployments.

---

## Latency Routing

Routes users to the region with the lowest network latency.

Example:

India → Mumbai

Germany → Frankfurt

---

## Failover Routing

Primary

↓

Health Check

↓

Secondary

Used for Disaster Recovery.

---

## Geolocation Routing

Routes based on user location.

Example:

India → ap-south-1

Europe → eu-central-1

---

## Multi-Value Routing

Returns multiple healthy IP addresses.

Provides basic load distribution.

---

# Health Checks

Route53 continuously checks endpoints.

Healthy endpoint:

Traffic continues.

Unhealthy endpoint:

Traffic redirected to backup.

---

# Hands-On

* Registered domain
* Created Hosted Zone
* Added A Record
* Added CNAME
* Configured Alias Record
* Tested Routing Policies
* Created Health Checks

---

# Best Practices

* Use Alias for AWS resources.
* Use Health Checks for failover.
* Use Latency Routing for global applications.
* Use Weighted Routing for blue-green deployments.
* Keep TTL low during migrations.

---

# Real World Example

Users

↓

Route53

↓

CloudFront

↓

Application Load Balancer

↓

EC2 Auto Scaling

↓

Aurora

↓

Redis

This is a common production architecture.
