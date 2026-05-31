# NACLs — Network Access Control Lists

## What is it?
A stateless firewall applied at the **subnet level**, controlling traffic in and out of subnets.

ACLs on a router or switch — applied at the network boundary, not the host. Stateless means each packet is evaluated independently with no connection tracking.

---

## Key Concepts
- Applied at the **subnet level** — affects all resources in the subnet
- **Stateless** — you must explicitly allow both inbound AND outbound traffic (including return/response traffic)
- Supports both **ALLOW and DENY** rules
- Rules are evaluated in **numerical order** — lowest number first, first match wins
- Default NACL: allows all inbound and all outbound traffic

## 💡 Good to Know
- NACLs are the only way to explicitly **DENY** traffic in a VPC — Security Groups cannot deny, only allow
- Because NACLs are stateless, if you allow inbound port 80, you also need an outbound rule for ephemeral ports (1024-65535) to allow the response back to the client
- Rules are processed in **numerical order** — a DENY rule at number 100 will block traffic even if there's an ALLOW rule at 200
- NACLs are useful for quickly blocking a specific IP address

---

## ⚠️ Easy to Mix Up
- NACLs are **STATELESS** — you must add rules for BOTH directions
- If you allow inbound port 80 but forget the outbound ephemeral port rule, responses will be blocked
- Default NACL = allows everything. Custom NACL = denies everything until you add allow rules.

---

## Security Groups vs NACLs — Quick Comparison
| Feature | Security Group | NACL |
|---|---|---|
| Level | Instance (ENI) | Subnet |
| State | Stateful | Stateless |
| Rules | Allow only | Allow + Deny |
| Rule order | All rules evaluated | Numbered order, first match wins |
| Default | Deny all inbound | Allow all |
