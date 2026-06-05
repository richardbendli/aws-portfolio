# Amazon Aurora

## What is it?
AWS's cloud-native relational database — fully managed, MySQL and PostgreSQL compatible, built from the ground up for the cloud.

Like having a super-charged, self-healing MySQL or PostgreSQL cluster — but without any of the operational overhead of managing replication,
failover, or storage.

---

## Key Concepts
- **MySQL and PostgreSQL compatible** — works with existing MySQL/
  PostgreSQL drivers, tools, and applications
- **Up to 5x faster** than standard MySQL, **3x faster** than
  standard PostgreSQL
- Storage automatically grows in 10GB increments up to 128TB —
  no capacity management needed
- **6 copies of data** replicated across 3 AZs automatically
- **Aurora Serverless** — automatically starts, scales, and stops
  based on demand. Pay per second. Good for variable workloads.
- **Aurora Global Database** — replicate across multiple AWS regions
  for low-latency global reads and disaster recovery

## When to Use It ✅
- Need higher performance than standard RDS MySQL/PostgreSQL
- Want managed relational DB with automatic storage scaling
- Variable or unpredictable workloads (Aurora Serverless)
- Global applications needing low-latency reads in multiple regions

## When NOT to Use It ❌
- Cost is a concern and standard RDS MySQL/PostgreSQL is sufficient
- NoSQL or key-value data → use DynamoDB
- Need Oracle or SQL Server → use standard RDS

---

## 💡 Good to Know
- Aurora is part of the RDS family but is a distinct, higher-performance
  offering — it's worth knowing as a separate service
- **Aurora Serverless** is one of the exam answers for
  "serverless relational database"
- Aurora storage is automatically backed up continuously to S3
- Aurora is more expensive than standard RDS — choose it when
  you need the performance or the serverless capability

---

## ⚠️ Easy to Mix Up
- **Aurora** (AWS cloud-native, MySQL/PostgreSQL compatible, premium)
  vs standard **RDS** (managed but on traditional DB engines)
- "Serverless database" in an exam question could mean
  Aurora Serverless OR DynamoDB — read the context carefully
