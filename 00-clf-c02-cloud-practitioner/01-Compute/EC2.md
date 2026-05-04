# 🖥️ EC2 —  Amazon Elastic Compute Cloud

## What is it?
Virtual servers in the AWS cloud. You rent compute capacity
(CPU, RAM, storage, networking) billed per hour or per second
depending on instance type.

---

## Key Concepts
- **Instance Types** — families optimised for different workloads
  (t3=general purpose, c6i=compute optimised, r6i=memory optimised,
  i3=storage optimised)
- **AMI (Amazon Machine Image)** — your server template.
  Like a build image or snapshot you clone from to launch new instances.
- **EBS Volume** — virtual hard disk attached to your EC2 instance.
  Persists independently of the instance lifecycle.
- **Key Pair** — SSH keypair for Linux access. For Windows, the Key Pair
  decrypts the auto-generated Administrator password,
  which you then use to RDP in.
- **Security Group** — virtual firewall controlling inbound/outbound
  traffic at the instance level.
- **Elastic IP** — static public IPv4 address you attach to an instance.
  Normal public IPs change on every stop/start. Elastic IPs don't.
- **User Data** — bootstrap script that runs once at first launch.
  Used to install software, run updates, configure the instance
  automatically on startup.
- **Instance Store** — temporary local storage physically attached
  to the host machine. Lost when instance stops or terminates.
  Never use for persistent data.

## When to Use It ✅
- Need full OS-level control
- Long-running applications (web servers, app servers, databases)
- Lift-and-shift migration from a physical data centre
- When you need specific hardware or software configurations

## When NOT to Use It ❌
- Short/event-driven tasks under 15 mins → use Lambda
- Don't want to manage OS patching → use managed services
- Need containers → use ECS or EKS

---

## Pricing Models 💰
| Model | Best For | Saving vs On-Demand |
|---|---|---|
| **On-Demand** | Unpredictable or short-term workloads, no commitment | Baseline price |
| **Reserved — Standard (1 or 3 yr)** | Steady, predictable workloads. Locked to instance family + region | Up to 72% off |
| **Reserved — Convertible (1 or 3 yr)** | Predictable but need flexibility to change instance type or OS | Up to 54% off |
| **Spot Instances** | Fault-tolerant batch jobs — AWS can interrupt with 2-min notice | Up to 90% off |
| **Savings Plans** | Flexible commitment to $/hr spend across instance families | Up to 66% off |
| **Dedicated Instance** | Single-tenant hardware, no other customers on same host | Higher than On-Demand |
| **Dedicated Host** | Full physical server control — needed for BYOL or compliance | Highest cost |

---

## 🌐 Networking
- Every instance always gets a **private IP address**.
  A public IP is optional and assigned automatically if enabled.
- Public IP is **released when you stop** the instance.
  Use an **Elastic IP** if you need a fixed public address.
- EC2 instances must live inside a **subnet** within a **VPC**
- **Elastic Network Interface (ENI)** — the virtual network card
  attached to your instance. You can attach multiple ENIs to a single instance.
- Traffic into and out of your instance is controlled at two layers:
  - Security Group → attached to the instance
  - NACL → attached to the subnet

---

## 💡 Good to Know
- Spot instances are the cheapest option but AWS can reclaim them
  at any time with only a **2-minute warning** — only suitable for
  workloads that can be interrupted (batch processing, data analysis)
- **Standard Reserved** locks you to a specific instance family and region.
  **Convertible Reserved** lets you change instance type, OS or tenancy
  — but the discount is lower
- Reserved Instances reduce cost but **you pay for the commitment
  whether you use it or not**
- EC2 falls under the **IaaS** category —
  Infrastructure as a Service. You manage the OS and above.
  AWS manages the physical hardware and hypervisor.
- **Dedicated Instance** and **Dedicated Host** are not the same thing.
  A Dedicated Host gives you visibility and control of the actual
  physical server — useful for software licensing tied to physical cores.

---

## ⚠️ Easy to Mix Up
- **Instance Store** (temporary, lost on stop/terminate)
  vs **EBS** (persistent, survives stop)
- **Stopping** an instance — ROOT EBS volume is kept,
  public IP is released
- **Terminating** an instance — ROOT EBS volume is deleted by default,
  additional attached EBS volumes are retained by default
- **Security Groups** = instance level, stateful
  (return traffic automatically allowed)
- **NACLs** = subnet level, stateless
  (return traffic must be explicitly allowed)
