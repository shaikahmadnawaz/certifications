# AWS CLF-C02 Official Objective Mapping

## What is Objective Mapping? & Why It Matters

This file maps the prep pack to the current official AWS Certified Cloud Practitioner `CLF-C02` blueprint so you can verify that the study folder covers every scored domain and task area. It prevents the common mistake of studying only familiar core services and missing smaller but scorable exam areas.

Source basis for this file:

- AWS Certified Cloud Practitioner `CLF-C02` exam guide
- CLF-C02 domain pages
- CLF-C02 in-scope and out-of-scope AWS services lists

Checked against official AWS docs on `May 12, 2026`.

---

## Prerequisites & Related Concepts

- `Exam weighting`: Some domains matter more than others, so your time allocation must reflect the scoring mix.
- `In-scope services`: The official service list is non-exhaustive, but it signals which names you should recognize.
- `Service selection`: Foundational AWS exams reward recognition and fit more than deep implementation detail.

---

## Core Concepts

### Official scored domains

| Domain | Weight |
| --- | --- |
| Domain 1: Cloud Concepts | 24% |
| Domain 2: Security and Compliance | 30% |
| Domain 3: Cloud Technology and Services | 34% |
| Domain 4: Billing, Pricing, and Support | 12% |

### Domain 1: Cloud Concepts

#### Task 1.1: Define the benefits of the AWS Cloud

Required knowledge and skill:

- AWS Cloud value proposition
- Benefits of global infrastructure
- High availability, elasticity, agility

Covered in:

- `01-cloud-fundamentals.md`
- `05-practice-review.md`
- `11-last-minute-revision.md`

#### Task 1.2: Identify design principles of the AWS Cloud

Required knowledge and skill:

- AWS Well-Architected Framework
- All six pillars
- Differences between pillars

Covered in:

- `01-cloud-fundamentals.md`
- `08-flashcards.md`

#### Task 1.3: Understand the benefits of and strategies for migration to the AWS Cloud

Required knowledge and skill:

- Cloud adoption strategies
- AWS Cloud Adoption Framework basics
- Migration strategies
- Tools such as AWS Snow Family

Covered in:

- `01-cloud-fundamentals.md`
- `09-service-selection-matrix.md`
- `10-mock-question-bank.md`

Notes:

- This is smaller than compute or security, but it is easy to miss if you study only “big-name” services.

#### Task 1.4: Understand concepts of cloud economics

Required knowledge and skill:

- Fixed vs variable costs
- On-prem cost model vs cloud cost model
- BYOL vs included licensing
- Rightsizing
- Economies of scale
- Benefits of automation

Covered in:

- `01-cloud-fundamentals.md`
- `04-billing-support.md`
- `11-last-minute-revision.md`

### Domain 2: Security and Compliance

#### Task 2.1: Understand the AWS shared responsibility model

Required knowledge and skill:

- AWS responsibilities
- Customer responsibilities
- Shared areas
- How responsibility shifts by service type

Covered in:

- `01-cloud-fundamentals.md`
- `03-security-compliance.md`
- `08-flashcards.md`

#### Task 2.2: Understand AWS Cloud security, governance, and compliance concepts

Required knowledge and skill:

- Compliance programs
- AWS Artifact
- Encryption at rest and in transit
- Logging and audit capture
- Governance and compliance services

Covered in:

- `03-security-compliance.md`
- `05-practice-review.md`
- `11-last-minute-revision.md`

Additional official names you should recognize:

- AWS Audit Manager
- AWS Config
- CloudTrail
- CloudWatch
- AWS Security Hub
- GuardDuty
- Shield
- Inspector
- CloudHSM
- Cognito
- Detective
- Directory Service
- Macie
- Resource Access Manager

#### Task 2.3: Identify AWS access management capabilities

Required knowledge and skill:

- IAM
- Root user protection
- Least privilege
- IAM Identity Center
- MFA
- Federated identity
- Cross-account roles
- Secrets and credential storage

Covered in:

- `03-security-compliance.md`
- `08-flashcards.md`
- `10-mock-question-bank.md`

#### Task 2.4: Identify components and resources for security

Required knowledge and skill:

- WAF, Shield, GuardDuty, Firewall Manager
- Security documentation and official resources
- Marketplace security products
- Trusted Advisor for security findings

Covered in:

- `03-security-compliance.md`
- `09-service-selection-matrix.md`
- `10-mock-question-bank.md`

### Domain 3: Cloud Technology and Services

#### Task 3.1: Define methods of deploying and operating in the AWS Cloud

Required knowledge and skill:

- Console vs CLI vs SDK vs APIs vs IaC
- One-time operations vs repeatable processes
- Cloud, hybrid, on-prem deployment models

Covered in:

- `01-cloud-fundamentals.md`
- `09-service-selection-matrix.md`
- `10-mock-question-bank.md`

#### Task 3.2: Define the AWS global infrastructure

Required knowledge and skill:

- Regions, Availability Zones, edge locations
- High availability
- Multi-AZ vs Multi-Region
- Data sovereignty and latency

Covered in:

