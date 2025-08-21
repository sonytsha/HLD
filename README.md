# 📘 High Level Design (HLD) Roadmap

This document combines a **comprehensive HLD roadmap** with topics covered in **Shrayansh Jain’s courses/resources** (Udemy + Concept & Coding) and standard industry references. It is structured as a **study + interview preparation guide**.

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
* **Design Patterns for HLD** (from Shrayansh Jain’s course)

  * Proxy, Observer, Factory, Singleton usage in distributed systems

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

  * Circuit breaker, bulkhead,
