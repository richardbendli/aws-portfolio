# EBS — Elastic Block Store

## What is it?
Persistent block storage volumes attached to EC2 instances. Think of it as the virtual hard drive for your EC2 server.
Low-latency block storage — the data survives if you stop the instance (unlike instance store).

---

## Key Concepts
- Attached to **one EC2 instance at a time** (in the same AZ)
- Persists independently from the instance lifecycle
- **Snapshots** — point-in-time backups stored in S3
  (not visible in your S3 console — managed separately by AWS)
- **Volume Types:**
  - **gp3/gp2** — General Purpose SSD (most common, default root volume)
  - **io2/io1** — Provisioned IOPS SSD (high-performance databases)
  - **st1** — Throughput Optimised HDD (big data, log processing)
  - **sc1** — Cold HDD (cheapest, infrequent access)

## When to Use It ✅
- Root volume (OS disk) for EC2
- Database storage requiring low latency
- Any persistent storage attached to a single EC2 instance

## When NOT to Use It ❌
- Share storage across multiple EC2 instances → use EFS
- Object or file storage → use S3

---