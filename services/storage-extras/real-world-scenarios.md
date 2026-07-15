# AWS Storage Extras - Real World Scenarios

# 1. Enterprise Data Center Migration

Company has 500 TB of data.

Internet transfer would take months.

Solution:

Snowball Edge

↓

AWS

Fast offline migration.

---

# 2. Hospital Hybrid Storage

Hospital stores medical images on-premises.

Doctors need cloud backups.

Solution:

Hospital Storage

↓

Storage Gateway

↓

Amazon S3

Provides seamless hybrid storage.

---

# 3. Daily File Synchronization

Company wants to synchronize files every night.

On-Premises NAS

↓

AWS DataSync

↓

Amazon S3

Only changed files are transferred.

---

# 4. Banking File Exchange

Business partners upload files using SFTP.

Partner

↓

AWS Transfer Family

↓

Amazon S3

↓

Processing Application

No SFTP server management required.

---

# 5. Windows File Server Migration

Existing Windows applications depend on SMB shares.

Windows Clients

↓

Amazon FSx for Windows

↓

Active Directory

Minimal application changes required.

---

# 6. High-Performance Computing

Research organization runs large simulations.

Compute Cluster

↓

Amazon FSx for Lustre

↓

S3

Provides very high throughput for parallel workloads.

---

# 7. Manufacturing Edge Location

Factory generates data in a remote location with poor internet connectivity.

Factory

↓

Snowcone

↓

AWS

Suitable for edge computing and remote sites.

---

# 8. Disaster Recovery

On-Premises Storage

↓

Storage Gateway

↓

S3

↓

Cross-Region Backup

↓

Recovery Environment

Supports business continuity.

---

# 9. Media Company

Editors upload video files using SFTP.

Transfer Family

↓

S3

↓

Media Processing Pipeline

↓

CloudFront

Delivers processed videos globally.

---

# 10. Enterprise Hybrid Cloud

Applications

↓

On-Premises NAS

↓

Storage Gateway

↓

S3

↓

DataSync

↓

FSx

Allows gradual cloud adoption without replacing existing infrastructure.

---

# Mapping to Your Experience

| Requirement             | AWS Service     |
| ----------------------- | --------------- |
| Large offline migration | Snowball        |
| Hybrid storage          | Storage Gateway |
| File synchronization    | DataSync        |
| Managed SFTP            | Transfer Family |
| Windows shared storage  | FSx for Windows |
| HPC storage             | FSx for Lustre  |

---

# Service Selection Guide

Need to migrate 300 TB with slow internet?

→ Snowball

Need continuous synchronization?

→ DataSync

Need SFTP for customers?

→ Transfer Family

Need hybrid file storage?

→ Storage Gateway

Need Windows file shares?

→ FSx for Windows

Need HPC file system?

→ FSx for Lustre

---

# Senior Backend Interview Questions

### Why choose DataSync over Snowball?

DataSync is for online, ongoing synchronization.

Snowball is for one-time large offline transfers.

---

### When would you choose Storage Gateway?

When applications remain on-premises but need cloud-backed storage.

---

### Why use Transfer Family?

To support existing SFTP/FTP workflows without maintaining file transfer servers.

---

### One-Line Revision

These services help bridge on-premises and AWS environments by enabling data migration, synchronization, hybrid storage, managed file transfer, and specialized file systems.
