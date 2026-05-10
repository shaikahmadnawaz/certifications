# AWS Billing Pricing And Support

## What is AWS Billing Pricing And Support? & Why It Matters

Billing, pricing, and support explain how AWS charges for services, how to control cost, and how organizations get help. This domain is smaller than security or core services, but it is high-scoring if you know the common pricing models and cost management tools.

---

## Prerequisites & Related Concepts

- `OpEx`: AWS billing is usage-based operating expense.
- `Managed services`: Cost is tied not just to compute hours but also requests, storage, transfer, and premium features.
- `Organizations`: Multi-account designs often change how billing is managed.

---

## Core Concepts

### Common pricing models

| Model | Meaning | Best fit |
| --- | --- | --- |
| On-Demand | Pay for use with no long commitment | Unpredictable or short-term workloads |
| Reserved Instances | Commit for lower cost | Steady workloads |
| Savings Plans | Flexible spend commitment | Consistent compute usage |
| Spot Instances | Use spare capacity at discount | Interruptible workloads |

### Cost management services

| Service | Purpose |
| --- | --- |
| AWS Free Tier | Limited free usage for learning and trials |
| Cost Explorer | Visualize and analyze spend |
| AWS Budgets | Alert on cost or usage thresholds |
| Cost and Usage Report | Detailed billing dataset |
| Pricing Calculator | Estimate future cost |

### Support plans

| Plan | Main idea |
| --- | --- |
| Basic | Account and billing support, limited technical guidance |
| Developer | Business-hours guidance for testing/dev workloads |
| Business | Faster response, trusted for production support |
| Enterprise | Highest support level and strategic guidance |

### Billing patterns

- `Consolidated billing`: One payer account pays for linked accounts.
- `Tagging`: Helps allocate spend by team, project, or environment.
- `Cost optimization`: Rightsizing, scheduling, lifecycle policies, and choosing managed services wisely.

### Common exam associations

| Need | Likely answer |
| --- | --- |
| Get alerted before overspending | AWS Budgets |
| Analyze historical spend trends | Cost Explorer |
| Estimate planned architecture cost | Pricing Calculator |
| Share one bill across accounts | AWS Organizations consolidated billing |

---

## Practical Examples & Reference Snippets

Cost visibility commands:

```bash
aws ce get-cost-and-usage --time-period Start=2026-05-01,End=2026-05-10 --granularity DAILY --metrics UnblendedCost
aws budgets describe-budgets --account-id 123456789012
```

Even if you do not use these often for the exam, they reinforce that cost management is also operational data.

---

## 🏗️ Production Engineering Context (CRITICAL)

### 1. Decision Making: Why Choose This Design?

- Use On-Demand when usage is uncertain.
- Use Savings Plans or Reserved pricing when workloads are stable.
- Use Spot only when interruption is acceptable.

### 2. Scaling Impact: What Happens If Traffic Increases?

- Bills rise with compute, storage, requests, and data transfer.
- Fast scaling without budgets or cost visibility can create surprise spend.

### 3. Failure Modes: What Might Break?

- Orphaned resources keep generating cost.
- No tagging means no accountability.
- Wrong purchase model increases spend even when architecture is technically correct.

### 4. Troubleshooting: How to Fix It?

- Identify cost spikes by service, account, and tag.
- Check for idle instances, unattached volumes, old snapshots, and unnecessary data transfer.
- Review whether usage pattern matches the pricing model.

---

## 🔮 Memory Hooks & Practical Scenarios

### Memory Hooks

- **When**: You hear “alert me on spend”
- **Say**: `AWS Budgets`
- **Remember**: Explorer explains, Budgets warns

### Real-World Scenario Q&A

Scenario 1:

- Context and environment: A team wants the cheapest compute for batch jobs.
- Symptoms/signals: Jobs can restart if interrupted.
- Wrong approach and why it fails: Buy On-Demand capacity for all batch work.
- Right approach with commands: Use Spot Instances for interruptible work.
- Prevention actions: Match interruption tolerance to pricing model.

Scenario 2:

- Context and environment: Finance asks why cloud spend increased last month.
- Symptoms/signals: Only total bill is visible.
- Wrong approach and why it fails: Guess based on recent deployments.
- Right approach with commands: Use Cost Explorer and tagged cost breakdowns.
- Prevention actions: Enforce cost allocation tags.

Scenario 3:

- Context and environment: A company runs steady workloads all year.
- Symptoms/signals: On-Demand cost stays consistently high.
- Wrong approach and why it fails: Keep paying On-Demand forever.
- Right approach with commands: Evaluate Savings Plans or Reserved pricing.
- Prevention actions: Review monthly utilization trends.

### Mini Case Study

`Trigger -> Monthly bill doubled -> Impact -> Budget concern and delayed approvals -> Investigation -> Unused test instances and expensive On-Demand baseline -> Mitigation -> Stop idle resources and buy better pricing plan -> Root Cause -> No budget alerts or cost ownership -> Prevention -> Budgets, tagging, scheduled shutdowns`

---

## 🧪 Hands-On Drills

### Drill 1: Quick Lab (10-15 min)

- Objective: Memorize which cost tool answers which question.
- Setup: Cover the tables and answer from memory.
- Commands:

```bash
aws ce get-cost-and-usage --time-period Start=2026-05-01,End=2026-05-10 --granularity DAILY --metrics UnblendedCost
```

- Verification: You can answer Budgets vs Cost Explorer vs Pricing Calculator instantly.

### Drill 2: Production Simulation (20-40 min)

- Failure injection method: Invent a cost spike after a deployment.
- Expected signals: More instances, bigger transfer, or idle storage growth.
- Recovery playbook: Identify cost source, reduce waste, and choose better purchase model.
- Rollback/cleanup steps: Write the cost-prevention checklist.

---

## Quick Reference

```bash
aws ce get-cost-and-usage --time-period Start=2026-05-01,End=2026-05-10 --granularity DAILY --metrics UnblendedCost
aws budgets describe-budgets --account-id 123456789012
```

---

## Interview Questions

- **Question**: When should Spot Instances be used?
- **Answer**: For workloads that can tolerate interruption, such as batch processing.
- **Why this matters**: It connects pricing to workload behavior.

- **Question**: What is AWS Budgets used for?
- **Answer**: To set custom cost or usage thresholds and alert when they are crossed.
- **Why this matters**: It is a common direct exam question.

- **Question**: What is the difference between Cost Explorer and the Pricing Calculator?
- **Answer**: Cost Explorer analyzes actual spend; Pricing Calculator estimates future cost.
- **Why this matters**: This is a frequent distinction in foundational exams.

- **Question**: Why use consolidated billing?
- **Answer**: To manage multiple accounts under one payer account while keeping account separation.
- **Why this matters**: It supports governance and cost visibility patterns.

- **Question**: Which support plan is more appropriate for production-critical workloads than Developer Support?
- **Answer**: Business Support.
- **Why this matters**: Support plan questions usually test scenario fit, not memorization alone.
