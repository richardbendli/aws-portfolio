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

## 💡 Good to Know
- EBS volumes are **AZ-specific** — a volume in London AZ-a cannot be attached to an instance in London AZ-b
- To move an EBS volume to a different AZ: take a **snapshot** → create a new volume from the snapshot in the target AZ
- **Delete on Termination** is enabled by default for root volumes — additional volumes are NOT deleted by default on termination
- EBS = **Block storage** (vs S3=Object, EFS=File)
- Snapshots are incremental — only changed blocks are saved after the first full snapshot

---

## ⚠️ Easy to Mix Up
- EBS volumes can only be attached to **ONE instance at a time** (exception: io1/io2 multi-attach, but this is an advanced use case)
- Snapshots are stored in S3 but you don't see them in your S3 buckets — they're managed through the EC2 console
- **EBS** (survives instance stop) ≠ **Instance Store** (lost on stop or terminate)

---

## Storage Comparison
| Feature | S3 | EBS | EFS |
|---|---|---|---|
| Type | Object | Block | File (NFS) |
| Access | HTTP/S | Single EC2 | Multiple EC2 |
| AZ scope | Region-wide | Single AZ | Multi-AZ |
| Scales automatically | ✅ | ❌ | ✅ |
| Use case | Files/backups/web | OS disk/DB | Shared file system |
