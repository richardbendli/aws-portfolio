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
