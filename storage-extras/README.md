# AWS Storage Extras (Snow Family, Storage Gateway, DataSync, Transfer Family & Amazon FSx)

# Overview

AWS provides several specialized storage and data transfer services to help organizations move, synchronize, and access data between on-premises environments and AWS.

This section covers:

* AWS Snow Family
* AWS Storage Gateway
* AWS DataSync
* AWS Transfer Family
* Amazon FSx

These services are commonly used in hybrid cloud and enterprise migration scenarios.

---

# AWS Snow Family

Used to transfer large amounts of data to or from AWS when network transfer is slow or impractical.

Products:

* Snowcone
* Snowball Edge
* Snowmobile

---

## Snowcone

Small portable device.

Suitable for:

* Remote offices
* IoT
* Edge computing

Storage:

Approximately 8 TB.

---

## Snowball Edge

Portable appliance.

Suitable for:

* Data migration
* Local compute
* Edge workloads

Storage:

80–210 TB (varies by model).

---

## Snowmobile

Large truck carrying storage devices.

Used for:

Petabyte or Exabyte-scale migrations.

Example:

Migrating an enterprise data center.

---

# AWS Storage Gateway

Hybrid storage service connecting on-premises systems with AWS.

Types:

* File Gateway
* Volume Gateway
* Tape Gateway

---

## File Gateway

Provides file access using:

* NFS
* SMB

Files are stored in Amazon S3.

---

## Volume Gateway

Provides block storage.

Backed by Amazon EBS snapshots.

Suitable for:

* Databases
* Legacy applications

---

## Tape Gateway

Virtual tape library.

Used for replacing physical backup tapes.

Stores backups in S3 and Glacier.

---

# AWS DataSync

Managed service for transferring large datasets.

Supports:

* On-premises → AWS
* AWS → AWS
* NFS
* SMB
* EFS
* FSx
* S3

Benefits:

* Fast
* Secure
* Incremental synchronization

---

# AWS Transfer Family

Managed file transfer service.

Protocols:

* SFTP
* FTPS
* FTP

Backend Storage:

* S3
* EFS

Used when customers or partners require traditional file transfer protocols.

---

# Amazon FSx

Managed file systems for specialized workloads.

Available Options:

* FSx for Windows
* FSx for Lustre
* FSx for NetApp ONTAP
* FSx for OpenZFS

---

## FSx for Windows

Supports:

* SMB
* Active Directory

Suitable for:

Windows enterprise applications.

---

## FSx for Lustre

High-performance parallel file system.

Used for:

* Machine Learning
* HPC
* Analytics

---

# Comparison

| Service         | Purpose                     |
| --------------- | --------------------------- |
| Snow Family     | Physical Data Transfer      |
| Storage Gateway | Hybrid Storage              |
| DataSync        | Online Data Synchronization |
| Transfer Family | Managed SFTP/FTP            |
| FSx             | Managed File Systems        |

---

# Hands-On

* Explored Snow Family devices
* Configured Storage Gateway concepts
* Reviewed DataSync architecture
* Learned Transfer Family workflow
* Compared FSx offerings

---

# Best Practices

* Use Snow Family for massive offline migrations.
* Use DataSync for continuous synchronization.
* Use Storage Gateway for hybrid cloud.
* Use Transfer Family for SFTP/FTP requirements.
* Choose FSx based on workload requirements.

---

# Production Architecture

On-Premises

↓

Storage Gateway

↓

Amazon S3

↓

DataSync

↓

Amazon FSx

↓

Applications

Provides hybrid storage and migration capabilities.
