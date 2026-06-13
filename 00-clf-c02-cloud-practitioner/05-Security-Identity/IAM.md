# IAM — Identity and Access Management

## What is it?
Controls **who** can do **what** to **which** AWS resources.
The foundation of all AWS security.

## Data Centre Analogy
Active Directory + RBAC + sudo rules combined. Who can log in what systems they can access, and what actions they can perform — but for every AWS service.

---

## Key Concepts

### Core Components
- **Users** — individual people or applications needing AWS access
- **Groups** — collection of users. Attach policies to groups,
  not individual users (best practice)
- **Roles** — temporary permissions assumed by AWS services,
  applications, or federated users. No static credentials.
- **Policies** — JSON documents defining allowed/denied actions
  on specific resources

### Policy Structure
```json
{
  "Effect": "Allow",
  "Action": "s3:GetObject",
  "Resource": "arn:aws:s3:::my-bucket/*"
}
```
- **Effect** — Allow or Deny
- **Action** — what operation is permitted (e.g., s3:GetObject)
- **Resource** — what AWS resource it applies to (ARN)

### Access Types
- **Console Access** — username + password + optional MFA
- **Programmatic Access** — Access Key ID + Secret Access Key
  (for CLI, SDK, and API calls)

### Key Principles
- **Principle of Least Privilege** — grant only the minimum
  permissions needed, nothing more
- **MFA** — always enable on root account and privileged users
- **Root Account** — the account created when you first sign up.
  Never use for day-to-day tasks. Lock it away.

## When to Use Roles (not Users) ✅
- EC2 instance needs to access S3 → attach IAM Role to EC2
- Lambda function needs to access DynamoDB → use execution role
- Cross-account access → assume a role
- **Never embed access keys in code — use roles instead**

---

## 💡 Good to Know
- IAM is a **global service** — not region-specific. Users and
  roles exist across all regions.
- **Root account** should be locked away after initial setup.
  Create an IAM admin user for day-to-day tasks instead.
- Default behaviour: **everything is denied** unless explicitly allowed.
  There is no such thing as implicit allow.
- MFA adds a second factor on top of password — critical for root
  and any admin users

### IAM Policy Evaluation Logic
```
1. Explicit DENY anywhere? → DENY (always wins, overrides everything)
2. Explicit ALLOW? → ALLOW
3. Neither? → DENY (implicit deny by default)
```

---

## ⚠️ Easy to Mix Up
- IAM users are NOT created per-region — they are global
- Never share access keys. Never commit them to code or Git.
- **Roles** are preferred over **users** for service-to-service access
  — roles use temporary credentials and don't require key management
- "Least privilege" = only what's needed, nothing more
