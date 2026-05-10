# AWS Practice Review

## What is Practice Review? & Why It Matters

Practice review turns memorized facts into faster decision-making. For Cloud Practitioner, the difference between passing and failing is often not raw knowledge but how quickly you eliminate wrong options and recognize service-selection patterns.

---

## Prerequisites & Related Concepts

- `Core services`: You need first-pass understanding of the main AWS services.
- `Security`: IAM and shared responsibility show up across many question types.
- `Pricing`: Cost questions are usually easy marks if reviewed often.

---

## Core Concepts

### High-value comparison table

| Pair | Difference |
| --- | --- |
| Region vs AZ | Geography vs isolated location inside a Region |
| Security Group vs NACL | Stateful resource firewall vs stateless subnet filter |
| S3 vs EBS | Object storage vs block storage |
| EBS vs EFS | Single-instance block vs shared file system |
| RDS vs DynamoDB | Relational SQL vs NoSQL key-value/document |
| CloudTrail vs CloudWatch | API audit vs metrics/logs/alarms |
| Shield vs WAF | DDoS protection vs application-layer filtering |
| Cost Explorer vs Budgets | Analyze spend vs alert on spend |

### Common exam traps

- Picking EC2 when a managed service is simpler
- Confusing monitoring with auditing
- Forgetting that customer manages IAM and EC2 guest OS security
- Choosing a database service for storage behavior it does not provide
- Missing keywords like `static website`, `event-driven`, `shared file system`, `interruptible`

### Fast elimination method

1. Identify the core need: compute, storage, database, network, security, or cost.
2. Circle the clue words.
3. Remove answers from the wrong category.
4. Remove answers that are too complex or solve a different problem.
5. Choose the AWS-managed option unless the question clearly needs more control.

---

## Practical Examples & Reference Snippets

Exam-time scratchpad pattern:

```text
Need: static content worldwide
Category: storage + delivery
Clues: static, global, low latency
Answer: S3 + CloudFront
Why not EC2: unnecessary server management
```

Wrong-to-right pattern:

```text
Need: audit API calls
Wrong: CloudWatch
Right: CloudTrail
```

---

## 🏗️ Production Engineering Context (CRITICAL)

### 1. Decision Making: Why Choose This Design?

- Foundational questions reward the most operationally sensible managed-service answer.
- Production teams reduce toil by choosing services aligned with workload shape.

### 2. Scaling Impact: What Happens If Traffic Increases?

- Scaling reveals weak architecture choices fast, especially around databases, caching, and content delivery.

### 3. Failure Modes: What Might Break?

- Misreading the problem statement.
- Choosing based on brand familiarity instead of service fit.
- Ignoring one key clue word in the question.

### 4. Troubleshooting: How to Fix It?

- If you get a practice question wrong, rewrite it as `problem -> best service -> why others fail`.
- Track mistakes by topic instead of by test.

---

## 🔮 Memory Hooks & Practical Scenarios

### Memory Hooks

- **When**: You freeze between two answers
- **Say**: `Which one matches the exact workload shape?`
- **Remember**: AWS exams reward fit, not maximal complexity

### Real-World Scenario Q&A

Scenario 1:

- Context and environment: You need a shared Linux file system for many EC2 instances.
- Symptoms/signals: Multiple servers need the same files.
- Wrong approach and why it fails: Choose EBS because it is storage for EC2.
- Right approach with commands: Choose EFS because it is a shared managed file system.
- Prevention actions: Map storage questions by access pattern first.

Scenario 2:

- Context and environment: You need to know who deleted an S3 bucket.
- Symptoms/signals: Resource disappeared, audit needed.
- Wrong approach and why it fails: Look only at CloudWatch metrics.
- Right approach with commands: Check CloudTrail events.
- Prevention actions: Separate observability from audit trail concepts.

### Mini Case Study

`Trigger -> Practice score stuck at 62% -> Impact -> Confidence drops -> Investigation -> Mistakes cluster around service comparisons -> Mitigation -> Build comparison tables and elimination workflow -> Root Cause -> Knowledge existed but recall was fuzzy -> Prevention -> Daily active recall and topic-based review`

---

## 🧪 Hands-On Drills

### Drill 1: Quick Lab (10-15 min)

- Objective: Answer 15 rapid-fire service selection prompts.
- Setup: Use flashcards or self-written prompts.
- Commands: No AWS account needed.
- Verification: Score at least 12 out of 15 in one pass.

### Drill 2: Production Simulation (20-40 min)

- Failure injection method: Take a timed 25-question quiz.
- Expected signals: Rushing, overthinking, confusion on similar services.
- Recovery playbook: Review only wrong answers and classify the error type.
- Rollback/cleanup steps: Add the top five weak patterns to tomorrow’s revision list.

---

## Quick Reference

```text
Static site -> S3
Global cache -> CloudFront
Audit API calls -> CloudTrail
Spend alerts -> Budgets
Shared file system -> EFS
Low-latency NoSQL -> DynamoDB
Managed SQL -> RDS/Aurora
Event-driven code -> Lambda
```

---

## Interview Questions

- **Question**: Why is service comparison so important for foundational AWS exams?
- **Answer**: Because many questions test whether you can map a scenario to the most suitable managed service.
- **Why this matters**: It changes how you study and review mistakes.

- **Question**: What is the fastest way to improve mock scores?
- **Answer**: Analyze wrong answers by topic and by confusion pattern, not just by total score.
- **Why this matters**: It produces targeted improvement.

- **Question**: Why is S3 often preferred over EC2 for static content?
- **Answer**: It is simpler, cheaper, and removes server management for that use case.
- **Why this matters**: It reflects AWS’s managed-service bias.

- **Question**: What clue suggests Budgets instead of Cost Explorer?
- **Answer**: The need for alerts or threshold notifications.
- **Why this matters**: Small wording differences decide the answer.
