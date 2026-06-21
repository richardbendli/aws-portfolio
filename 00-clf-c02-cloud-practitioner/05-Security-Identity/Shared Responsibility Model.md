# Shared Responsibility Model

## What is it?
Defines what AWS is responsible for securing vs what you (the customer) are responsible for securing.

## The Core Rule
> **AWS:** Security **OF** the cloud
> **You:** Security **IN** the cloud

---

## AWS Responsibility — Security OF the Cloud
AWS manages and secures the underlying **infrastructure**:
- Physical data centres (buildings, power, cooling, physical security)
- Hardware (servers, storage, networking equipment)
- Virtualisation layer (hypervisor)
- Managed service infrastructure (e.g., patching RDS DB engine)
- Global network infrastructure

## Customer Responsibility — Security IN the Cloud
You are responsible for everything you put **in** the cloud:
- Data encryption (at rest and in transit)
- IAM — who has access to what
- OS patching on EC2 instances
- Application security and code
- Security Group and NACL configuration
- Any configuration you make in AWS services

---

## How It Changes by Service Type
| Service Type | Example | AWS Manages | You Manage |
|---|---|---|---|
| **IaaS** | EC2 | Hardware, hypervisor | OS, patching, app, data |
| **PaaS** | RDS | Hardware, OS, DB engine | Data, users, access config |
| **SaaS** | S3 | Everything infrastructure | Data, access policies, encryption |

---

## 💡 Good to Know
- This model is tested heavily — know it thoroughly
- **RDS:** AWS patches the DB engine and OS. You manage the data
  and control who can access it.
- **EC2:** You are responsible for OS patching, not AWS.
- **S3:** AWS secures the infrastructure. You control who can
  access your data via bucket policies and IAM.
- Encryption is almost always the **customer's** responsibility
  — AWS provides the tools (KMS), you decide to use them.

---

## ⚠️ Easy to Mix Up
- "Who patches the OS on an EC2 instance?" → **You** (customer)
- "Who patches the MySQL engine on RDS?" → **AWS**
- "Who is responsible for physical data centre security?" → **AWS**
- Encryption at rest — AWS provides KMS, but enabling encryption
  on your data is your responsibility
