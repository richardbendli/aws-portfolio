## What is it?

A horizontally scaled, redundant AWS-managed gateway that connects VPC to the public internet.
Edge/Border router or firewall that connects internal network to the internet.
The single point where your private network meets the public internet.

---

## Key Concepts
- **One IGW per VPC** — you cannot attach multiple IGWs to one VPC
- Attached to the VPC itself, not a specific subnet
- Enables **inbound AND outbound** internet connectivity
- To make a subnet public: attach IGW to VPC + add route (0.0.0.0/0 → IGW) in the subnet's route table

## 💡 Good to Know
- IGW = bidirectional internet access (used by public subnets)
- NAT Gateway = outbound only internet access (used by private subnets)
- IGW is free to use — you pay only for data transfer out
- IGW is fully managed and highly available by default — you don't need to worry about it failing

---

## ⚠️ Easy to Mix Up
- **IGW** (bidirectional, public subnets) vs **NAT Gateway** (outbound only, private subnets)
- Attaching an IGW to a VPC is not enough alone — you also need a route in the subnet's route table pointing to it

---