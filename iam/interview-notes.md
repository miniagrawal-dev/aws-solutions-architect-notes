
# AWS IAM Interview Notes

## What is IAM?

IAM (Identity and Access Management) is AWS's service for authentication and authorization.

Authentication:
Who are you?

Authorization:
What are you allowed to do?

---

## IAM Components

### User

Permanent identity.

Example:

* Developer
* Tester

### Group

Collection of users.

Used to assign permissions collectively.

### Policy

JSON document defining permissions.

### Role

Temporary permissions assumed by users or AWS services.

---

## IAM User vs Role

| User               | Role                                          |
| ------------------ | --------------------------------------------- |
| Permanent identity | Temporary identity                            |
| Has credentials    | No long-term credentials                      |
| Used by humans     | Used by AWS services and cross-account access |

---

## Why Prefer Roles?

Security.

Bad Practice:
Store AWS Access Key inside application.

Good Practice:
Attach IAM Role to EC2.

AWS automatically provides temporary credentials.

---

## IAM Policy Example

{
"Version":"2012-10-17",
"Statement":[
{
"Effect":"Allow",
"Action":"s3:GetObject",
"Resource":"*"
}
]
}

---

## What is Least Privilege?

Grant only the permissions required to perform a task.

Example:
Developer needs S3 read access.

Grant:
s3:GetObject

Do not grant:
s3:*

---

## What is MFA?

Multi-Factor Authentication.

Adds additional security layer beyond password.

Recommended for:

* Root Account
* Admin Users

---

## Interview Questions

Q: What is IAM?

A:
IAM is AWS's service for managing authentication and authorization through users, groups, roles, and policies.

---

Q: Difference between Authentication and Authorization?

A:
Authentication verifies identity.
Authorization determines permissions.

---

Q: Why use Roles instead of Access Keys?

A:
Roles provide temporary credentials, eliminate credential storage, and improve security.

---

Q: Can an EC2 instance access S3 without Access Keys?

A:
Yes. Attach an IAM Role with S3 permissions to the EC2 instance.

---

Q: What is an IAM Policy?

A:
A JSON document defining allowed or denied actions on AWS resources.

---

Q: What is the Principle of Least Privilege?

A:
Grant only the minimum permissions required to perform a task.

---

Real Interview Example

Question:
How would your Spring Boot application running on EC2 access S3?

Answer:
I would create an IAM Role with S3 permissions, attach it to the EC2 instance, and let AWS provide temporary credentials automatically instead of storing access keys in the application.
