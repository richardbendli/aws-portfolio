# 🐳 ECS — Elastic Container Service

## What is it?
AWS's managed container orchestration service. Run Docker containers
without managing the underlying cluster infrastructure.

---

## Key Concepts
- **Task** — a running container (or group of containers)
- **Task Definition** — blueprint for your container (image, CPU, memory, ports)
- **Cluster** — logical grouping of tasks/services
- **Service** — maintains a desired number of running tasks
- **Launch Types:**
  - **EC2 Launch Type** — you manage the underlying EC2 instances
  - **Fargate Launch Type** — fully serverless, AWS manages the hosts

## When to Use It ✅
- Running containerised (Docker) workloads
- Microservices architectures
- When you want managed container orchestration on AWS

## When NOT to Use It ❌
- Non-containerised apps → use EC2
- Short event-driven functions → use Lambda

---

