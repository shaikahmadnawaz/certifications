# AWS Cloud Practitioner Prep Pack

This folder is a **complete** study pack for the AWS Certified Cloud Practitioner (`CLF-C02`) exam. It combines concept notes, scenario-based practice questions, hands-on labs, and exam-day checklists.

---

## Start Here

1. Read this `README.md`
2. Follow the [Recommended Study Order](#recommended-study-order) below
3. Track daily progress in [plan/03-progress-tracker.md](./plan/03-progress-tracker.md)

---

## File Map

### Plan & Tracking

- [plan/01-roadmap.md](./plan/01-roadmap.md) — 14-day sprint plan
- [plan/02-daily-timetable.md](./plan/02-daily-timetable.md) — day-by-day schedule
- [plan/03-progress-tracker.md](./plan/03-progress-tracker.md) — daily checklist with weak-area notes

### Concept Notes (read in order)

- [notes/01-cloud-fundamentals.md](./notes/01-cloud-fundamentals.md) — Cloud basics, AWS model, global infrastructure
- [notes/02-core-services.md](./notes/02-core-services.md) — Compute, storage, databases, networking
- [notes/03-security-compliance.md](./notes/03-security-compliance.md) — IAM, security services, governance
- [notes/04-billing-support.md](./notes/04-billing-support.md) — Pricing models, cost tools, support plans
- [notes/12-well-architected-deep-dive.md](./notes/12-well-architected-deep-dive.md) — All 6 pillars explained in depth
- [notes/13-migration-and-caf.md](./notes/13-migration-and-caf.md) — 7 Rs of migration, migration tools (CAF summary + link to deep-dive)
- [notes/19-cloud-adoption-framework.md](./notes/19-cloud-adoption-framework.md) — **AWS CAF deep-dive**: 6 perspectives, 4 domains, 4 phases, CAF vs Well-Architected
- [notes/14-service-deep-dives.md](./notes/14-service-deep-dives.md) — S3 classes, EC2 families, VPC endpoints, Snow Family, Transit Gateway, Global Accelerator

### Reference & Revision

- [notes/07-official-objective-mapping.md](./notes/07-official-objective-mapping.md) — CLF-C02 domain/task coverage map
- [notes/09-service-selection-matrix.md](./notes/09-service-selection-matrix.md) — Scenario → service mapping
- [notes/05-practice-review.md](./notes/05-practice-review.md) — Comparison tables, traps, elimination strategy
- [notes/08-flashcards.md](./notes/08-flashcards.md) — 100 flashcards for active recall
- [notes/11-last-minute-revision.md](./notes/11-last-minute-revision.md) — Final 48-hour condensed revision
- [notes/17-official-service-glossary.md](./notes/17-official-service-glossary.md) — One-line guide to official in-scope AWS services
- [notes/18-exam-format-and-strategy.md](./notes/18-exam-format-and-strategy.md) — Official exam format, scoring facts, and test strategy

### Practice

- [notes/10-mock-question-bank.md](./notes/10-mock-question-bank.md) — 100 basic recall questions
- [notes/15-advanced-mock-questions.md](./notes/15-advanced-mock-questions.md) — 100 scenario-based questions with distractors (exam-style)
- [notes/16-hands-on-labs.md](./notes/16-hands-on-labs.md) — 10 AWS Free Tier labs

### Exam Day

- [notes/06-exam-day-checklist.md](./notes/06-exam-day-checklist.md) — 48-hour countdown and test strategy

---

## Recommended Study Order

### Phase 1: Foundations (Days 1–5)

1. [notes/01-cloud-fundamentals.md](./notes/01-cloud-fundamentals.md)
2. [notes/02-core-services.md](./notes/02-core-services.md)
3. [notes/12-well-architected-deep-dive.md](./notes/12-well-architected-deep-dive.md)
4. [notes/19-cloud-adoption-framework.md](./notes/19-cloud-adoption-framework.md) — learn right after Well-Architected to lock in the difference
5. [notes/13-migration-and-caf.md](./notes/13-migration-and-caf.md)
6. [notes/03-security-compliance.md](./notes/03-security-compliance.md)
7. [notes/04-billing-support.md](./notes/04-billing-support.md)

### Phase 2: Depth & Service Details (Days 6–8)

7. [notes/14-service-deep-dives.md](./notes/14-service-deep-dives.md)
8. [notes/09-service-selection-matrix.md](./notes/09-service-selection-matrix.md)
9. [notes/17-official-service-glossary.md](./notes/17-official-service-glossary.md)
10. [notes/07-official-objective-mapping.md](./notes/07-official-objective-mapping.md) — verify coverage

### Phase 3: Hands-On (Parallel with Phase 1-2)

11. [notes/16-hands-on-labs.md](./notes/16-hands-on-labs.md) — 30-45 min/day

### Phase 4: Practice (Days 9–12)

12. [notes/08-flashcards.md](./notes/08-flashcards.md) — daily
13. [notes/10-mock-question-bank.md](./notes/10-mock-question-bank.md) — basic recall
14. [notes/15-advanced-mock-questions.md](./notes/15-advanced-mock-questions.md) — **scenario-based; most important for real exam**
15. [notes/05-practice-review.md](./notes/05-practice-review.md) — elimination strategy
16. [notes/18-exam-format-and-strategy.md](./notes/18-exam-format-and-strategy.md)

### Phase 5: Final Revision (Days 13–14)

17. [notes/11-last-minute-revision.md](./notes/11-last-minute-revision.md)
18. [notes/06-exam-day-checklist.md](./notes/06-exam-day-checklist.md)

---

## How to Use This Pack Effectively

1. **Read actively.** After each note file, close it and write 5 things you learned from memory.
2. **Do hands-on labs in parallel.** Reading + doing beats reading alone.
3. **Score-based progression.**
   - 70%+ on mock questions → ready for practice exams
   - 80%+ on [15-advanced-mock-questions.md](./notes/15-advanced-mock-questions.md) → ready to book the real exam
4. **Track weak areas.** Every wrong answer gets logged with the topic. Re-study only the gap.
5. **Supplement with one external resource.** Tutorials Dojo practice exams (~$15) or AWS Skill Builder practice questions (free).
   - Practice-question resource used for this pack: [ExamCademy CLF-C02](https://examcademy.com/exams/amazon/aws-certified-cloud-practitioner-clf-c02) — free, community-contributed mock tests. Use it for timed format/recall practice, but cross-check any answer against the verified notes (`17-official-service-glossary.md`, `07-official-objective-mapping.md`, `19-cloud-adoption-framework.md`), since community answers can be outdated or wrong.

---

## Exam Strategy (Summary)

- Learn **service purpose** before memorizing details
- Focus on choosing the **best AWS service for a scenario**
- Revisit IAM, pricing, S3, shared responsibility, and global infrastructure repeatedly
- For wrong answers, write down **why the wrong options are wrong**
- Use [notes/07-official-objective-mapping.md](./notes/07-official-objective-mapping.md) to confirm every official domain and task is covered

---

## Coverage Note

This pack is mapped to the current AWS Certified Cloud Practitioner `CLF-C02` exam guide and in-scope/out-of-scope service lists, verified on May 12, 2026.

Content reflects:
- Current 6 Well-Architected pillars (Sustainability included)
- AWS CAF 3.0 six perspectives (Business, People, Governance, Platform, Security, Operations)
- 7 Rs of migration (including Relocate)
- Snow Family status as of Nov 2025 (Snowmobile retired, Snowcone discontinued, Snowball Edge existing-customer only)
- Current pricing model names (Savings Plans, current RI types)
- Current in-scope services (IAM Identity Center, SageMaker AI, etc.)

---

## Pass Rate Estimate

- Complete Phase 1–2 only: ~55–65%
- Complete Phase 1–2 + flashcards + basic mocks: ~70–75%
- Complete all 5 phases: **85–95%**

Book the exam only when you consistently hit 80%+ on [15-advanced-mock-questions.md](./notes/15-advanced-mock-questions.md).
