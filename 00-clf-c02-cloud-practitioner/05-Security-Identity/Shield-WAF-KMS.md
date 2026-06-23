# Shield, WAF & KMS

---

# Shield — AWS DDoS Protection

## What is it?
Managed DDoS (Distributed Denial of Service) protection for AWS applications

## Key Concepts
- **Shield Standard** — FREE. Automatically applied to all AWS
  accounts. Protects against common Layer 3/4 DDoS attacks.
- **Shield Advanced** — Paid (~$3,000/month). Enhanced protection,
  24/7 DDoS Response Team (DRT), cost protection for scaling
  costs incurred during an attack.

## 💡 Good to Know
- Shield Standard = **free and automatic** — everyone gets it
- Shield Advanced = paid, for high-risk or mission-critical applications
- Pairs with CloudFront and Route 53 for edge protection
- Shield Advanced provides detailed attack diagnostics and metrics

## ⚠️ Easy to Mix Up
- Shield = DDoS protection (Layer 3/4)
- WAF = web application threats (Layer 7)
- They work at different layers and complement each other

---

# WAF — Web Application Firewall

## What is it?
Protects web applications from common web exploits (SQL injection,
cross-site scripting, etc.) at Layer 7 (HTTP).

## Data Centre Analogy
Application-layer firewall or reverse proxy with WAF rules — like
a ModSecurity rule set in front of your web servers.

## Key Concepts
- Works at **Layer 7** (application layer — HTTP/HTTPS)
- Deployed on: CloudFront, Application Load Balancer, API Gateway
- Create **Web ACLs** with rules to allow, block, or count requests
- Can block by IP address, geographic location, request patterns,
  request size, or known malicious signatures

## 💡 Good to Know
- WAF = Layer 7 (HTTP) — protects against web application attacks
- Shield = Layer 3/4 — protects against network-level DDoS
- **WAF + Shield + CloudFront** = full edge protection stack
- AWS Managed Rules are pre-built rule groups you can enable quickly

## ⚠️ Easy to Mix Up
- WAF protects against application attacks (SQL injection, XSS)
  not network floods — that is Shield's job

---

# KMS — Key Management Service

## What is it?
Create and manage encryption keys used to encrypt your data
across AWS services.

## Data Centre Analogy
Your HSM (Hardware Security Module) or key management system —
centralised place to create, store, and control cryptographic keys.

## Key Concepts
- **CMK (Customer Master Key)** — your encryption key, stored in KMS
- Integrates with S3, EBS, RDS, Lambda, and most AWS services
- **AWS-managed keys** — created and managed by AWS on your behalf
- **Customer-managed keys** — you create, control, and set rotation policy
- All key usage is logged in CloudTrail for full audit trail

## 💡 Good to Know
- KMS manages encryption **keys** — it does not store your data
- Encryption at rest for EBS, S3, RDS → all can use KMS keys
- KMS falls under the **customer's** side of the Shared Responsibility
  Model — you are responsible for enabling and managing encryption
- You can set automatic key rotation for customer-managed keys

## ⚠️ Easy to Mix Up
- KMS stores and manages **keys**, not the data itself
- AWS-managed keys vs customer-managed keys:
  AWS-managed = simpler, less control
  Customer-managed = more control, more responsibility