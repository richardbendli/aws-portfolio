# CloudWatch Alarms

## What is it?
CloudWatch Alarms watch a single metric over time and trigger an action when the metric crosses a defined threshold.

Like your Nagios alert rules — "if CPU > 90% for 5 minutes, send a page." Except CloudWatch Alarms can trigger much richer automated responses beyond just notifications.

---

## Key Concepts
- **Metric** — the value being watched (e.g., CPUUtilization)
- **Threshold** — the value that triggers the alarm
  (e.g., CPUUtilization > 80%)
- **Evaluation period** — how many data points to evaluate
- **Alarm states:**
  - **OK** — metric is within threshold
  - **ALARM** — metric has breached threshold
  - **INSUFFICIENT_DATA** — not enough data yet to evaluate

## Alarm Actions (what happens when alarm fires)
- **SNS notification** — send email, SMS, or trigger a Lambda function
- **EC2 action** — stop, terminate, reboot, or recover an instance
- **Auto Scaling action** — scale out (add instances) or scale in
- **Systems Manager** — trigger an automation runbook

## Common Alarm Use Cases
- CPU > 80% for 5 minutes → scale out via Auto Scaling
- Billing charges > $10 → send email via SNS
- RDS CPU > 90% → alert the on-call team
- EC2 StatusCheckFailed → automatically reboot the instance

---

## 💡 Good to Know
- **Billing Alarms** — a specific type of CloudWatch alarm that
  monitors your account charges. Must be set up in **us-east-1**
  (N. Virginia) region, even if your resources are elsewhere.
  This is a common exam gotcha.
- Alarms trigger on **sustained** threshold breaches, not spikes —
  you define how many consecutive periods must breach before alarming
- SNS (Simple Notification Service) is the most common alarm action
  for notifications

---

## ⚠️ Easy to Mix Up
- **Alarms** (metric threshold → action)
  vs **AWS Budgets** (cost threshold → alert)
  Both alert on thresholds but Alarms are for any metric,
  Budgets are specifically for spend
- Billing alarms must be created in **us-east-1** regardless of
  where your resources are — this catches people out