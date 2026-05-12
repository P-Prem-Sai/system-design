# Memcached vs Redis

## Overview

Both **Memcached** and Redis are **in-memory data stores** used to improve application performance by reducing database load.

* **Memcached** → Simple distributed caching system
* **Redis** → Advanced in-memory data structure store

---

# High-Level Difference

| Feature      | Memcached                         | Redis                                |
| ------------ | --------------------------------- | ------------------------------------ |
| Data Type    | Simple key-value                  | Advanced data structures             |
| Persistence  | No                                | Yes                                  |
| Complexity   | Simple                            | Feature-rich                         |
| Speed        | Extremely fast for simple caching | Very fast                            |
| Scaling      | Easy horizontal scaling           | Replication + clustering             |
| Memory Usage | More efficient                    | Slightly higher                      |
| Use Cases    | Pure caching                      | Cache + queues + pub/sub + analytics |

---

# 1. Data Structure Support

## Memcached

Supports only:

```text
key -> string/blob
```

Example:

```text
user:101 -> "Prem"
```

---

## Redis

Supports:

* Strings
* Lists
* Hashes
* Sets
* Sorted Sets
* Bitmaps
* Streams
* HyperLogLogs

Example:

```text
user:101:name -> "Prem"
user:101:skills -> ["Python", "AWS"]
```

---

# 2. Persistence

## Memcached

* Purely in-memory
* Data lost on restart

Used only as a temporary cache.

---

## Redis

Supports persistence using:

* RDB snapshots
* AOF (Append Only File)

Can also behave like a lightweight database.

---

# 3. Performance

## Memcached

Optimized for:

* Simple key-value access
* Very high throughput
* Low latency

Usually slightly faster for basic caching.

---

## Redis

Still extremely fast but includes additional features:

* Data structures
* Persistence
* Replication
* Transactions

---

# 4. Multi-threading

## Memcached

* Multi-threaded
* Uses multiple CPU cores efficiently

---

## Redis

Traditionally single-threaded for command execution.

Modern Redis versions use threads for:

* networking
* background tasks
* I/O operations

---

# 5. Scaling

## Memcached

Horizontal scaling through client-side hashing.

Example:

```text
Server1 -> users
Server2 -> products
Server3 -> sessions
```

No replication between nodes.

---

## Redis

Supports:

* Replication
* Clustering
* Sentinel failover

More powerful but more complex.

---

# 6. Memory Efficiency

## Memcached

More memory efficient for:

* simple string caching
* massive cache workloads

---

## Redis

Uses more memory because of:

* metadata
* advanced structures
* persistence support

---

# 7. Eviction Policies

Both support eviction when memory becomes full.

## Redis supports advanced policies:

* LRU
* LFU
* TTL-based eviction
* Random eviction

---

# 8. Use Cases

## Memcached Best For

### Simple caching

Examples:

* API response cache
* Database query cache
* HTML page cache

Architecture:

```text
App -> Memcached -> Database
```

---

## Redis Best For

### Advanced distributed systems

Examples:

* Session store
* Leaderboards
* Chat systems
* Rate limiting
* Queues
* Pub/Sub
* Distributed locks
* Real-time analytics

---

# Example Commands

## Memcached

```text
GET user:101
SET user:101 "Prem"
```

---

## Redis

```text
INCR page_views
LPUSH notifications "msg"
ZADD leaderboard 100 prem
```

---

# Real-World Analogy

## Memcached

Like:

> A super-fast temporary notebook.

---

## Redis

Like:

> A notebook + queue + ranking system + messaging system + analytics engine.

---

# Company Usage

## Memcached

Historically used by:

* Facebook
* large-scale web caching systems

---

## Redis

Widely used in:

* microservices
* distributed systems
* real-time applications

Used by:

* GitHub
* Twitter
* Stack Overflow

---

# Interview Quick Summary

## Choose Memcached When

* Only caching is needed
* Simple key-value store is enough
* Maximum memory efficiency matters
* Extremely high throughput is required

---

## Choose Redis When

* Advanced data structures are needed
* Persistence is required
* Pub/Sub or queues are needed
* Distributed locks are required
* Replication and clustering are needed

---

# One-Line Difference

> **Memcached** = Simple distributed cache
> **Redis** = Powerful in-memory data structure store with caching capabilities

---

# Quick Revision Table

| Topic            | Memcached      | Redis                       |
| ---------------- | -------------- | --------------------------- |
| Storage          | Key-value      | Multiple data structures    |
| Persistence      | ❌ No           | ✅ Yes                       |
| Multi-threaded   | ✅ Yes          | Mostly single-threaded      |
| Replication      | ❌ No           | ✅ Yes                       |
| Clustering       | ❌ Limited      | ✅ Yes                       |
| Pub/Sub          | ❌ No           | ✅ Yes                       |
| Transactions     | ❌ No           | ✅ Yes                       |
| Memory Efficient | ✅ Better       | ❌ Slightly higher usage     |
| Best For         | Simple caching | Complex distributed systems |

---

# Final Interview Answer

> Memcached is a lightweight distributed caching system optimized for simple high-speed key-value caching, while Redis is a powerful in-memory data structure store that supports persistence, replication, pub/sub, queues, and advanced data structures.
