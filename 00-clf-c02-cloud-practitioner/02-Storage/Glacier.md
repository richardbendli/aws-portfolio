# S3 Glacier — Archive Storage

## What is it?
Low-cost archival storage for data that is rarely accessed but must be retained for long periods. Part of the S3 storage class family.

Like an offsite tape backup library — very cheap to store, but takes time to retrieve. You keep data there knowing you probably won't need it for months or years.

---

## Glacier Storage Classes

| Class | Retrieval Time | Best For | Cost |
|---|---|---|---|
| **S3 Glacier Instant Retrieval** | Milliseconds | Accessed ~once per quarter | Low |
| **S3 Glacier Flexible Retrieval** | Minutes to 12 hours | Accessed 1-2x per year | Very low |
| **S3 Glacier Deep Archive** | Up to 12 hours | Long-term retention, rarely accessed | Lowest |

## Retrieval Options for Glacier Flexible
- **Expedited** — 1-5 minutes (higher cost)
- **Standard** — 3-5 hours (default)
- **Bulk** — 5-12 hours (cheapest)

## When to Use It ✅
- Compliance and regulatory data retention (e.g., keep records for 7 years)
- Old backups you're required to keep but rarely access
- Media archives
- Scientific or research data

## When NOT to Use It ❌
- Data you need to access quickly or frequently → use S3 Standard
- Active working data → use S3 Standard or Standard-IA

---
