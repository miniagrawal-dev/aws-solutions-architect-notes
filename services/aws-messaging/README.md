# AWS Messaging Services (SQS, SNS, Kinesis & Amazon MQ)

# Overview

AWS provides multiple messaging and streaming services to decouple applications, improve scalability, increase reliability, and enable event-driven architectures.

This section covers:

* Amazon SQS
* Amazon SNS
* Amazon Kinesis
* Amazon MQ (ActiveMQ)

---

# Why Messaging?

Without messaging:

Service A directly calls Service B.

Problems:

* Tight coupling
* Cascading failures
* Poor scalability
* Difficult retries

With messaging:

Producer

↓

Message Queue / Topic

↓

Consumer

Benefits:

* Loose coupling
* Reliability
* Scalability
* Fault tolerance
* Asynchronous processing

---

# Amazon SQS

Simple Queue Service is a fully managed message queue.

Supports asynchronous communication between services.

Producer

↓

Queue

↓

Consumer

Messages remain in the queue until processed.

---

# Types of SQS

## Standard Queue

Features:

* Unlimited throughput
* At-least-once delivery
* Best-effort ordering

Use Cases:

* Order Processing
* Email Sending
* Background Jobs
* Image Processing

---

## FIFO Queue

Features:

* Exactly-once processing
* First-In-First-Out ordering
* Message Group ID

Use Cases:

* Payment Systems
* Banking
* Inventory Management

---

# Important SQS Concepts

## Visibility Timeout

After a consumer receives a message:

The message becomes temporarily invisible.

If processing succeeds:

Delete message.

If processing fails:

Message becomes visible again.

---

## Long Polling

Waits for messages before returning a response.

Benefits:

* Fewer empty responses
* Lower cost
* Better performance

---

## Dead Letter Queue (DLQ)

Stores messages that repeatedly fail processing.

Useful for:

* Debugging
* Monitoring
* Preventing infinite retries

---

# Amazon SNS

Simple Notification Service is a Pub/Sub messaging service.

Publisher

↓

SNS Topic

↓

Multiple Subscribers

Subscribers may include:

* SQS
* Lambda
* Email
* SMS
* HTTP Endpoint

One message can reach many subscribers.

---

# Fan-Out Pattern

Order Created

↓

SNS Topic

↓

Inventory Service

↓

Billing Service

↓

Email Service

↓

Analytics Service

Every subscriber receives the same event.

---

# Amazon Kinesis

Real-time streaming platform.

Used for continuous processing of streaming data.

Examples:

* IoT Devices
* Clickstream
* Log Analytics
* Financial Data
* Sensor Data

Supports:

* High throughput
* Ordered streams
* Real-time analytics

---

# Amazon MQ (ActiveMQ)

Managed message broker.

Supports:

* ActiveMQ
* RabbitMQ

Used when migrating existing enterprise applications.

Provides compatibility with:

* JMS
* AMQP
* MQTT
* STOMP

Unlike SQS, Amazon MQ manages traditional message brokers.

---

# SQS vs SNS

| SQS                                 | SNS                                       |
| ----------------------------------- | ----------------------------------------- |
| Queue                               | Topic                                     |
| One Consumer processes each message | Multiple subscribers receive same message |
| Pull Model                          | Push Model                                |
| Asynchronous Processing             | Notifications & Events                    |

---

# SQS vs Kafka vs Kinesis

| SQS             | Kafka                | Kinesis          |
| --------------- | -------------------- | ---------------- |
| Queue           | Event Streaming      | Event Streaming  |
| Managed         | Self-managed/Managed | Fully Managed    |
| No Replay       | Replay Supported     | Replay Supported |
| Background Jobs | Event Streaming      | AWS Streaming    |

---

# Amazon MQ vs SQS

Amazon MQ

* Traditional Broker
* JMS Support
* Existing Enterprise Applications

SQS

* Cloud Native
* Serverless
* Highly Scalable

---

# Hands-On

* Created Standard Queue
* Created FIFO Queue
* Configured Dead Letter Queue
* Published messages to SNS
* Connected SNS with SQS
* Explored Fan-Out architecture
* Created Kinesis Data Stream
* Reviewed Amazon MQ

---

# Best Practices

* Use SQS to decouple services.
* Use FIFO only when ordering is required.
* Configure Dead Letter Queues.
* Enable Long Polling.
* Use SNS for notifications.
* Use Kinesis for real-time streaming.
* Use Amazon MQ only for legacy migrations.

---

# Production Example

Order Service

↓

SNS Topic

↓

Inventory Service (SQS)

↓

Email Service (SQS)

↓

Billing Service (SQS)

↓

Analytics Service (Kinesis)

This architecture is scalable, fault tolerant, and event-driven.
