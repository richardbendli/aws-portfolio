# NAT Gateway — Network Address Translation Gateway

## What is it?
Allows EC2 instances in **private subnets** to initiate outbound connections to the internet, while preventing inbound connections from the internet.

Your PAT (Port Address Translation) firewall rule — internal servers can reach the internet to download updates, but external users can't reach them directly. Classic outbound-only NAT.

---
