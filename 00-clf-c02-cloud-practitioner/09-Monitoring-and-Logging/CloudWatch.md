# CloudWatch — Monitoring & Observability

## What is it?
AWS's central monitoring service. Collects metrics, logs, and events from AWS services and your own applications. Lets you set alarms, create dashboards, and respond to operational changes.

Your monitoring platform (Nagios, Zabbix, Datadog) — but built into AWS and pre-integrated with every AWS service. Collects performance data and alerts you when things go wrong.

---

## Key Concepts
- **Metrics** — numerical time-series data (CPU usage, network I/O,
  request count, error rate). Every AWS service publishes metrics.
- **Logs** — text records of events from applications and services.
  Stored in Log Groups and Log Streams.
- **Alarms** — trigger actions when a metric crosses a threshold
  (e.g., send SNS notification, trigger Auto Scaling)
- **Dashboards** — visual display of metrics and alarms
- **Events / EventBridge** — respond to state changes in AWS services
  (e.g., EC2 state change → trigger Lambda)

## Default Metrics CloudWatch Collects for EC2
- CPU utilisation
- Network in/out
- Disk read/write (for instance store)

> Note: Memory utilisation and disk space on EBS are NOT collected
> by default — you need to install the CloudWatch Agent on the instance.

## When to Use It
- Monitor EC2, RDS, Lambda, and any AWS service
- Set billing alarms to avoid unexpected charges
- Troubleshoot performance issues
- Trigger Auto Scaling based on metrics
- Centralise application logs

---

## 💡 Good to Know
- **CloudWatch** = metrics and logs (what is happening RIGHT NOW)
- **CloudTrail** = API audit log (who did what and when)
- Standard monitoring = metric every 5 minutes (free)
  Detailed monitoring = metric every 1 minute (additional cost)
- CloudWatch Logs can retain logs for as long as you configure —
  useful for compliance and troubleshooting
- CloudWatch Agent is needed on EC2 to collect memory and disk metrics

---

## ⚠️ Easy to Mix Up
- **CloudWatch** (performance metrics + logs + alarms)
  vs **CloudTrail** (API call audit trail)
  These are the most commonly confused pair in CLF-C02.
- EC2 memory utilisation is NOT a default CloudWatch metric —
  you need the CloudWatch Agent installed