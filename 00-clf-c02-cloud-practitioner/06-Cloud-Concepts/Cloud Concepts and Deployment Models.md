# Cloud Computing Concepts

## What is Cloud Computing?
On-demand delivery of IT resources over the internet with pay-as-you-go pricing. You access technology services — such as computing power, storage, and databases — as needed, without owning or managing physical data centres.

---

## 6 Advantages of Cloud Computing
> AWS's official list — these appear frequently on the exam

1. **Trade fixed expense for variable expense** — pay only for
   what you use, no upfront hardware investment
2. **Benefit from massive economies of scale** — AWS's buying
   power means lower prices passed on to you
3. **Stop guessing capacity** — scale up or down as needed,
   no over-provisioning or under-provisioning
4. **Increase speed and agility** — new resources available in
   minutes, not weeks of hardware procurement
5. **Stop spending money running and maintaining data centres**
   — focus your resources on your business, not infrastructure
6. **Go global in minutes** — deploy in multiple regions worldwide
   instantly with minimal effort

---

## Cloud Service Models

| Model | You Manage | AWS Manages | Example |
|---|---|---|---|
| **IaaS** (Infrastructure as a Service) | OS, middleware, app, data | Hardware, network, virtualisation | EC2 |
| **PaaS** (Platform as a Service) | App, data | Everything below the app | Elastic Beanstalk, RDS |
| **SaaS** (Software as a Service) | Just your data/config | Everything | Gmail, Salesforce |

## Cloud Deployment Models

| Model | Description | Example |
|---|---|---|
| **Public Cloud** | Everything runs on AWS infrastructure | Standard AWS usage |
| **Private Cloud** | Cloud-like environment on-premises | VMware private cloud |
| **Hybrid Cloud** | Mix of on-premises + public cloud | AWS Direct Connect to data centre |

---

## 💡 Good to Know
- Know all **6 advantages** — they come up frequently and are
  sometimes tested by describing the benefit without naming it
- **Hybrid cloud** = on-premises + AWS — common in enterprises
  transitioning to cloud gradually
- **Elasticity** = automatically scale up AND down with demand
- **Agility** = speed of deploying new resources
- **High Availability** = system stays up even if components fail
  (fast recovery via multi-AZ)
- **Fault Tolerance** = system continues with NO interruption
  even if components fail (stronger than just HA)

---

## ⚠️ Easy to Mix Up
- **High Availability** ≠ **Fault Tolerant**
  HA = fast recovery from failure
  FT = no interruption during failure (stricter requirement)
- **Scalability** (handle growth) ≠ **Elasticity** (scale up AND
  down automatically in response to real-time demand)