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
