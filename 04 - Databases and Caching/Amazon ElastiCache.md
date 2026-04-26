---
title: Amazon ElastiCache
tags:
  - aws
  - database
  - cache
aliases:
  - ElastiCache
---

# Amazon ElastiCache

## What It Is

Amazon ElastiCache is AWS's managed in-memory caching service. It is used to improve application performance by storing frequently accessed data in memory instead of repeatedly fetching it from slower systems.

## Why It Exists

Databases and downstream APIs often become bottlenecks. A cache reduces latency, database load, repeated expensive computation, and session storage overhead.

## Core Concepts

- In-memory data
- Cache-aside pattern
- TTL
- Cache is usually not the source of truth

## How It Works

Applications read and write to the cache directly. On a miss, they fall back to the database or another backend.

```mermaid
flowchart LR
    U[User Request] --> APP[Application]
    APP --> CACHE[ElastiCache]
    CACHE -->|Hit| APP
    CACHE -->|Miss| DB[Database]
    DB --> APP
    APP --> CACHE
```

## When To Use

Use ElastiCache when you need faster reads, session storage, rate limiting or counters, temporary state, or reduced load on databases.

## When Not To Use

Do not use ElastiCache when you need durable long-term storage as the source of truth or when the dataset is rarely reused.

## Common Use Cases

- Web session storage
- Product catalog caching
- Leaderboards and counters
- API response caching
- Feature flag lookups

## Cost And Operations

Cost factors include node size, cluster count, replication choices, and backup options. Plan eviction and TTL strategy carefully and monitor hit ratio and memory use.

## Common Mistakes

- Treating cache as permanent storage
- Forgetting invalidation strategy
- Caching everything without measuring hit rates
- Assuming adding a cache automatically fixes poor queries

## Practical Example

An ecommerce site caches product details in ElastiCache. Most reads return in-memory data, the primary database handles only misses or updates, and response times drop while database load falls.

## Related Notes

- [[Amazon RDS]]
- [[Amazon Aurora]]
- [[Amazon DynamoDB]]
