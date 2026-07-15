# AWS IAM (Identity and Access Management)

## Overview

AWS IAM enables secure access control to AWS resources. It allows you to manage users, groups, roles, and permissions using policies.

## Problem It Solves

Without IAM, everyone would need to use the root account, creating security risks. IAM enables:

* Least privilege access
* Role-based access control
* Temporary credentials
* Cross-account access
* Secure access to AWS services

---

## Hands-On Lab

### Objective

Create an IAM user with S3 read-only access.

### Steps

1. Login to AWS Console
2. Navigate to IAM
3. Create User: `aws-demo-user`
4. Attach Policy:

   * AmazonS3ReadOnlyAccess
5. Generate Console Password
6. Login using IAM user
7. Verify access to S3
8. Attempt EC2 access (should fail)

### Outcome

Successfully restricted the user to read-only S3 access.

---

## IAM Components

### User

Represents a person or application.

Example:

* mini
* developer1

### Group

Collection of users.

Example:

* Developers
* Admins

### Policy

JSON document defining permissions.

### Role

Temporary permissions assumed by AWS services or users.

Example:

* EC2 accessing S3
* Lambda accessing DynamoDB

---

## Best Practices

* Never use root account for daily work
* Enable MFA
* Follow least privilege principle
* Use roles instead of access keys whenever possible
* Rotate credentials regularly

---

## Real World Example

An EC2 instance needs to read files from S3.

Instead of storing access keys inside the application:

1. Create IAM Role
2. Attach S3 Read Policy
3. Attach Role to EC2

EC2 automatically receives temporary credentials.

This is the recommended AWS approach.

---

## Services Frequently Using IAM

* EC2
* Lambda
* ECS
* EKS
* S3
* RDS
* CloudWatch
* API Gateway

---

## Architecture
                   AWS Account
                        |
        --------------------------------
        |              |              |
      Users          Groups         Roles
        |              |              |
     Developer      Developers     EC2 Role
        |              |              |
        --------------------------------
                        |
                    Policies
                        |
         -----------------------------
         |             |             |
      S3 Access     EC2 Access   RDS Access

## Key Learnings

* IAM controls authentication and authorization
* Policies define permissions
* Roles provide temporary credentials
* Groups simplify permission management
* Least privilege improves security
