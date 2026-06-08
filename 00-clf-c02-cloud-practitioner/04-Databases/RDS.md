# RDS — Relational Database Service

## What is it?
Managed relational database service. AWS handles provisioning, patching, backups, and failover — you manage your data and schema.

Your physical database server (MySQL, PostgreSQL, Oracle) — but AWS racks it, patches the OS and DB engine, and manages replication.
You just connect and run queries.

---

## Supported Engines
- MySQL, PostgreSQL, MariaDB, Oracle, Microsoft SQL Server
- **Amazon Aurora** — AWS's own high-performance relational DB
  (MySQL/PostgreSQL compatible, up to 5x faster than MySQL)

## Key Concepts
- **Multi-AZ** — synchronous standby replica in another AZ for
  automatic failover. Used for **high availability**, not performance.
- **Read Replicas** — asynchronous read-only copies for read scaling.
  Used for **performance**, not failover.
- **Automated Backups** — daily snapshots + transaction logs,
  retained for up to 35 days
- Runs inside your VPC — not publicly accessible by default

## When to Use It ✅
- Structured, relational data with SQL queries
- Existing applications using MySQL/PostgreSQL/etc.
- ACID transactions required (banking, e-commerce)

## When NOT to Use It ❌
- Key-value or document data → use DynamoDB
- Need massive scale with flexible schema → use DynamoDB
- Data warehousing and analytics → use Redshift
