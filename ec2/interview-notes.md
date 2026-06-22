# EC2 Interview Notes

## What is EC2?

Amazon EC2 is AWS's virtual machine service that provides scalable compute capacity in the cloud.

---

## What is an AMI?

AMI (Amazon Machine Image) is a template used to launch EC2 instances.

Contains:

* OS
* Application software
* Configuration

---

## What is the difference between AMI and EC2 Instance?

AMI:

* Template

EC2:

* Running virtual machine created from AMI

---

## What is a Security Group?

Virtual firewall controlling inbound and outbound traffic.

Characteristics:

* Stateful
* Allow rules only
* Attached to EC2 instances

---

## NACL vs Security Group

Security Group:

* Instance level
* Stateful

NACL:

* Subnet level
* Stateless

---

## What is User Data?

Script executed during instance launch.

Example:

* Install Java
* Install Docker
* Deploy Spring Boot application

---

## What is EBS?

Elastic Block Store.

Persistent block storage attached to EC2.

Use Cases:

* Databases
* Application storage

---

## EBS vs Instance Store

EBS:

* Persistent
* Network attached
* Supports snapshots

Instance Store:

* Temporary
* Faster
* Data lost when instance stops

---

## What is an EBS Snapshot?

Backup of an EBS volume stored in S3.

Benefits:

* Disaster Recovery
* Volume restoration

---

## What is an Elastic IP?

Static public IPv4 address.

Use Cases:

* Fixed endpoint

AWS Recommendation:
Use ALB and Route53 instead.

---

## What are Placement Groups?

Mechanism controlling how EC2 instances are placed physically.

Types:

Cluster:

* Low latency

Spread:

* Fault isolation

Partition:

* Large distributed systems

---

## What are EC2 Purchasing Options?

On-Demand:

* Flexible

Reserved:

* Long-term savings

Spot:

* Cheap but interruptible

Dedicated Hosts:

* Physical server dedicated to customer

---

## What is Auto Scaling?

Automatically adds or removes EC2 instances based on demand.

Benefits:

* High Availability
* Cost Optimization

---

## Interview Question

Q: How would you deploy a Spring Boot application in AWS?

Answer:

1. Package application as JAR
2. Launch EC2 instance
3. Install Java
4. Deploy application
5. Configure Security Groups
6. Use ALB for load balancing
7. Store data in RDS
8. Configure Auto Scaling

---

## Interview Question

Q: How does EC2 access S3 securely?

Answer:

Create IAM Role with S3 permissions and attach it to EC2. Avoid storing access keys inside application code.

---

## Interview Question

Q: Why use Spot Instances?

Answer:

Reduce infrastructure cost for fault-tolerant workloads such as batch processing and data analytics.

---

## Interview Question

Q: What storage would you use for a production database?

Answer:

EBS because it provides persistent storage, snapshots, backup capability, and high durability.

---

## Senior Backend Interview Focus

Must Know:

* EC2 Lifecycle
* Security Groups
* IAM Roles
* User Data
* EBS
* Snapshots
* Auto Scaling
* ALB
* EC2 Pricing Models
* High Availability Architecture

Real Architecture:

Users
|
Route53
|
ALB
|
Auto Scaling Group
|
EC2 Instances
|
RDS
|
S3
