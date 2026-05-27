# Route 53

## What is it?
AWS's managed DNS service. Translates domain names (example.com) into IP addresses and routes users to the right AWS resources.

Your internal/external DNS servers — but fully managed, globally distributed, and deeply integrated with AWS services.

---

## Key Concepts
- **Domain registration** — register domains directly in Route 53
- **DNS records** — A, AAAA, CNAME, MX, TXT and others
- **Alias records** — like CNAME but work for root domains
  (e.g., example.com → ALB). Standard CNAMEs cannot be at zone apex.
- **Health checks** — Route 53 checks endpoint health and routes
  traffic away from unhealthy resources automatically
- **Routing Policies:**
  - **Simple** — one resource, straightforward routing
  - **Weighted** — split traffic by percentage (e.g., 80/20 A/B test)
  - **Latency** — route to lowest latency region for the user
  - **Failover** — active/passive failover with health checks
  - **Geolocation** — route based on user's geographic location
  - **Geoproximity** — route based on proximity to resources

## 💡 Good to Know
- Route 53 is a **global service** — not region-specific
- The name "Route 53" comes from DNS port 53
- Route 53 does more than DNS — it also does health checks, routing policies, and domain registration
- Alias records are preferred over CNAMEs for pointing to AWS resources — they are free and work at the zone apex

---

## ⚠️ Easy to Mix Up
- **Geolocation** routing = routes based on WHERE the user is (UK users go to EU region, US users go to US region)
- **Latency** routing = routes based on what is FASTEST for the user (they are not the same thing)
- Route 53 health checks actively probe your endpoints — they don't just passively monitor
