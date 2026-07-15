# AWS CloudFront

# Overview

Amazon CloudFront is AWS's Content Delivery Network (CDN) that delivers content to users with low latency and high transfer speeds by caching content at edge locations worldwide.

CloudFront can serve:

* Static websites
* Images
* Videos
* APIs
* Software downloads
* Dynamic content

---

# Why CloudFront?

Without CloudFront

User (India)

↓

US Server

↓

High Latency

↓

Slow Response

With CloudFront

User

↓

Nearest Edge Location

↓

Cached Content

↓

Fast Response

---

# CDN (Content Delivery Network)

A CDN stores cached copies of content at geographically distributed edge locations.

Benefits:

* Faster response time
* Reduced latency
* Lower origin server load
* Better user experience

---

# CloudFront Components

## Origin

The original source of content.

Can be:

* Amazon S3
* Application Load Balancer
* EC2
* API Gateway
* Custom HTTP Server

---

## Edge Locations

CloudFront servers distributed worldwide.

Requests are served from the nearest edge.

---

# Cache Behavior

CloudFront caches:

* Images
* CSS
* JavaScript
* Videos
* API Responses

Reduces repeated requests to the origin.

---

# TTL (Time To Live)

Defines how long objects remain cached.

Short TTL

* Fresh content
* More origin requests

Long TTL

* Better performance
* Lower origin cost

---

# Cache Invalidation

Used when cached content changes before TTL expires.

Example:

Updated logo.png

↓

Invalidate Cache

↓

Users receive latest version

---

# Signed URLs & Signed Cookies

Provide temporary access to private content.

Used for:

* Paid Videos
* Premium Documents
* Online Courses

---

# HTTPS Support

CloudFront integrates with AWS Certificate Manager (ACM).

Benefits:

* SSL termination
* Secure communication
* Easy certificate management

---

# CloudFront + S3

Users

↓

CloudFront

↓

S3

Common architecture for:

* Static websites
* Images
* Downloads

---

# CloudFront + ALB

Users

↓

CloudFront

↓

Application Load Balancer

↓

ECS / EC2

↓

Database

Suitable for dynamic applications.

---

# CloudFront + API Gateway

Users

↓

CloudFront

↓

API Gateway

↓

Lambda

Improves API performance globally.

---

# Hands-On

* Created CloudFront Distribution
* Configured S3 Origin
* Configured ALB Origin
* Tested Cache Hit
* Configured Cache Invalidation
* Configured HTTPS
* Explored Signed URLs

---

# Best Practices

* Cache static content aggressively.
* Use Origin Access Control (OAC) for S3.
* Enable HTTPS.
* Compress content.
* Use cache invalidation only when necessary.
* Monitor cache hit ratio.

---

# Production Architecture

Users

↓

CloudFront

↓

Application Load Balancer

↓

Auto Scaling

↓

Spring Boot

↓

Redis

↓

Aurora

↓

S3

CloudFront serves static assets while dynamic requests are forwarded to the backend.
