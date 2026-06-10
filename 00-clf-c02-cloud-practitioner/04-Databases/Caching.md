# Caching — ElastiCache

## What is it?
Fully managed in-memory caching service. Dramatically speeds up applications by storing frequently accessed data in memory, so your databases aren't hit on every request.

Like adding a Redis or Memcached cluster in front of your database — reads hit the fast in-memory cache first, and only go to the database if the data isn't cached yet.

---

## ElastiCache Engines

| Engine | Best For |
|---|---|
| **Redis** | Complex data types, persistence, pub/sub, sorted sets, leaderboards |
| **Memcached** | Simple key-value caching, multi-threading, horizontal scaling |

## When to Use It ✅
- Reduce database load for read-heavy applications
- Store session data for web applications
- Cache results of expensive database queries
- Real-time leaderboards (Redis sorted sets)
- Rate limiting and counters

## When NOT to Use It ❌
- Data that changes frequently and consistency is critical
- Primary data store — ElastiCache is a cache, not a database
- If your read load is low and RDS/DynamoDB handles it fine

---

## 💡 Good to Know
- ElastiCache sits **in front of** your database — it doesn't
  replace it. The pattern is: app → cache → database (on cache miss)
- **Redis** is the more feature-rich option and is generally preferred
  for new deployments
- Both engines run inside your **VPC**
- ElastiCache is a managed service — AWS handles patching,
  failover, and backups
- **Read-heavy workloads** are the classic use case — if your app
  reads the same data repeatedly, caching it saves significant
  database cost and latency

---

## ⚠️ Easy to Mix Up
- **ElastiCache** (managed caching, reduces DB load)
  vs **DAX** (DynamoDB-specific cache) vs **CloudFront** (CDN cache)
  — they all cache things but at different layers
- ElastiCache is NOT a database — it is a cache. Data can be lost
  if the cache restarts (unless Redis persistence is configured).

---

## Caching Strategy
```
Request arrives
      ↓
Check ElastiCache
      ↓
Cache HIT? → Return data instantly (microseconds)
Cache MISS? → Query database → Store result in cache → Return data
```
