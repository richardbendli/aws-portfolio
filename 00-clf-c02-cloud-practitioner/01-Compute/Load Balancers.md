# Load Balancers & Auto Scaling — ELB & ASG

## What is it?
**Elastic Load Balancing (ELB)** distributes incoming traffic across multiple targets (EC2 instances, containers, IPs) to ensure no single server is overwhelmed.
`ELB = your hardware load balancer (F5, HAProxy) sitting in front of your server farm, distributing requests.`

**Auto Scaling Groups (ASG)** automatically add or remove EC2 instances based on demand — keeping your application available and cost-efficient.
`ASG = automated capacity management — like having an ops team that spins up servers when traffic spikes and removes them when it drops.`

---
