# Load Balancers & Auto Scaling — ELB & ASG

## What is it?
**Elastic Load Balancing (ELB)** distributes incoming traffic across multiple targets (EC2 instances, containers, IPs) to ensure no single server is overwhelmed.
`ELB = your hardware load balancer (F5, HAProxy) sitting in front of your server farm, distributing requests.`

**Auto Scaling Groups (ASG)** automatically add or remove EC2 instances based on demand — keeping your application available and cost-efficient.
`ASG = automated capacity management — like having an ops team that spins up servers when traffic spikes and removes them when it drops.`

---

## ELB — Types of Load Balancers

| Type | Layer | Best For |
|---|---|---|
| **ALB (Application Load Balancer)** | Layer 7 (HTTP/HTTPS) | Web apps, microservices, path-based routing |
| **NLB (Network Load Balancer)** | Layer 4 (TCP/UDP) | Ultra-high performance, static IP, gaming, IoT |
| **GLB (Gateway Load Balancer)** | Layer 3 | Third-party security appliances (firewalls, IDS) |
| **CLB (Classic Load Balancer)** | Layer 4 & 7 | Legacy — avoid for new deployments |

## Key ELB Concepts
- **Target Group** — the set of targets (EC2 instances) the LB routes to
- **Health Checks** — LB regularly checks if targets are healthy.
  Unhealthy targets stop receiving traffic automatically.
- **Listener** — rules that define how the LB routes incoming requests
- ELB is a **managed service** — AWS handles availability and scaling

## Auto Scaling Group (ASG) Key Concepts
- **Minimum capacity** — always keep at least N instances running
- **Desired capacity** — the target number of instances
- **Maximum capacity** — never exceed N instances
- **Scaling policies** — rules that trigger scale out/in
  (e.g., add instance when CPU > 70%)
- **Launch Template** — defines what kind of EC2 instance to launch

## When to Use Them ✅
- Any production application needing high availability
- Handling unpredictable or variable traffic
- Distributing load across multiple AZs for resilience
- Reducing cost by scaling in during low traffic periods

---

## 💡 Good to Know
- ALB is the most commonly used — it understands HTTP and can route
  based on URL path (e.g., /api → one target group, /web → another)
- NLB handles millions of requests per second with ultra-low latency
- ELB + ASG together = the standard AWS high availability pattern
- ASG can automatically replace unhealthy EC2 instances
- Load balancers work across **multiple AZs** — this is how you
  achieve high availability in AWS

---

## ⚠️ Easy to Mix Up
- **ALB** (Layer 7, HTTP) vs **NLB** (Layer 4, TCP) — ALB is almost
  always the right choice for web applications
- **High Availability** (fast recovery, multi-AZ) ≠
  **Fault Tolerance** (no interruption at all)
- ASG **scaling out** = adding instances. ASG **scaling in** = removing instances.

---

## ELB + ASG Architecture Pattern
```
Internet
    ↓
[Application Load Balancer]
    ↓           ↓           ↓
[EC2 AZ-a]  [EC2 AZ-b]  [EC2 AZ-c]
        ← Auto Scaling Group →
```
