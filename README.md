# 📘 High Level Design (HLD) Roadmap

This document combines a **comprehensive HLD roadmap** with topics covered in **Shrayansh Jain’s courses/resources** (Udemy, Concept && Coding channel, InterviewReady references) and standard industry best practices. It is structured as a **study + interview preparation guide**.

---

## 1. Foundations

* **System Design Thinking**

  * Functional vs Non-Functional requirements
  * Constraints, assumptions, risks, scope control
  * API-first design (idempotency, versioning, pagination, contracts)
  * Success metrics & SLAs
* **Estimation & Capacity Planning**

  * Requests per second (RPS/QPS)
  * Storage estimation (daily/annual growth)
  * Peak load vs average load
  * Latency (p95, p99)

---

## 2. Core Distributed Systems Concepts

* **Networking & Protocols** (Shrayansh Jain)

  * TCP, UDP, HTTP, gRPC, WebSockets
  * DNS, CDN basics
* **CAP Theorem & PACELC**

  * Consistency vs Availability vs Partition Tolerance
  * Strong, Eventual, Causal Consistency
* **Load Balancing**

  * L4 vs L7
  * Sticky sessions, health checks
* **Caching**

  * Client, CDN, server-side, DB cache
  * Write-through, write-around, write-back
  * Cache invalidation, cache stampede
* **Databases**

  * RDBMS vs NoSQL
  * Indexing (B-Tree, LSM Tree)
  * Sharding, partitioning, replication
  * Isolation levels, transactions

---

## 3. Messaging & Communication

* **Message Queues & Pub/Sub**

  * Kafka, RabbitMQ, SQS
  * Ordering guarantees, replay, DLQ
* **Event-Driven Design**

  * Producers, Consumers
  * Event sourcing vs CQRS

---

## 4. Service Architecture & Design

* **Monolith vs Microservices**
* **Service Discovery & API Gateway**
* **Idempotency & Retries**
* **Saga Pattern & Outbox Pattern**
* **Design Patterns for HLD** (Shrayansh Jain coverage)

  * Proxy, Observer, Factory, Singleton in distributed systems

---

## 5. Reliability & Observability

* **Reliability**

  * SLI, SLO, SLA
  * Error budgets, DR strategy
  * Multi-AZ & Multi-Region
* **Observability**

  * Metrics, logs, tracing
  * RED & USE methods
* **Resiliency Patterns**

  * Circuit breaker, bulkhead, failover

---

## 6. Security & Privacy

* Authentication & Authorization (OAuth2, JWT)
* Encryption (in-transit, at-rest)
* Rate limiting & quota management
* Secrets management
* OWASP Top 10 for distributed systems

---

## 7. Cost & Performance Engineering

* Latency profiling
* FinOps basics
* Horizontal vs vertical scaling
* CDN offloading to reduce infra costs

---

## 8. Special Systems (Shrayansh Jain Coverage)

* **Search Systems**

  * Inverted index, Elasticsearch
* **Real-time Systems**

  * WebSockets, long polling, SSE
* **Media/File Storage**

  * Object storage, CDN, chunking, deduplication
* **Analytics Pipelines**

  * Batch vs streaming, ETL vs ELT
* **Payment Systems**

  * Double-entry ledger
  * Idempotency keys, reconciliation
* **Rate Limiting Systems**

  * Token bucket, leaky bucket
* **Distributed Logging & Monitoring**

  * Log aggregation, tracing, alerting pipelines

---

## 9. Case Studies (Interview-Ready)

* URL Shortener
* Rate Limiter
* News Feed System
* Chat/Messaging App
* Notification Service
* File Storage/Drive (Dropbox, Google Drive)
* Search Autocomplete
* Ride Sharing (Uber)
* Video Streaming (YouTube/Netflix)
* Ad Serving System
* Web Crawler
* E-commerce Checkout
* Payment Gateway (Stripe, Razorpay-like)
* Social Media Timeline (Instagram/Twitter)
* Distributed Logging System (Splunk/ELK)

---

## 10. Interview Strategy

* **Workflow for 45–60 min interviews**

  * Clarify requirements
  * Estimate capacity
  * Design components
  * Trade-offs
  * Wrap-up with evolution path
* Always highlight:

  * APIs
  * Data storage choices
  * Scalability approach
  * Reliability/resiliency
  * Cost and performance

---

✅ With this roadmap, you won’t miss **any topic from Shrayansh Jain (Udemy + YouTube + InterviewReady) or standard FAANG-style HLD prep**.

👉 Next step: We will go **topic by topic**, starting with **Problem Framing & API-first design** in depth (interview pitch → deep dive → memory tricks → interview Qs → mini-task).
