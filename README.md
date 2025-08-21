HLD roadmap (end-to-end)
phase 0 — how to think (foundations)
problem framing & requirements

functional vs non-functional, success metrics, constraints, assumptions, risks, scope control

API-first thinking, request/response contracts, versioning

capacity planning & back-of-the-envelope

QPS/RPS, DAU/MAU, data size, read/write mix, peak vs p95/p99, fan-out, SLO → capacity

core data modeling

relational vs NoSQL, normalization vs denormalization, ERD, access patterns, schema evolution

keys, secondary indexes, TTL, partition keys, hot partitions

phase 1 — distributed systems building blocks
consistency & availability

CAP, PACELC, consistency models (strong, eventual, read-your-writes, monotonic), quorum reads/writes

storage & indexing internals

B-tree, LSM tree, write-ahead log, compaction, transactions, isolation levels

replication, sharding & multi-tenancy

leader/follower, sync/async, rebalancing, consistent hashing, tenant isolation, noisy neighbor

caching & CDNs

client vs edge vs app vs db cache; TTL, LRU/LFU, cache stampede, write-through/around/back

messaging & streams

queues vs pub/sub, ordering, exactly-once/at-least-once, consumer groups, backpressure, replay, DLQ

service architecture

monolith vs microservices, service boundaries, idempotency, retries, saga/outbox, API gateway

networking & load balancing

L4/L7, reverse proxies, health checks, sticky sessions, rate limiting, circuit breaking

phase 2 — reliability, observability, security
reliability & resiliency

SLI/SLO/SLA, error budgets, chaos/DR drills, multi-AZ/region, failover patterns, bulkheads

observability

logs/metrics/traces, RED/USE methods, dashboards, alerts, tracing a request across services

security & privacy

authN/authZ (OAuth2/OIDC, JWT), secrets mgmt, encryption (at rest/in transit), PII handling

cost & performance engineering

perf profiles, hotspots, perf/cost trade-offs, FinOps basics

phase 3 — special systems (you’ll meet in interviews)
search systems

inverted index, ranking basics, Elasticsearch/OpenSearch topology

media/file storage at scale

object storage, chunking, dedup, resumable upload, CDN signing

real-time delivery

websockets/long-polling/SSE, presence, fan-out to N, push notifications

analytics pipelines

batch vs streaming (Lambda/Kappa), ETL vs ELT, exactly-once sinks, late/ordered events

payments & ledgers (high-stakes correctness)

idempotency keys, double-entry ledger, reconciliation, consistency choices

phase 4 — case studies (reusable patterns)
classic designs (progressively harder)

url shortener, rate limiter, news feed, chat/messaging, notification service, file storage/drive, search autocomplete, ride-sharing, video streaming, ad serving, web crawler, e-commerce checkout

phase 5 — interview execution
whiteboard workflow & storytelling

45–60 min flow, diagramming kit, trade-off narration, handling pushback, finishing strong

personal “toolbelt” templates, checklists, and a capacity calculator

how we’ll do each topic (repeatable template)
60-sec interview pitch (how to explain)

deep dive essentials (everything you must know)

child-like memory hooks (sticky analogies)

likely interview questions (basic → advanced)

10–15 min mini-task (quick practice)

what’s next (preview + small prep)

Topic 1 — problem framing + API-first (start here)
60-sec interview pitch
“I start by clarifying functional goals, then lock non-functional targets (SLA/SLO, latency p95/p99, availability, cost). I define constraints & assumptions and choose APIs/contracts that reflect access patterns. With that, I estimate capacity (traffic, data size, read/write ratio) to guide choices like storage, caching, and partitioning. I document risks and define a simple MVP → v2 evolution path before drawing the high-level diagram.”

deep dive essentials
functional vs non-functional: features vs qualities (latency, availability, durability, cost, security)

constraints & assumptions: user scale, geo, client types, data retention, compliance

success metrics: e.g., p95 < 200 ms, 99.9% availability, <$X/day infra

API-first: define endpoints early (input validation, idempotency, versioning, pagination, filtering, errors)

contracts & evolution: backward compatibility, canarying, deprecation policy

risk list: hotspots, single points of failure, data loss scenarios, abuse/rate-limit needs

MVP → v2 path: deliver core read/write, add search/analytics later

tiny Java-flavored API checklist
pagination: ?limit=&cursor= over ?page=

idempotency: Idempotency-Key header for POST (server stores recent keys)

versioning: /v1/… + semantic change logs

error model: typed codes + stable shape {code, message, details, traceId}

child-like memory hook
use “SPADE”:

Scope (what & who)

Performance goals (latency, availability, cost)

APIs (contracts first)

Data (model & access patterns)

Estimates (traffic, storage, growth)

when stuck, dig with your SPADE.

interview questions (likely)
clarify: “what are the strict non-functionals and typical request paths?”

trade-offs: “how would your API design support evolution without breaking clients?”

reliability: “where would you put idempotency and why?”

abuse: “what rate limits or quotas make sense here?”

migration: “how would you deprecate v1 to v2 safely?”

mini-task (10–15 min)
write a minimal API for a note-taking service (create/read/list) that is future-proof:

list the endpoints with request/response shapes

add pagination, idempotency, and error model

note 3 non-functional targets and 3 assumptions

(if you want, tell me “generate baseline” and I’ll draft a clean spec we iterate on.)

what’s next
Topic 2: capacity planning & back-of-the-envelope.
we’ll learn quick math to size QPS, storage/day, cache hit targets, shard counts, and call out p95/p99. we’ll build a tiny capacity calculator and practice on the notes API.

