# Route Tables

## What is it?
A set of rules (routes) that determine where network traffic is directed within your VPC.

Your physical router's routing table — entries that say "traffic for this destination goes via this next hop."

---

## Key Concepts
- Every subnet must be associated with a route table
- **Main Route Table** — default table, applied to subnets not
  explicitly associated with another table
- **Local route** (e.g., 10.0.0.0/16 → local) always exists —
  traffic within the VPC always routes locally and cannot be removed
- Add a route: **0.0.0.0/0 → IGW** = makes subnet **public**
- Add a route: **0.0.0.0/0 → NAT Gateway** = private subnet
  with outbound internet access

## 💡 Good to Know
- A route to **0.0.0.0/0 → IGW** = public subnet
- A route to **0.0.0.0/0 → NAT Gateway** = private subnet
  with outbound-only internet access
- Multiple subnets can share one route table
- The local route always takes priority — you cannot accidentally
  route internal VPC traffic to the internet

---

## ⚠️ Easy to Mix Up
- The local route cannot be modified or deleted
- A subnet with NO explicit route table association uses the
  main route table — this can be a security risk if the main
  route table has an IGW route
