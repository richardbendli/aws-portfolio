# AWS Billing & Pricing

## Core Pricing Principles
- **Pay for what you use** — no upfront commitment required
- **Pay less when you reserve** — Reserved Instances, Savings Plans
- **Pay less with volume** — S3 tiered pricing, data transfer discounts
- **Free tier** — 12 months free for most new accounts +
  always-free services that never expire

---

## Key Billing Tools

### AWS Pricing Calculator
- Estimate costs **before** deploying anything
- URL: calculator.aws
- Build architecture scenarios and compare costs

### AWS Cost Explorer
- Visualise and analyse your **actual** past and current spending
- Identify cost trends and top services by spend
- Forecast future costs based on usage patterns

### AWS Budgets
- Set **alerts** when spending exceeds or is forecast to exceed thresholds
- Proactively warns you before overspending — not just after
- Alert types: cost, usage, reservation utilisation, coverage

### AWS Cost and Usage Report (CUR)
- Most detailed billing data available
- Used for in-depth cost analysis and third-party tools

### Billing Dashboard
- Overview of current month charges
- Single entry point to all billing tools

---

## Support Plans
| Plan | Price | Response Time (Critical) | Key Feature |
|---|---|---|---|
| **Basic** | Free | Docs and forums only | Included with every account |
| **Developer** | ~$29/month | 12-24 hours (business hours) | For testing and development |
| **Business** | ~$100/month | 1 hour | Full Trusted Advisor + 24/7 support |
| **Enterprise On-Ramp** | ~$5,500/month | 30 minutes | Pool of TAMs |
| **Enterprise** | ~$15,000/month | 15 minutes | Dedicated TAM |

### Support Plan Key Differentiators
- **Business and above** — access to full **Trusted Advisor** checks
- **Business and above** — 24/7 phone and chat support
- **Enterprise On-Ramp and Enterprise** — access to TAMs
  (Technical Account Managers)
- **Enterprise** — dedicated TAM (not shared)

---

## AWS Free Tier — 3 Types
1. **12-month free** — available for 12 months after account creation
   (e.g., EC2 t2.micro 750hrs/month, S3 5GB)
2. **Always free** — never expire, available to all accounts
   (e.g., Lambda 1M requests/month, DynamoDB 25GB)
3. **Short-term trials** — e.g., 30-day free trial on some services

---

## TCO — Total Cost of Ownership
- AWS Pricing Calculator helps compare on-premises costs vs cloud
- On-premises factors to include: hardware, power, cooling,
  data centre space, networking, and staff time
- Cloud replaces most of those with variable, usage-based costs

---

## 💡 Good to Know
- Know all **5 support plans** and their key differentiators
- **TAM (Technical Account Manager)** = Enterprise support only
- **Trusted Advisor** full checks = Business support and above
  (Basic/Developer only get core security + service limit checks)
- **Cost Explorer** = analyse past and current spending
  **Budgets** = set alerts for future spending thresholds
- **Basic support is free** for all AWS accounts — always

---

## ⚠️ Easy to Mix Up
- **Developer** support = business hours only, NOT 24/7
- Trusted Advisor basic checks = everyone gets them
  Full checks = Business plan and above only
- **Cost Explorer** (analyse what you've spent)
  ≠ **Budgets** (alert when you're about to overspend)
- **Pricing Calculator** (estimate before you deploy)
  ≠ **Cost Explorer** (analyse what you've already spent)