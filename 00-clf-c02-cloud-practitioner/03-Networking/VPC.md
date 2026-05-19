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
