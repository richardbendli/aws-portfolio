# AWS Well-Architected Framework

## What is it?
AWS's best practices framework for designing and operating reliable, secure, efficient, cost-effective, and sustainable cloud systems.
Based on six pillars.

---

## The Six Pillars — Know All Six

| Pillar | Focus | Key Service Examples |
|---|---|---|
| **Operational Excellence** | Run, monitor, and improve systems and processes | CloudWatch, CloudTrail, Systems Manager |
| **Security** | Protect data, systems, and assets | IAM, KMS, Shield, WAF, CloudTrail |
| **Reliability** | Recover from failure, meet demand consistently | Multi-AZ, Auto Scaling, Backups, Route 53 |
| **Performance Efficiency** | Use resources efficiently, adapt to change | Right-sizing, Lambda, CloudFront, Aurora |
| **Cost Optimisation** | Avoid unnecessary costs | Reserved Instances, Spot, Cost Explorer |
| **Sustainability** | Minimise environmental impact of workloads | Right-sizing, serverless, efficient architectures |

> Sustainability was added as the **6th pillar in 2021** — know this.

---

## AWS Trusted Advisor
AWS's automated tool that checks your account against Well-Architected
best practices across 5 categories:
- Cost Optimisation
- Performance
- Security
- Fault Tolerance
- Service Limits

**Basic/Developer plans:** Limited checks (core security + service limits)
**Business/Enterprise plans:** All checks + API access

---

## AWS Well-Architected Tool
A free interactive tool in the AWS console that walks you through
the six pillars and evaluates your architecture against best practices.
Produces a report with identified risks and improvement recommendations.

---

## Design Principles for Reliability
- **Design for failure** — assume components will fail. Build accordingly.
- **Multi-AZ** — spread across AZs to survive AZ-level failures
- **Auto Scaling** — automatically replace failed or overloaded instances
- **Loose coupling** — use queues (SQS) between components so one
  failure doesn't cascade

---