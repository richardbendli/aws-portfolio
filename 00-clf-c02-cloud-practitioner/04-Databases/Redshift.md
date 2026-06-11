# Redshift — Data Warehouse

## What is it?
Fully managed, petabyte-scale data warehouse service.
Used for running complex analytical queries across massive datasets.

Like an on-premises data warehouse (Teradata, Oracle DW) — but fully managed, scales to petabytes, and costs a fraction of the price.

---

## Key Concepts
- **OLAP** (Online Analytical Processing) — designed for
  complex queries, aggregations, and reporting across large datasets.
  NOT for day-to-day transactional workloads.
- **Columnar storage** — data stored by column not row,
  making analytical queries dramatically faster.
- **Massively Parallel Processing (MPP)** — distributes
  queries across multiple nodes simultaneously.
- **Redshift Serverless** — run analytics without managing
  a cluster. Pay only for what you use.
- **Redshift Spectrum** — query data directly in S3
  without loading it into Redshift first.

## When to Use It ✅
- Business intelligence (BI) and reporting
- Analytics on petabytes of historical data
- Complex SQL queries across large datasets
- Data lake analytics

## When NOT to Use It ❌
- Day-to-day transactions (orders, payments) → use RDS
- Key-value / NoSQL → use DynamoDB
- Real-time in-memory lookups → use Caching

---

## Good to Know
- Redshift = OLAP. RDS = OLTP. This is heavily tested.
- "Petabyte-scale" or "data warehouse" in an exam
  question → answer is almost always Redshift
- Redshift Serverless removes the need to provision
  or manage clusters — good for variable workloads
- Redshift integrates natively with S3, making it
  the centre of an AWS data lake architecture

---

## Easy to Mix Up
- **Redshift** (analytics, OLAP, historical data)
  vs **RDS** (transactions, OLTP, live application data)
- **Redshift** (SQL, structured, columnar)
  vs **DynamoDB** (NoSQL, key-value, real-time)
- **Redshift Spectrum** (query S3 directly)
  vs **Athena** (also queries S3 — serverless, no cluster needed)

---

## Database Decision Guide
| Workload | Service |
|---|---|
| Relational, transactional (OLTP) | RDS / Aurora |
| Analytics, reporting (OLAP) | Redshift |
| NoSQL, key-value, serverless | DynamoDB |
| In-memory cache | ElastiCache |
| Data warehouse, petabyte scale | Redshift |
