# Elastic Beanstalk

## What is it?
A PaaS (Platform as a Service) that deploys and manages your web
application automatically. You upload your code, Beanstalk handles
the infrastructure.

Like handing your application to a managed hosting team — they
provision servers, configure load balancers, handle scaling, and
monitor health. You just provide the code.

---

## Key Concepts
- Supports: Java, .NET, PHP, Node.js, Python, Ruby, Go, Docker
- Automatically provisions: EC2, Load Balancer, Auto Scaling, RDS
- You still have access to the underlying resources if needed
- Free to use — you pay only for the underlying AWS resources it creates

## When to Use It ✅
- Developers who want to deploy apps without managing infrastructure
- Quick deployments with standard web application patterns
- When you want PaaS simplicity but still want AWS flexibility underneath

## When NOT to Use It ❌
- Need full infrastructure control → use EC2 directly
- Serverless architecture → use Lambda
- Infrastructure as code control → use CloudFormation

---

