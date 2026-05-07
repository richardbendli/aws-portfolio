# AWS Lambda

## What is it?
Run code without managing servers. You upload a function, define a
trigger, and AWS handles everything else — scaling, patching,
infrastructure.


---

## Key Concepts
- **Function** — your code (Python, Node.js, Java, Go, etc.)
- **Trigger** — what invokes the function (API Gateway, S3 event,
  DynamoDB stream, EventBridge schedule, etc.)
- **Execution Role** — IAM role that grants your function permissions
  to access other AWS services
- **Timeout** — max 15 minutes per execution
- **Concurrency** — Lambda scales automatically, running thousands
  of instances in parallel
- **Stateless** — no persistent memory between invocations.
  Use S3 or DynamoDB for state that must persist.

## When to Use It ✅
- Event-driven, short-duration tasks
- APIs and microservices (paired with API Gateway)
- File processing (e.g., resize image when uploaded to S3)
- Scheduled tasks (cron-style automation via EventBridge)
- Anything where you don't want to manage infrastructure

## When NOT to Use It ❌
- Workloads longer than 15 minutes → use EC2 or ECS
- Need persistent OS-level access → use EC2
- Long-running batch processing → use EC2 with Spot Instances

---

## 💡 Good to Know
- Lambda is **serverless** — falls under the **FaaS** category
  (Function as a Service)
- You pay **per invocation + duration** (measured in GB-seconds)
  — NOT for idle time. If it's not running, you pay nothing.
- Max execution timeout = **15 minutes**
- Lambda integrates with almost every AWS service as a trigger
- Part of the **serverless trio**: Lambda + API Gateway + DynamoDB
- Lambda still needs an **IAM execution role** to access other
  AWS services — it doesn't get permissions automatically

---

## ⚠️ Easy to Mix Up
- Lambda is NOT for long-running processes (hard 15-minute limit)
- "No servers to manage" in an exam question = Lambda
  (or another serverless service)
- Lambda needs an IAM execution role — it is NOT automatically
  allowed to access S3, DynamoDB, or anything else
  