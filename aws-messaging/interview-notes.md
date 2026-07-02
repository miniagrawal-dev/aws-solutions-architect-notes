# AWS Messaging Services - Interview Notes

# What is Amazon SQS?

Amazon SQS is a fully managed message queue service used to decouple distributed applications.

Producer sends messages.

Consumers process messages asynchronously.

---

# Why use SQS?

Benefits:

* Loose Coupling
* Retry Mechanism
* High Availability
* Scalability
* Failure Isolation

---

# Standard vs FIFO Queue

| Standard               | FIFO                    |
| ---------------------- | ----------------------- |
| At-least-once delivery | Exactly-once processing |
| Best-effort ordering   | Strict ordering         |
| Higher throughput      | Lower throughput        |
| Default choice         | Financial systems       |

---

# What is Visibility Timeout?

When a consumer receives a message:

The message becomes invisible.

If processed successfully:

Delete it.

Otherwise:

It reappears after timeout.

---

# What is a Dead Letter Queue?

Messages failing multiple times are moved to the DLQ.

Benefits:

* Prevent infinite retries
* Easier debugging
* Error monitoring

---

# What is SNS?

SNS is a publish-subscribe messaging service.

One publisher.

Multiple subscribers.

Supports:

* Email
* SMS
* Lambda
* HTTP
* SQS

---

# SQS vs SNS

SQS

One consumer processes one message.

SNS

One message is delivered to many subscribers.

---

# What is Fan-Out Pattern?

SNS receives one message.

↓

Multiple SQS queues receive copies.

Each microservice processes independently.

---

# What is Amazon Kinesis?

AWS managed real-time streaming platform.

Used for:

* Log Streaming
* IoT
* Analytics
* Clickstream
* Financial Data

Supports replay and ordered processing.

---

# What is Amazon MQ?

Managed ActiveMQ/RabbitMQ service.

Used when migrating applications already using JMS or traditional message brokers.

---

# Amazon MQ vs SQS

Amazon MQ

* Traditional broker
* Supports JMS
* Stateful

SQS

* Serverless
* Cloud-native
* Highly scalable

---

# Common Interview Questions

## Why use SQS instead of REST communication?

REST creates synchronous dependency.

If Service B is down:

Service A also fails.

With SQS:

Messages remain safely stored until consumers become available.

---

## Why use SNS with SQS?

SNS allows one event to be delivered to multiple services.

Each service has its own SQS queue.

Provides loose coupling.

---

## When would you choose FIFO?

When ordering is critical.

Examples:

* Payments
* Banking
* Stock Trading
* Inventory Updates

---

## Why configure a Dead Letter Queue?

Failed messages should not block queue processing.

DLQ stores problematic messages for later investigation.

---

## When should Kinesis be used instead of SQS?

Kinesis is designed for continuous streaming and real-time analytics.

SQS is designed for asynchronous task processing.

---

## Why choose Amazon MQ?

Only when migrating legacy enterprise applications already using JMS, ActiveMQ, or RabbitMQ.

For new cloud-native applications, SQS and SNS are generally preferred.

---

# Senior Backend Interview Focus

Know these topics thoroughly:

* SQS Standard vs FIFO
* Visibility Timeout
* Dead Letter Queue
* Long Polling
* SNS Fan-Out Pattern
* Kinesis vs Kafka
* Amazon MQ vs SQS
* Idempotent Consumers
* Event-Driven Architecture
* Retry Strategies

---

# Production Architecture

Order Service

↓

SNS Topic

↓

Inventory Queue

↓

Billing Queue

↓

Notification Queue

↓

Consumers

↓

Database

---

# Real Interview Question

Design an Order Processing System.

Expected Architecture:

Order API

↓

SNS

↓

Inventory Queue

Billing Queue

Email Queue

Shipping Queue

↓

Independent Consumers

↓

Database

Benefits:

* Loose coupling
* Independent scaling
* Better fault tolerance
* Easier maintenance

---

# One-Line Revision

Use SQS for asynchronous processing, SNS for publish-subscribe notifications, Kinesis for real-time event streaming, and Amazon MQ when integrating or migrating legacy JMS-based messaging systems.
