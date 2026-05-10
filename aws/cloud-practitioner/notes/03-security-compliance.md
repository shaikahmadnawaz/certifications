# AWS Security And Compliance

## What is AWS Security And Compliance? & Why It Matters

Security and compliance cover identity, access control, encryption, logging, governance, and threat protection across AWS. This domain has a large exam weight, and it is one of the easiest places to lose points if you mix up IAM, auditing, and managed security services.

---

## Prerequisites & Related Concepts

- `Shared Responsibility Model`: You need to know which tasks belong to AWS and which belong to the customer.
- `Identity`: Authentication confirms who you are; authorization decides what you can do.
- `Encryption`: Protecting data at rest and in transit is a core security expectation.

---

## Core Concepts

### IAM basics

| Item | Meaning | Best practice |
| --- | --- | --- |
| User | Identity for a person or workload | Avoid root usage for daily work |
| Group | Collection of users | Assign common permissions |
| Role | Temporary assumed identity | Preferred for AWS services and cross-account access |
| Policy | JSON permission document | Grant least privilege |

Key ideas:

- Enable MFA.
- Protect the root user.
- Prefer IAM roles over long-lived access keys.
- Follow least privilege.

### Organizations and governance

- `AWS Organizations`: Manage multiple AWS accounts centrally.
- `Service Control Policies`: Guardrails at org/account level.
- `Consolidated billing`: One payer account with linked accounts.

### Logging, auditing, configuration

| Service | Purpose |
| --- | --- |
| CloudTrail | Records API actions and account activity |
| CloudWatch | Metrics, logs, alarms |
| AWS Config | Tracks resource configuration and compliance state |
| Trusted Advisor | Best-practice checks |

### Threat protection and vulnerability tools

| Service | Purpose |
| --- | --- |
| GuardDuty | Threat detection from logs and signals |
| Inspector | Vulnerability findings |
| Macie | Sensitive data discovery in S3 |
| Shield | DDoS protection |
| WAF | Web application filtering |

### Data protection

| Service | Purpose | Key idea |
| --- | --- | --- |
| KMS | Managed encryption keys | Common default answer for encryption management |
| CloudHSM | Dedicated hardware security modules | Specialized strict key control needs |
| ACM | SSL/TLS certificates | Manage certs for AWS-integrated services |
| Secrets Manager | Store and rotate secrets | Better than hardcoding passwords |

### Compliance and reporting

- `AWS Artifact`: Access compliance reports and agreements.
- `Compliance programs`: AWS supports many standards, but customer configuration still matters.

### Security responsibility examples

| Task | AWS | Customer |
| --- | --- | --- |
| Physical data center security | Yes | No |
| Hypervisor and hardware | Yes | No |
| IAM users and permissions | No | Yes |
| EC2 guest OS patching | No | Yes |
| S3 bucket policy configuration | No | Yes |

---

## Practical Examples & Reference Snippets

Basic identity inspection:

```bash
aws sts get-caller-identity
aws iam list-users
aws iam list-roles
```

Audit-related examples:

```bash
aws cloudtrail describe-trails
aws configservice describe-configuration-recorders
```

These commands matter because real security work starts by verifying identity, auditing, and configuration state.

---

## 🏗️ Production Engineering Context (CRITICAL)

### 1. Decision Making: Why Choose This Design?

- Use IAM roles instead of embedded credentials.
- Use KMS for most encryption key management needs.
- Use Organizations when multiple accounts need governance and billing separation.

### 2. Scaling Impact: What Happens If Traffic Increases?

- More workloads mean more IAM sprawl, more logs, and more policy complexity.
- Centralized governance becomes more important as account count grows.

### 3. Failure Modes: What Might Break?

- Overly broad IAM policies expose data.
- Public S3 buckets leak information.
- Missing CloudTrail reduces forensic visibility.
- Poor secret handling leads to credential compromise.

### 4. Troubleshooting: How to Fix It?

