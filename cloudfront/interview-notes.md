# CloudFront Interview Notes

# What is CloudFront?

AWS Content Delivery Network (CDN).

Caches content at edge locations worldwide.

Purpose:

Reduce latency.

Improve application performance.

---

# Why CloudFront?

Benefits:

* Faster content delivery
* Lower latency
* Reduced server load
* Better scalability
* Lower bandwidth cost

---

# What can CloudFront cache?

* Images
* CSS
* JavaScript
* Videos
* PDFs
* API Responses

---

# Origin Types

* S3
* ALB
* EC2
* API Gateway
* Custom Origin

---

# What is TTL?

Time cached objects remain at edge locations.

Higher TTL

↓

Better performance

↓

Less origin traffic

---

# Cache Invalidation

Used to remove outdated objects before TTL expires.

Example:

Updated image

↓

Invalidate

↓

Users receive new version

---

# Signed URLs

Temporary access to private content.

Examples:

* Netflix
* Udemy
* Online Courses

---

# Signed Cookies

Used when users need access to multiple protected files.

---

# CloudFront vs S3

| S3            | CloudFront            |
| ------------- | --------------------- |
| Storage       | CDN                   |
| Stores Files  | Caches Files          |
| Single Region | Global Edge Locations |

---

# CloudFront vs API Gateway

CloudFront

Optimizes delivery.

API Gateway

Handles API requests.

Often used together.

---

# Common Interview Questions

## Why use CloudFront?

To reduce latency and improve application performance.

---

## Why put CloudFront before ALB?

Reduce requests reaching backend servers.

Serve cached static content.

Improve global performance.

---

## Can CloudFront cache APIs?

Yes.

Useful for GET requests with cacheable responses.

---

## Why use Signed URLs?

Protect premium/private content.

---

## Senior Backend Focus

Know:

* CDN
* Edge Locations
* TTL
* Cache Invalidation
* Signed URLs
* OAC
* S3 Integration
* ALB Integration

---

# One-Line Revision

CloudFront is AWS's CDN that caches content globally, reducing latency, lowering origin load, and improving application performance.
