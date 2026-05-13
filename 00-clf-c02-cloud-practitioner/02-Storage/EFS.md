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
