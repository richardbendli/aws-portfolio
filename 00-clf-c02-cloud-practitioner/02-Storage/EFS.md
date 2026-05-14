# EFS — Elastic File System

## What is it?
Managed NFS (Network File System) that can be mounted by multiple EC2 instances simultaneously across multiple AZs.

Like data centre NFS share or NAS — multiple servers mount the same shared file system concurrently. EFS is the AWS equivalent, fully managed.

---

## Key Concepts
- **Shared file storage** — multiple EC2 instances can mount the
  same EFS simultaneously
- Works across **multiple AZs** in a region
- **Automatically scales** — grows and shrinks as you add/remove files.
  No capacity management required.
- Linux only (NFS protocol)
- More expensive per GB than EBS

## When to Use It ✅
- Shared storage across multiple EC2 instances
- Content management systems (WordPress, Drupal)
- Web server farms sharing the same files
- Home directories for multiple users

## When NOT to Use It ❌
- Windows instances → use FSx for Windows File Server instead
- Single EC2 instance storage → use EBS (cheaper)
- Object storage → use S3

---

## 💡 Good to Know
- EFS automatically scales — you never provision capacity or worry
  about running out of space
- EFS works across **multiple AZs** — this makes it more resilient
  than EBS (which is tied to a single AZ)
- EFS is Linux-only because it uses the NFS protocol.
  Windows requires FSx for Windows File Server.
- EFS is more expensive than EBS per GB — only use it when you
  genuinely need shared access across multiple instances

---

## ⚠️ Easy to Mix Up
- **EFS** (multi-instance, multi-AZ, Linux only)
  vs **EBS** (single instance, single AZ, any OS)
- EFS is Linux-only — Windows needs FSx (a different service entirely)

---

## Storage Comparison Cheat Sheet
| Feature | S3 | EBS | EFS |
|---|---|---|---|
| Type | Object | Block | File (NFS) |
| Access | HTTP/HTTPS | Single EC2 | Multiple EC2 |
| AZ scope | Region-wide | Single AZ | Multi-AZ |
| Scales automatically | ✅ | ❌ | ✅ |
| Use case | Files/backups/web | OS disk/DB | Shared file system |
