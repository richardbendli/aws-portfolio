# CloudTrail — API Audit Logging

## What is it?
Records every API call made in your AWS account — who did what, when, from where, and with what result. Your complete audit trail.

Like SIEM or syslog server capturing all admin actions — every SSH login, every config change, every command run.
Except CloudTrail captures every AWS API call automatically.

---

## Key Concepts
- Every action in AWS (console click, CLI command, SDK call)
  is an API call — CloudTrail records all of them
- Logs include: **who** made the call (IAM user/role), **what** action,
  **when** (timestamp), **from where** (IP address), and the **result**
- **Event History** — last 90 days of management events, free, in console
- **Trails** — configure longer retention by sending logs to S3
- **Management Events** — API calls on AWS resources
  (create EC2, delete S3 bucket, etc.)
- **Data Events** — object-level activity (S3 object reads/writes,
  Lambda invocations) — not enabled by default, additional cost
- **CloudTrail Insights** — detect unusual API activity automatically

## When to Use It ✅
- Security investigations (who deleted that S3 bucket?)
- Compliance auditing (prove what changes were made and when)
- Operational troubleshooting (what changed before this broke?)
- Detecting unauthorised access or unusual activity

---

## 💡 Good to Know
- CloudTrail is enabled by default for **90 days** of event history
  in every AWS account — you don't have to do anything
- To retain logs beyond 90 days, create a Trail that ships to S3
- CloudTrail logs are the primary source of truth for
  **"who did what"** in AWS — critical for security and compliance
- KMS can encrypt your CloudTrail logs at rest
- CloudTrail is NOT real-time monitoring — there can be up to
  15 minutes delay for log delivery

---

## ⚠️ Easy to Mix Up
- **CloudTrail** (API audit trail — who did what)
  vs **CloudWatch** (metrics and performance — what is happening)
  This is one of the most tested distinctions in CLF-C02.
- CloudTrail records API calls — not OS-level or application-level
  events. For those, you need CloudWatch Logs + an agent.
