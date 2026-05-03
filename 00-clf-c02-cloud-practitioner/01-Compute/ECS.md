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

## 💡 Good to Know
- ECS with **Fargate** = serverless containers (no EC2 instances to manage)
- ECS vs EKS: ECS is AWS-native and simpler. EKS is managed Kubernetes
  for teams already using Kubernetes.
- At CLF-C02 level: know what ECS does and when you'd choose it —
  deep configuration is not required.
- Fargate is NOT the same as Lambda. Fargate runs containers,
  Lambda runs individual functions.

---

## ⚠️ Easy to Mix Up
- **Fargate** ≠ **Lambda** — both are serverless but:
  Fargate = containerised workloads
  Lambda = short event-driven functions
- **ECS** ≠ **EKS** — ECS is AWS-native, EKS is managed Kubernetes

