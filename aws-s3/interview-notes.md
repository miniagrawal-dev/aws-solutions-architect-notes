# AWS S3 Interview Notes

# What is Amazon S3?

Amazon S3 is AWS's highly durable object storage service used for storing and retrieving files at virtually unlimited scale.

---

# Why use S3 instead of EC2 Storage?

S3:

* Durable
* Highly Available
* Unlimited Storage
* Low Cost
* Managed Service

EC2 Storage:

* Limited
* Instance dependent
* Harder to scale

---

# S3 vs EBS

| S3               | EBS                         |
| ---------------- | --------------------------- |
| Object Storage   | Block Storage               |
| Unlimited Scale  | Attached to EC2             |
| Accessed via API | Mounted as Disk             |
| Stores Files     | Stores File System/Database |

---

# What is Versioning?

Stores multiple versions of the same object.

Benefits:

* Recover deleted files
* Restore previous versions
* Prevent accidental overwrite

---

# What are Lifecycle Rules?

Automatically transition objects between storage classes or delete them after a defined period.

Used to optimize storage costs.

---

# Storage Classes

Standard

Frequently accessed data.

Standard-IA

Infrequently accessed data.

Intelligent-Tiering

Automatically optimizes costs.

Glacier

Long-term archive.

Deep Archive

Lowest-cost archival storage.

---

# What is Cross Region Replication?

Automatically copies objects to another AWS region.

Requirements:

* Versioning enabled
* IAM permissions

Use Cases:

* Disaster Recovery
* Compliance
* Global applications

---

# What are Presigned URLs?

Temporary URLs allowing secure access to private objects.

Common use cases:

* File upload
* File download

Avoid exposing AWS credentials to clients.

---

# Bucket Policy vs IAM Policy

IAM Policy

Attached to users, groups, or roles.

Bucket Policy

Attached directly to the bucket.

Both control access but operate at different scopes.

---

# What is Block Public Access?

AWS feature preventing accidental public exposure of S3 buckets.

Should remain enabled unless public access is explicitly required.

---

# S3 Encryption

SSE-S3

AWS-managed keys.

SSE-KMS

KMS-managed keys with auditing.

SSE-C

Customer-managed keys.

Client-side Encryption

Application encrypts data before upload.

---

# Common Interview Questions

## Why use Presigned URLs?

To allow clients to upload/download files directly to S3 without exposing AWS credentials or routing files through the backend.

---

## How do you secure S3?

* IAM Roles
* Bucket Policies
* Block Public Access
* Server-Side Encryption
* Versioning
* CloudTrail
* Least Privilege

---

## How would you reduce storage cost?

* Lifecycle Rules
* Intelligent-Tiering
* Glacier
* Delete unused objects

---

## What happens if an object is accidentally deleted?

If Versioning is enabled:

Restore previous version.

Otherwise:

Recover from backup if available.

---

## How would you design an image upload service?

Client

↓

Spring Boot API

↓

Generate Presigned URL

↓

Client uploads directly to S3

↓

S3 Event

↓

Lambda

↓

Resize Image

↓

Store Thumbnail

---

## When would you use S3 instead of a database?

Use S3 for unstructured binary data:

* Images
* Videos
* PDFs
* Documents
* Backups
* Logs

Use databases for structured relational or transactional data.

---

# Senior Backend Interview Focus

Know these topics thoroughly:

* S3 vs EBS vs EFS
* Versioning
* Lifecycle Rules
* Storage Classes
* Bucket Policy vs IAM Policy
* Presigned URLs
* SSE-S3 vs SSE-KMS
* Cross Region Replication
* Multipart Upload
* Event Notifications
* Block Public Access

---

# One-Line Revision

Amazon S3 is AWS's scalable object storage service used for securely storing files, optimizing storage costs, enabling disaster recovery, and integrating with serverless workflows through events and presigned URLs.
