# Subnets

## What is it?
A subdivision of VPC's IP range, tied to a single Availability Zone.
Individual VLANs or network segments within your data centre, each in a specific physical location (AZ).

---

## Key Concepts
- Each subnet lives in **one AZ only**
- **Public Subnet** — has a route to an Internet Gateway.
  Resources can communicate with the internet.
- **Private Subnet** — no route to IGW. Resources cannot be directly reached from the internet.
- Subnet CIDR must be within the VPC CIDR range
- AWS reserves **5 IP addresses** per subnet (first 4 + last 1)

## 💡 Good to Know
- A public subnet alone doesn't make an EC2 instance internet-accessible.
  The instance also needs a **public IP** assigned.
- Subnets span **one AZ** — VPC spans the whole region
- For high availability: spread resources across subnets in **multiple AZs** so an AZ failure doesn't take down your app
- The 5 reserved IPs are: network address, VPC router, DNS, future use, and broadcast. You cannot assign these to resources.

---

## ⚠️ Easy to Mix Up
- A subnet in AZ-a and a subnet in AZ-b are **different subnets**, even if they are in the same VPC
- AWS reserves 5 IPs per subnet — remember to subtract these when calculating usable host addresses
- "Public subnet" just means it has a route to an IGW — the EC2 instance still needs a public IP to actually be reachable