- `01-cloud-fundamentals.md`
- `11-last-minute-revision.md`

#### Task 3.3: Identify AWS compute services

Required knowledge and skill:

- EC2
- Instance families at a high level
- Containers: ECS, EKS
- Serverless: Fargate, Lambda
- Auto Scaling
- Load balancers

Covered in:

- `02-core-services.md`
- `09-service-selection-matrix.md`
- `10-mock-question-bank.md`

#### Task 3.4: Identify AWS database services

Required knowledge and skill:

- Managed vs self-hosted databases
- RDS, Aurora, DynamoDB, ElastiCache
- Migration tools such as DMS and SCT

Covered in:

- `02-core-services.md`
- `09-service-selection-matrix.md`

#### Task 3.5: Identify AWS network services

Required knowledge and skill:

- VPC components
- Route 53
- Security groups and NACLs
- VPN and Direct Connect

Covered in:

- `02-core-services.md`
- `05-practice-review.md`
- `09-service-selection-matrix.md`

#### Task 3.6: Identify AWS storage services

Required knowledge and skill:

- Object, block, file, cached file systems
- S3 storage classes
- EBS vs instance store
- EFS, FSx
- Storage Gateway
- Lifecycle policies
- AWS Backup

Covered in:

- `02-core-services.md`
- `09-service-selection-matrix.md`
- `10-mock-question-bank.md`

#### Task 3.7: Identify AWS AI/ML services and analytics services

Required knowledge and skill:

- High-level awareness of AI/ML services
- High-level awareness of analytics services
- Match service name to major use case

Core names to recognize:

- SageMaker AI
- Lex
- Kendra
- Polly
- Rekognition
- Textract
- Transcribe
- Translate
- Comprehend
- Amazon Q
- Athena
- EMR
- Kinesis
- Glue
- OpenSearch Service
- QuickSight

Covered in:

- `09-service-selection-matrix.md`
- `08-flashcards.md`
- `10-mock-question-bank.md`

#### Task 3.8: Identify services from other in-scope AWS service categories

Required knowledge and skill:

- EventBridge, SNS, SQS
- Step Functions
- Connect, SES
- CodeBuild, CodePipeline, X-Ray
- AWS CLI
- AppStream 2.0, WorkSpaces, WorkSpaces Secure Browser
- Amplify, AppSync
- IoT Core
- AWS Support
- ECR

Covered in:

- `09-service-selection-matrix.md`
- `08-flashcards.md`
- `10-mock-question-bank.md`

### Domain 4: Billing, Pricing, and Support

#### Task 4.1: Compare AWS pricing models

Required knowledge and skill:

- On-Demand
- Reserved Instances
- Spot Instances
- Savings Plans
- Dedicated Hosts
- Dedicated Instances
- Capacity Reservations
- Storage pricing tiers
- Data transfer cost awareness

Covered in:

- `04-billing-support.md`
- `11-last-minute-revision.md`
- `10-mock-question-bank.md`

#### Task 4.2: Understand resources for billing, budget, and cost management

Required knowledge and skill:

- AWS Budgets
- Cost Explorer
- Cost and Usage Reports
- Pricing Calculator
- Organizations consolidated billing
- Cost allocation tags
- Cost and Usage Report

Covered in:

- `04-billing-support.md`
- `05-practice-review.md`
- `08-flashcards.md`

#### Task 4.3: Identify AWS technical resources and AWS Support options

Required knowledge and skill:

- Official documentation, whitepapers, blogs
- re:Post, Knowledge Center, Prescriptive Guidance
- Support plans
- Trusted Advisor
- AWS Health Dashboard
- AWS Partners and Marketplace
- Professional Services and Solutions Architects

Covered in:

- `04-billing-support.md`
- `09-service-selection-matrix.md`
- `10-mock-question-bank.md`

### High-priority in-scope service recognition list

These names are especially worth recognizing quickly:

- EC2, Auto Scaling, ELB, Lambda, Fargate, ECS, EKS, Beanstalk, Lightsail
- ECR, ECS, EKS, Fargate
- S3, EBS, EFS, FSx, S3 Glacier, Backup, Storage Gateway, Elastic Disaster Recovery
- RDS, Aurora, DocumentDB, DynamoDB, ElastiCache, Neptune, Redshift
- VPC, Route 53, CloudFront, API Gateway, Direct Connect, VPN, Site-to-Site VPN, Client VPN, Transit Gateway, PrivateLink, Global Accelerator
- IAM, IAM Identity Center, KMS, CloudHSM, CloudTrail, CloudWatch, Config, GuardDuty, Inspector, Macie, Shield, WAF, Artifact, Secrets Manager, Security Hub
- Budgets, Cost and Usage Reports, Cost Explorer, Marketplace, Organizations, Trusted Advisor, Health Dashboard, Well-Architected Tool
- SNS, SQS, EventBridge, Step Functions, SES, Connect, CodePipeline, CodeBuild, X-Ray, CLI, IoT Core, Amplify, AppSync
- Athena, EMR, Glue, Kinesis, OpenSearch Service, QuickSight
- Application Discovery Service, Application Migration Service, DMS, Migration Evaluator, Migration Hub, SCT, Snow Family

