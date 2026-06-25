# AWS Global Infrastructure

## Key Components — Know the Hierarchy

```
Regions
  └── Availability Zones (AZs)
        └── Data Centres
Edge Locations (separate infrastructure, more numerous)
Local Zones (extension of regions, fewer locations)
```

---

## Regions
- Geographic area containing multiple AZs (e.g., eu-west-2 = London)
- **34+ regions** worldwide and growing
- Most AWS services are region-scoped
- **How to choose a region:**
  - **Compliance/data sovereignty** — data must stay in a specific
    country (e.g., UK → eu-west-2)
  - **Latency** — deploy closest to your users
  - **Service availability** — not all services available in all regions
  - **Pricing** — varies by region (same service can cost differently)

## Availability Zones (AZs)
- One or more discrete data centres with independent power,
  cooling, and networking
- **3-6 AZs per region** (usually 3)
- Connected by low-latency, high-bandwidth private links
- Isolated from failures in other AZs — different power grids,
  flood zones, and physical locations
- Identified as: eu-west-2a, eu-west-2b, eu-west-2c

## Data Centres
- Physical buildings housing AWS servers
- Multiple data centres per AZ (you don't interact with these directly)

## Edge Locations
- **400+ globally** — far more than regions or AZs
- Used by CloudFront (CDN) and Route 53 (DNS)
- Cache content close to end users to reduce latency
- NOT used to run EC2 or other compute services

## Local Zones
- Extension of a region placed closer to large population centres
- Used for workloads needing single-digit millisecond latency
  (e.g., gaming, media rendering, real-time applications)

---

## 💡 Good to Know
- **Edge Locations > AZs > Regions** — in terms of count
- AZs are physically separated — different power sources and
  flood zones — so an AZ failure is isolated
- An AZ is NOT one data centre — it can be multiple data centres
  that operate as one unit
- **Global services** (not region-specific): IAM, Route 53,
  CloudFront, WAF
- **Regional services**: EC2, VPC, S3, RDS

---

## ⚠️ Easy to Mix Up
- **Edge Locations** are for CloudFront CDN and DNS caching —
  NOT for running EC2 or other compute workloads
- **AZ** ≠ one data centre — it is one or more data centres
  operating as a logical unit
- Choosing a region: compliance and data residency requirements
  always take priority over other factors