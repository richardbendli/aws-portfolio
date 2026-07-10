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

## When to Use It ✅
- Monitor EC2, RDS, Lambda, and any AWS service
- Set billing alarms to avoid unexpected charges
- Troubleshoot performance issues
- Trigger Auto Scaling based on metrics
- Centralise application logs

---
