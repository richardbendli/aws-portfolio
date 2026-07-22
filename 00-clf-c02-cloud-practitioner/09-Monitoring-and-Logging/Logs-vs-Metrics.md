# Logs vs Metrics — What's the Difference?

## Metrics — Numbers Over Time

**What they are:** Numerical data points collected at regular intervals.
They measure HOW MUCH of something is happening.

**Characteristics:**
- Always a number
- Collected at set intervals (every 1 or 5 minutes)
- Low storage cost
- Easy to graph, alert on, and aggregate
- Great for dashboards and alarms

**Examples:**
- EC2 CPU utilisation: 45%
- S3 bucket size: 120GB
- Lambda invocations: 5,432 per minute
- RDS connections: 87

---

## Logs — Text Records of Events

**What they are:** Timestamped text entries describing what happened.
They record WHAT happened and WHY.

**Characteristics:**
- Free-form text or structured JSON
- Written at the time of an event
- Higher storage cost
- Best for debugging and investigation
- Great for troubleshooting specific issues

**Examples:**
- "2026-04-30 10:23:41 ERROR: Database connection timeout"
- "GET /api/users 200 OK 142ms"
- "User john@example.com logged in from 203.0.113.42"

---
