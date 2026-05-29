# CloudFront — AWS CDN

## What is it?
AWS's Content Delivery Network (CDN). Caches and serves your content from **edge locations** around the world, closer to your users.

A globally distributed caching layer in front of your origin servers.
Like having PoP (Point of Presence) servers worldwide that serve cached copies of your content so users don't hit your data centre directly.

---

## Key Concepts
- **Edge Locations** — 400+ globally distributed cache points (more numerous than Regions or AZs)
- **Origin** — where CloudFront fetches the original content (S3, EC2, ALB, or any HTTP server — including non-AWS origins)
- **Distribution** — your CloudFront configuration
- **TTL (Time to Live)** — how long content is cached at edge before fetching a fresh copy from origin
- **Cache Invalidation** — force CloudFront to fetch fresh content before TTL expires (incurs a small charge)

## When to Use It ✅
- Accelerate static website delivery for global users
- Reduce latency for international users
- Protect origin from direct traffic and DDoS (pairs with Shield )
- Stream video globally
- Serve S3 content securely without making the bucket public

## When NOT to Use It ❌
- Dynamic, personalised content that cannot be cached per user
- Applications where users are all in one region near the origin

---

## 💡 Good to Know
- CloudFront = CDN = **Edge Locations** — not Regions, not AZs
- Edge Locations > AZs > Regions in terms of count (400+ edge, 100+ AZs, 34 regions)
- CloudFront reduces load on your origin by serving cached responses
- CloudFront + S3 = the standard pattern for secure, fast, global static website hosting
- CloudFront integrates with **AWS WAF** for web application firewall protection at the edge
- CloudFront can serve content from origins **outside AWS** too

---

## ⚠️ Easy to Mix Up
- **Edge Locations** are NOT the same as AZs — they are separate, more numerous locations used specifically for caching/CDN/DNS
- CloudFront can serve content from non-AWS origins — it is not limited to AWS resources