### Current official out-of-scope course names

These may appear in older YouTube courses or broad AWS training, but current AWS CLF-C02 docs mark them as out of scope:

- Amazon MSK
- Amazon WorkDocs
- Amazon WorkMail
- AWS App Runner
- AWS CodeDeploy
- AWS CloudShell
- AWS Network Firewall
- Amazon FSx for Lustre

---

## Practical Examples & Reference Snippets

Study routing example:

```text
If a task says:
- "learn IAM and root user protection" -> go to 03 + 08 + 10
- "revise service comparisons" -> go to 05 + 09 + 11
- "check if the folder covers all objectives" -> use this file
```

Coverage check workflow:

```text
Read domain task
Ask: can I explain it in one minute?
If no:
Go to mapped file
Review flashcards
Answer 3 practice questions on the same area
```

---

## 🏗️ Production Engineering Context (CRITICAL)

### 1. Decision Making: Why Choose This Design?

- Objective mapping keeps revision aligned to scoring reality rather than topic preference.
- It prevents over-investing in familiar services and under-investing in support, pricing, and security wording.

### 2. Scaling Impact: What Happens If Traffic Increases?

- As exam scope widens, recall gets harder unless material is grouped by domain and by task.
- Mapping reduces revision friction by making weak areas obvious.

### 3. Failure Modes: What Might Break?

- Studying only EC2, S3, and IAM and ignoring support, migration, analytics, and integration services
- Thinking “I know AWS” without checking official task coverage
- Missing small services that appear as distractors in multiple-choice questions

### 4. Troubleshooting: How to Fix It?

- If mock scores stay weak, identify the failing domain and task statement.
- If you cannot explain a task without notes, that area is not exam-ready.
- If a service name feels unfamiliar, add it to flashcards and the service matrix.

---

## 🔮 Memory Hooks & Practical Scenarios

### Memory Hooks

- **When**: You think “I’ve studied enough”
- **Say**: `Show me the objective map`
- **Remember**: Exam confidence without blueprint coverage is unreliable

### Real-World Scenario Q&A

Scenario 1:

- Context and environment: A learner studies only core services.
- Symptoms/signals: Good confidence, but mocks miss pricing and support questions.
- Wrong approach and why it fails: Keep repeating the same familiar notes.
- Right approach with commands: Use this map to identify unstudied domain tasks and patch coverage.
- Prevention actions: Review against the official blueprint every 2-3 study days.

Scenario 2:

- Context and environment: A learner knows IAM well but misses AI/ML and analytics service names.
- Symptoms/signals: Mock question options look unfamiliar.
- Wrong approach and why it fails: Ignore those services because they seem “advanced.”
- Right approach with commands: Learn one-line service purpose only; foundational exams test recognition, not implementation depth.
- Prevention actions: Use `09-service-selection-matrix.md` and `08-flashcards.md`.

### Mini Case Study

`Trigger -> Strong reading confidence but uneven mock scores -> Impact -> Repeated misses in smaller domains -> Investigation -> No task-by-task blueprint tracking -> Mitigation -> Build and use coverage map -> Root Cause -> Study plan was topic-based, not objective-based -> Prevention -> Review by official task statements`

---

## 🧪 Hands-On Drills

### Drill 1: Quick Lab (10-15 min)

- Objective: Verify full objective coverage.
- Setup: Open this file and hide the “Covered in” lines.
- Commands: For each task statement, say the task and name at least two relevant AWS services or concepts.
- Verification: If you hesitate for more than 15 seconds, mark that task for review.

### Drill 2: Production Simulation (20-40 min)

- Failure injection method: Take 20 mixed mock questions from `10-mock-question-bank.md`.
- Expected signals: Mistakes cluster into one or two official task statements.
- Recovery playbook: Map each wrong question back to this file and re-study only that task area.
- Rollback/cleanup steps: Add misses to your flashcard list.

---

## Quick Reference

```text
Domain 1 -> Cloud value, Well-Architected, migration, economics
Domain 2 -> Shared responsibility, compliance, IAM, security services
Domain 3 -> Deployment methods, global infra, core services, analytics, integration
Domain 4 -> Pricing, budgets, support, resources, partners
```

---

## Interview Questions

- **Question**: Why should exam prep be mapped to the official blueprint?
- **Answer**: Because AWS tests across weighted domains and task statements, not just popular services.
- **Why this matters**: It prevents blind spots.

- **Question**: Which domain usually feels “done” too early for learners?
- **Answer**: Domain 3, because learners know some core services and assume full coverage.
- **Why this matters**: Domain 3 is broad and includes analytics, integration, and other categories.

- **Question**: Why is migration still worth studying for Cloud Practitioner?
- **Answer**: Because it is explicitly called out in Domain 1 and appears as scenario knowledge, even if only at a high level.
- **Why this matters**: Small domains still produce scored questions.

- **Question**: How deep should AI/ML and analytics study go for CLF-C02?
- **Answer**: High-level service recognition and matching service to common use case.
- **Why this matters**: Foundational exams test awareness more than implementation depth.
