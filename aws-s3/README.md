# AWS S3 (Simple Storage Service)

# Overview

Amazon S3 (Simple Storage Service) is AWS's highly durable, scalable object storage service used to store files such as images, videos, documents, backups, logs, and static website content.

S3 is designed for **11 9's (99.999999999%) durability** and can scale virtually without limits.

---

# Common Use Cases

* Image Storage
* Video Storage
* Application Backups
* Static Website Hosting
* Log Storage
* Data Lake
* Software Downloads
* Disaster Recovery
* Machine Learning Datasets

---

# S3 Basics

## Bucket

A container for storing objects.

Example:

company-images

user-documents

Bucket names must be globally unique.

---

## Object

Files stored inside a bucket.

Each object consists of:

* Key (filename)
* Value (actual data)
* Metadata
* Version ID (if enabled)

Example:

products/mobile.png

---

# Storage Classes

## Standard

* Frequently accessed data
* Lowest latency
* Highest availability

Examples:

Images

Videos

Web applications

---

## Intelligent-Tiering

AWS automatically moves data between storage tiers based on access patterns.

Best when access patterns are unpredictable.

---

## Standard-IA

Infrequent Access

Lower storage cost.

Higher retrieval cost.

Used for:

Backups

Monthly reports

---

## One Zone-IA

Stores data in a single Availability Zone.

Cheaper but lower availability.

---

## Glacier Instant Retrieval

Archive data that still requires fast retrieval.

---

## Glacier Flexible Retrieval

Minutes to hours retrieval.

Long-term archive.

---

## Glacier Deep Archive

Lowest cost.

Retrieval can take several hours.

Suitable for compliance and legal archives.

---

# Versioning

Stores multiple versions of an object.

Benefits:

* Recover deleted files
* Restore previous versions
* Protection against accidental overwrites

---

# Lifecycle Rules

Automatically move or delete objects based on age.

Example:

30 Days → Standard-IA

90 Days → Glacier

365 Days → Delete

Reduces storage costs.

---

# Replication

## Same Region Replication (SRR)

Replicate objects within the same region.

Used for:

Development

Testing

Compliance

---

## Cross Region Replication (CRR)

Replicate objects to another AWS region.

Used for:

Disaster Recovery

Global Applications

Compliance

Versioning must be enabled.

---

# Static Website Hosting

S3 can host static websites.

Suitable for:

HTML

CSS

JavaScript

Not suitable for dynamic backend applications.

---

# Presigned URLs

Generate temporary URLs for private objects.

Common use case:

Spring Boot generates a temporary upload URL.

Client uploads directly to S3.

Benefits:

* Reduces backend load
* Improves scalability

---

# Multipart Upload

Large files are uploaded in multiple parts.

Benefits:

* Faster uploads
* Retry only failed parts
* Parallel uploads

Recommended for files larger than 100 MB.

---

# S3 Encryption

## SSE-S3

AWS manages encryption keys.

---

## SSE-KMS

AWS KMS manages customer encryption keys.

Provides auditing and fine-grained access control.

---

## SSE-C

Customer provides encryption key.

AWS never stores the key.

---

## Client-Side Encryption

Application encrypts data before uploading.

Highest level of control.

---

# Bucket Policies

Resource-based policies attached to buckets.

Used to:

* Allow public access
* Grant cross-account access
* Restrict IP addresses

---

# Access Control

IAM Policies

Bucket Policies

ACLs (legacy)

Block Public Access (recommended)

---

# Event Notifications

S3 can trigger:

* Lambda
* SQS
* SNS

Example:

Image uploaded

↓

Lambda

↓

Generate Thumbnail

---

# Hands-On

* Created S3 Bucket
* Uploaded Objects
* Enabled Versioning
* Configured Lifecycle Rules
* Configured Bucket Policies
* Enabled Encryption
* Generated Presigned URLs
* Configured Cross Region Replication
* Triggered Lambda using S3 Events

---

# Best Practices

* Enable Versioning.
* Enable Server-Side Encryption.
* Enable Block Public Access.
* Use Lifecycle Rules.
* Use Presigned URLs for uploads.
* Avoid storing secrets in S3.
* Use IAM Roles instead of Access Keys.
* Monitor using CloudTrail and CloudWatch.

---

# Production Example

User uploads profile picture.

↓

Frontend requests Presigned URL.

↓

Spring Boot generates URL.

↓

Frontend uploads directly to S3.

↓

S3 Event triggers Lambda.

↓

Lambda resizes image.

↓

Thumbnail stored back in S3.

Benefits:

* Scalable
* Low backend load
* Secure
* Cost-effective
