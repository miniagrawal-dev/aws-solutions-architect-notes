# AWS Storage Extras - Interview Notes

# What is AWS Snow Family?

Physical devices used for transferring very large datasets to or from AWS.

Used when network transfer is too slow.

---

# Snowcone vs Snowball vs Snowmobile

| Service    | Best For                    |
| ---------- | --------------------------- |
| Snowcone   | Small edge locations        |
| Snowball   | Large enterprise migrations |
| Snowmobile | Petabyte/Exabyte migrations |

---

# What is Storage Gateway?

Hybrid cloud storage service.

Allows on-premises applications to use AWS storage.

---

# Types of Storage Gateway

File Gateway

* NFS
* SMB

Volume Gateway

* Block Storage

Tape Gateway

* Backup replacement

---

# What is DataSync?

Managed data transfer service.

Supports incremental synchronization.

Much faster than manually copying files.

---

# What is AWS Transfer Family?

Managed SFTP, FTPS and FTP service.

Stores transferred files directly in:

* S3
* EFS

---

# What is Amazon FSx?

Managed file system.

Different versions exist for different workloads.

Examples:

* Windows File Server
* Lustre
* NetApp
* OpenZFS

---

# Common Interview Questions

## When should Snowball be used?

When transferring tens or hundreds of terabytes where internet transfer is impractical.

---

## Storage Gateway vs DataSync

Storage Gateway

Provides continuous hybrid storage access.

DataSync

Moves data between locations.

---

## Why use Transfer Family?

When customers require SFTP/FTP without managing file transfer servers.

---

## Why use FSx instead of EFS?

FSx provides specialized file systems for workloads like Windows, HPC, or enterprise storage.

---

# Senior Backend Focus

Know:

* Snow Family purpose
* Storage Gateway types
* DataSync use cases
* Transfer Family protocols
* FSx options
* Hybrid Cloud architecture

---

# One-Line Revision

Snow Family transfers large datasets physically, Storage Gateway connects on-premises storage to AWS, DataSync synchronizes data online, Transfer Family provides managed SFTP/FTP, and FSx offers specialized managed file systems.
