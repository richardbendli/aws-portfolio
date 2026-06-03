# Security Groups

## What is it?
A virtual stateful firewall that controls inbound and outbound traffic at the **EC2 instance level**.

Host-based firewall rules on an individual server — like Windows Firewall or iptables rules applied per machine.

---

## Key Concepts
- Applied at the **instance (ENI) level**
- **Stateful** — if inbound traffic is allowed, return traffic is
  automatically allowed without needing a separate outbound rule
- **Allow rules only** — you cannot create explicit deny rules
- Default behaviour: all inbound DENIED, all outbound ALLOWED
- Can reference other security groups (e.g., allow traffic from
  SG-WebServer to reach SG-Database)
- Multiple security groups can be attached to one instance

## 💡 Good to Know
- Security Groups are **STATEFUL** — this is the key fact to remember
- Because they're stateful, you only need to write rules for the
  direction you initiate traffic. Return traffic is handled automatically.
- Security Groups can only **allow** — they cannot block specific IPs.
  If you need to block an IP, use a NACL instead.
- Security Groups are applied per ENI (Elastic Network Interface),
  not per subnet

---

## ⚠️ Easy to Mix Up
- **Security Groups** (instance level, stateful, allow only)
  vs **NACLs** (subnet level, stateless, allow + deny)
- Stateful means you do NOT need an outbound rule to allow
  responses to allowed inbound traffic

---

## Security Groups vs NACLs — Quick Comparison
| Feature | Security Group | NACL |
|---|---|---|
| Level | Instance (ENI) | Subnet |
| State | Stateful | Stateless |
| Rules | Allow only | Allow + Deny |
| Rule order | All rules evaluated | Numbered order, first match wins |
| Default | Deny all inbound | Allow all |
