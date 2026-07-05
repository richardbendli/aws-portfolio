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