- Identify whether the issue is authentication, authorization, encryption, or network filtering.
- Review CloudTrail for denied or unusual API activity.
- Check policy evaluation, trust relationships, and role assumptions.

Useful commands:

```bash
aws iam simulate-principal-policy --policy-source-arn arn:aws:iam::123456789012:user/demo --action-names s3:ListBucket
aws kms list-keys
aws secretsmanager list-secrets
```

---

## 🔮 Memory Hooks & Practical Scenarios

### Memory Hooks

- **When**: You hear “who can do what”
- **Say**: `IAM`
- **Remember**: Identity first, then permissions, then audit trail

### Real-World Scenario Q&A

Scenario 1:

- Context and environment: Developers share one admin account.
- Symptoms/signals: No traceability, high privilege everywhere.
- Wrong approach and why it fails: Keep sharing credentials for convenience.
- Right approach with commands: Create individual identities, groups, and roles with MFA.
- Prevention actions: Enforce least privilege and stop shared-user patterns.

Scenario 2:

- Context and environment: A company needs proof of compliance for auditors.
- Symptoms/signals: Audit asks for certification reports.
- Wrong approach and why it fails: Search random PDFs online.
- Right approach with commands: Use AWS Artifact for reports and agreements.
- Prevention actions: Keep compliance access documented and centralized.

Scenario 3:

- Context and environment: Security team wants to detect suspicious behavior.
- Symptoms/signals: Unusual API calls and scanning activity.
- Wrong approach and why it fails: Depend only on manual console review.
- Right approach with commands: Use GuardDuty, CloudTrail, and CloudWatch alerts.
- Prevention actions: Turn on logging and automated detection early.

### Mini Case Study

`Trigger -> Access key leaked in code repository -> Impact -> Unauthorized API calls -> Investigation -> CloudTrail showed suspicious usage -> Mitigation -> Disable key and rotate credentials -> Root Cause -> Long-lived credentials stored unsafely -> Prevention -> Use IAM roles and secret management`

---

## 🧪 Hands-On Drills

### Drill 1: Quick Lab (10-15 min)

- Objective: Explain IAM, CloudTrail, KMS, and GuardDuty in one sentence each.
- Setup: Use this file only.
- Commands:

```bash
aws sts get-caller-identity
aws iam list-roles
aws cloudtrail describe-trails
```

- Verification: You can classify each service as identity, audit, encryption, or threat detection.

### Drill 2: Production Simulation (20-40 min)

- Failure injection method: Write three access-denied scenarios.
- Expected signals: `AccessDenied`, missing role assumption, blocked S3 call.
- Recovery playbook: Check principal, attached policy, trust policy, then service-specific policy.
- Rollback/cleanup steps: Record the exact layer that caused the denial.

---

## Quick Reference

```bash
aws sts get-caller-identity
aws iam list-users
aws iam list-roles
aws cloudtrail describe-trails
aws configservice describe-configuration-recorders
aws kms list-keys
aws secretsmanager list-secrets
```

---

## Interview Questions

- **Question**: Why are IAM roles preferred over access keys for AWS services?
- **Answer**: Roles provide temporary credentials and reduce the risk of long-lived secret exposure.
- **Why this matters**: It reflects a core AWS security pattern.

- **Question**: What is the difference between CloudTrail and CloudWatch?
- **Answer**: CloudTrail records API activity; CloudWatch focuses on metrics, logs, and alarms.
- **Why this matters**: They are often confused in exam questions.

- **Question**: When would you use AWS Artifact?
- **Answer**: To access AWS compliance reports and agreements.
- **Why this matters**: This is a common direct fact question.

- **Question**: What does least privilege mean?
- **Answer**: Grant only the permissions required to perform the intended task, nothing more.
- **Why this matters**: It is the default secure design principle in AWS.

- **Question**: Who patches the operating system on an EC2 instance?
- **Answer**: The customer.
- **Why this matters**: It tests Shared Responsibility Model understanding.
