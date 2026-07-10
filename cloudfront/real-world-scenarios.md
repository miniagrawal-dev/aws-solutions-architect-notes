# CloudFront Real World Scenarios

# 1. E-Commerce Website

Users

↓

CloudFront

↓

S3 (Images)

↓

ALB

↓

Spring Boot

↓

Aurora

Product images are cached globally.

---

# 2. Video Streaming

Videos

↓

S3

↓

CloudFront

↓

Users

Low latency streaming.

---

# 3. Online Learning Platform

Videos

↓

CloudFront

↓

Signed URLs

↓

Students

Only enrolled users access videos.

---

# 4. Global REST API

Users

↓

CloudFront

↓

API Gateway

↓

Lambda

↓

Database

Lower API latency worldwide.

---

# 5. Static Website Hosting

CloudFront

↓

S3

↓

Users

Very low-cost architecture.

---

# 6. Software Downloads

Windows Installer

↓

S3

↓

CloudFront

↓

Global Users

Fast download speed.

---

# 7. News Website

Images

↓

CloudFront Cache

↓

S3

↓

Users

Millions of requests served without overloading origin.

---

# Mapping to Your Experience

Spring Boot

↓

CloudFront

↓

ALB

↓

ECS

↓

Redis

↓

Aurora

Used to accelerate static assets while backend APIs remain dynamic.

---

# Common Design Patterns

Cache-Aside

Static Asset Caching

Edge Caching

HTTPS Offloading

Private Content Delivery

---

# Senior Interview Questions

Why CloudFront instead of only ALB?

How does TTL affect performance?

When should cache invalidation be used?

How do Signed URLs protect content?

---

# One-Line Revision

CloudFront improves global application performance by caching content at edge locations and reducing requests to backend servers.
