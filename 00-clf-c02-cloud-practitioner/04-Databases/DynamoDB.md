# DynamoDB

## What is it?
AWS's fully managed, serverless NoSQL key-value and document database.
Millisecond performance at any scale.

Like a highly scalable hash table or key-value store in the cloud — fully managed with no servers to provision or capacity to plan.

---

## Key Concepts
- **Tables** — collection of items (no fixed schema required)
- **Items** — individual records (like a row in SQL)
- **Attributes** — fields on an item (flexible per item, unlike SQL columns)
- **Primary Key** — Partition Key alone, or Partition Key + Sort Key
- **DynamoDB Streams** — capture item-level changes in real time can trigger Lambda
- **DAX (DynamoDB Accelerator)** — in-memory cache layer, reduces response times to microseconds

## When to Use It ✅
- High-scale, low-latency key-value lookups
- Serverless applications (pairs naturally with Lambda)
- Gaming leaderboards, session stores, shopping carts
- IoT data ingestion
- Flexible schema requirements

## When NOT to Use It ❌
- Complex SQL queries and joins → use RDS
- Need ACID transactions across many tables → use RDS
- Analytical queries on large datasets → use Redshift

---

## 💡 Good to Know
- DynamoDB is **serverless** — no infrastructure to manage,
  no capacity planning, scales automatically
- DynamoDB is **NoSQL** — no SQL, no joins, no fixed schema
- Scales to millions of requests per second automatically
- Single-digit millisecond performance at any scale — this is
  its key selling point
- **Global Tables** = multi-region, multi-active replication —
  data is available in multiple regions simultaneously

---

## ⚠️ Easy to Mix Up
- DynamoDB ≠ SQL. Do not use it where you need complex relational queries.
- "Serverless database" in exam = likely DynamoDB
  (or Aurora Serverless for relational)
- DynamoDB is NOT just a cache — it is a full database.
  DAX is the caching layer on top of DynamoDB.

---

## RDS vs DynamoDB — Quick Decision Guide
| Factor | Choose RDS | Choose DynamoDB |
|---|---|---|
| Data model | Relational/SQL | Key-value/document |
| Schema | Fixed | Flexible |
| Scale | Vertical + read replicas | Horizontal, automatic |
| Serverless | No (except Aurora Serverless) | Yes |
| Query style | Complex SQL joins | Simple key lookups |
