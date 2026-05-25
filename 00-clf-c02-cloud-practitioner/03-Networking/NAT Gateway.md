# NAT Gateway — Network Address Translation Gateway

## What is it?
Allows EC2 instances in **private subnets** to initiate outbound connections to the internet, while preventing inbound connections from the internet.

Your PAT (Port Address Translation) firewall rule — internal servers can reach the internet to download updates, but external users can't reach them directly. Classic outbound-only NAT.

---

## Key Concepts
- Lives in a **public subnet** (not the private subnet it serves)
- Private subnet route table points to NAT Gateway for 0.0.0.0/0
- AWS-managed — highly available within an AZ
- For full HA: deploy a **NAT Gateway in each AZ** — otherwise a single NAT Gateway is a single point of failure for that AZ
- Has an Elastic IP automatically assigned

## When to Use It ✅
- Private EC2 instances need to download updates or patches
- Private instances need to call external APIs
- Any outbound-only internet access from private resources

## When NOT to Use It ❌
- Need full bidirectional internet → use Internet Gateway (and put instance in a public subnet)

---

## 💡 Good to Know
- NAT Gateway lives in a **public subnet** but serves instances in **private subnets** — this confuses people
- **Outbound only** — the internet cannot initiate connections to private instances through a NAT Gateway
- **NAT Gateway** (AWS managed, preferred) vs **NAT Instance** (self-managed EC2 running NAT software, legacy approach).
  Always choose NAT Gateway for new deployments.
- You pay per hour + per GB of data processed through the NAT Gateway

---

## ⚠️ Easy to Mix Up
- NAT Gateway itself lives in a **PUBLIC** subnet — not the private one
- NAT Gateway ≠ Internet Gateway:
  IGW = bidirectional, public subnets
  NAT GW = outbound only, serves private subnets
