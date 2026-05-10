# AWS Exam Day Checklist

## What is the Exam Day Checklist? & Why It Matters

The final day is not for learning new content. It is for reducing avoidable mistakes, keeping recall sharp, and showing up prepared so your knowledge is usable under time pressure.

---

## Prerequisites & Related Concepts

- `Practice review`: This checklist works only if you have already revised the main notes and know your weak areas.
- `Time management`: Foundational exams reward clear elimination and calm pacing, not deep over-analysis.
- `Exam strategy`: Final-day performance depends on recall quality, rest, and environment readiness.

---

## Core Concepts

### 48-24 hours before exam

- Stop collecting new resources.
- Review only your notes in this folder.
- Revisit IAM, S3, pricing, shared responsibility, and service comparisons.
- Take one short untimed confidence review only if it helps.

### Night before exam

- Sleep properly.
- Keep review light.
- Prepare ID and exam setup.
- If online proctored, verify system requirements and room readiness.

### During the exam

- Read the full question once before touching answers.
- Underline clue words mentally: `cheapest`, `managed`, `shared`, `audit`, `event-driven`, `global`, `highly available`.
- Eliminate obviously wrong categories first.
- Mark and move if stuck.

### Time strategy

- First pass: answer what is clear.
- Second pass: return to flagged items.
- Final pass: review only uncertain answers, not every answer.

---

## Practical Examples & Reference Snippets

Exam-time reminder:

```text
Need -> Category -> Service -> Why not others
```

Confidence checklist:

```text
I know:
- Region vs AZ
- S3 vs EBS vs EFS
- RDS vs DynamoDB
- CloudTrail vs CloudWatch
- Budgets vs Cost Explorer
- IAM role vs user
```

---

## 🏗️ Production Engineering Context (CRITICAL)

### 1. Decision Making: Why Choose This Design?

- Final review should prioritize high-yield recall, not breadth.
- Short, repeated comparison review is better than opening brand-new material.

### 2. Scaling Impact: What Happens If Traffic Increases?

- Under exam pressure, more mental load acts like production load: confusion rises, simple mistakes increase, and weak recall gets exposed.

### 3. Failure Modes: What Might Break?

- Panic review of new topics
- Poor sleep
- Rushing and misreading clue words
- Changing correct answers without a strong reason

### 4. Troubleshooting: How to Fix It?

- If confidence drops, return to comparison tables and shared responsibility.
- If stuck on a question, identify the category first and eliminate by mismatch.
- If one domain feels weak, do one focused 20-minute review instead of broad re-reading.

---

## 🔮 Memory Hooks & Practical Scenarios

### Memory Hooks

- **When**: You start overthinking
- **Say**: `Need -> Category -> Service -> Eliminate`
- **Remember**: The exam tests fit and clarity more than obscure detail

### Real-World Scenario Q&A

Scenario 1:

- Context and environment: You encounter a question with two plausible answers.
- Symptoms/signals: Both options seem familiar.
- Wrong approach and why it fails: Pick the service you have heard of most often.
- Right approach with commands: Match the exact workload clue words and eliminate mismatched categories.
- Prevention actions: Practice service-comparison tables daily.

Scenario 2:

- Context and environment: You feel weak in pricing one night before the exam.
- Symptoms/signals: You want to start a new long video course.
- Wrong approach and why it fails: Cram new material and reduce sleep.
- Right approach with commands: Review `04-billing-support.md` and `05-practice-review.md` only.
- Prevention actions: Lock the revision scope 48 hours before the exam.

### Mini Case Study

`Trigger -> Candidate reviewed random new sources on exam eve -> Impact -> Fragmented recall and fatigue -> Investigation -> Strong topics became mixed with new terminology -> Mitigation -> Switched back to short revision notes -> Root Cause -> No final-day study boundary -> Prevention -> Use one fixed checklist and one fixed note pack`

---

## 🧪 Hands-On Drills

### Drill 1: Final 10-minute reset

- Objective: Calm recall before the exam.
- Setup: Open only `05-practice-review.md`.
- Commands: Read the comparison table aloud once.
- Verification: Explain the high-value comparison table aloud.

### Drill 2: Last confidence check

- Objective: Confirm readiness without draining energy.
- Setup: Answer 10 self-made questions from memory.
- Commands: Write answers without notes, then validate against the pack.
- Verification: If score is weak in one area, review only that area for 20 minutes.

---

## Quick Reference

```text
Audit -> CloudTrail
Metrics/logs -> CloudWatch
Static files -> S3
Shared file storage -> EFS
Attached disk -> EBS
NoSQL -> DynamoDB
Managed SQL -> RDS/Aurora
Spend alert -> Budgets
Estimate cost -> Pricing Calculator
Temporary service credentials -> IAM Role
```

---

## Interview Questions

- **Question**: What should you focus on in the final 24 hours before the exam?
- **Answer**: High-yield review, weak-domain refresh, and environment readiness rather than learning new content.
- **Why this matters**: Good final-day choices improve score consistency.

- **Question**: What is the best recovery move when two AWS answers both seem correct?
- **Answer**: Return to the exact workload clues and eliminate options that solve a different category of problem.
- **Why this matters**: This is how many foundational questions are won.

- **Question**: Why is sleep part of exam strategy?
- **Answer**: Fatigue reduces reading accuracy and recall speed, which directly hurts performance.
- **Why this matters**: Operational thinking includes human reliability, not just facts.
