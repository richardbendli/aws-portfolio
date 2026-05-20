# VPC — Virtual Private Cloud

## What is it?

Private, logically isolated network within AWS. All AWS resources live inside a VPC.

Private VLAN infrastructure or private network segment in the data centre. You define the IP ranges, subnets, routing, and firewalls — just like you do physically, but in software.

---

## Key Concepts
- **CIDR Block** — IP address range for your VPC (e.g., 10.0.0.0/16)
- **Subnets** — subdivisions of the VPC CIDR, tied to a specific AZ
- **Route Table** — controls where traffic is directed
- **Internet Gateway (IGW)** — connects VPC to the internet
- **NAT Gateway** — allows private subnets to reach internet outbound only
- **Security Groups** — instance-level virtual firewall, stateful
- **NACLs** — subnet-level firewall, stateless
- **VPC Peering** — connect two VPCs privately (non-transitive)
- **Default VPC** — AWS creates one per region automatically. Safe to use for learning and testing.

---

## When to Use It ✅
- Every AWS deployment uses a VPC — it is foundational
- Isolate environments (dev/test/prod in separate VPCs)
- Control network traffic flow and security between resources

---

## 💡 Good to Know
- VPC is **region-specific** — spans all AZs in that region
- **Subnets** are **AZ-specific** — a subnet exists in only one AZ
- A **public subnet** has a route to an IGW. A **private subnet** does not.
- Default VPC exists in every region — AWS creates it for you
- **Security Groups** = stateful, instance level
- **NACLs** = stateless, subnet level
- **VPC Peering** is NOT transitive — if A peers with B, and B peers with C, then A cannot reach C through B. A needs its own peering with C.

---

## ⚠️ Easy to Mix Up
- VPC spans a **region** — subnets span a single **AZ**
- Security Groups are stateful — NACLs are stateless. This distinction is heavily tested.
- VPC Peering is non-transitive — a common exam scenario

---

## VPC Architecture — Basic Pattern
```
VPC (10.0.0.0/16) — London Region
├── Public Subnet (10.0.1.0/24) — AZ-a
│   └── EC2 Web Server → Internet Gateway → Internet
├── Public Subnet (10.0.2.0/24) — AZ-b
│   └── EC2 Web Server
├── Private Subnet (10.0.3.0/24) — AZ-a
│   └── EC2 App Server → NAT Gateway → Internet (outbound only)
└── Private Subnet (10.0.4.0/24) — AZ-b
    └── RDS Database (no internet access)
```
