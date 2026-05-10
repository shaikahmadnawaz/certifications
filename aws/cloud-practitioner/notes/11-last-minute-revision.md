# AWS Last-Minute Revision Sheet

## What is the Last-Minute Revision Sheet? & Why It Matters

This file is the compressed version of the full pack for the last 24-48 hours before the exam. It is optimized for fast retrieval, comparison, and trap avoidance.

---

## Core Concepts

### Highest-yield comparisons

| Compare | Correct distinction |
| --- | --- |
| Region vs AZ | Geography vs isolated location inside a Region |
| CloudTrail vs CloudWatch | API audit vs metrics/logs/alarms |
| S3 vs EBS vs EFS | Object vs block vs file |
| RDS vs DynamoDB | Managed relational SQL vs NoSQL key-value/document |
| SNS vs SQS | Pub/sub notifications vs queueing |
| Budgets vs Cost Explorer | Alerts vs spend analysis |
| WAF vs Shield | Web request filtering vs DDoS protection |
| IAM user vs IAM role | Long-lived identity vs assumable temporary permissions |

### Shared Responsibility Model

- AWS: physical facilities, hardware, foundational managed service infrastructure
- Customer: IAM, data, configurations, guest OS on EC2, bucket policies, security groups
- Responsibility shifts more toward AWS when using higher-level managed services

### Must-know service matches

| Need | Service |
| --- | --- |
| Static site | S3 |
| CDN | CloudFront |
| DNS | Route 53 |
| VM | EC2 |
| Serverless function | Lambda |
| Containers | ECS/EKS/Fargate |
| Managed SQL | RDS/Aurora |
| NoSQL | DynamoDB |
| Shared file system | EFS |
| Block storage | EBS |
| Archive | S3 Glacier |
| Audit API calls | CloudTrail |
| Metrics and alarms | CloudWatch |
| Threat detection | GuardDuty |
| Web protection | WAF |
| DDoS protection | Shield |
| Encryption keys | KMS |
| Budget alert | AWS Budgets |
| Spend analysis | Cost Explorer |
| Cost estimate | Pricing Calculator |

### Pricing quick view

| Option | Best fit |
| --- | --- |
| On-Demand | Unpredictable workloads |
| Spot | Interruptible workloads |
| Reserved/Savings Plans | Predictable long-term workloads |
| Dedicated Hosts | Specific licensing or compliance needs |

### Global infrastructure quick view

- Region: choose for compliance, latency, service availability
- Multi-AZ: choose for high availability
- Multi-Region: choose for DR, sovereignty, global latency, continuity
- Edge location: choose for content delivery and global edge presence

### AI/ML and analytics recognition

| Need | Service |
| --- | --- |
| Managed ML platform | SageMaker AI |
| Chatbot | Lex |
| OCR/document extraction | Textract |
| Speech to text | Transcribe |
| Translate text | Translate |
| Sentiment/text analysis | Comprehend |
| SQL on S3 | Athena |
| ETL | Glue |
| BI dashboards | QuickSight |
| Streams | Kinesis |

### Small but testable services

- EventBridge: event bus
- SNS: notifications
- SQS: queues
- SES: email
- Connect: contact center
- CodeBuild: build
- CodePipeline: release pipeline
- X-Ray: tracing
- Amplify: frontend/mobile workflow
- IoT Core: device connectivity
- Artifact: compliance reports
- Trusted Advisor: best-practice checks
- Health Dashboard: AWS environment health events

---

## Practical Examples & Reference Snippets

Fast answer method:

```text
1. Identify category
2. Find clue words
3. Remove wrong category answers
4. Choose the simplest direct managed service
```

Clue words:

```text
static -> S3
shared files -> EFS
audit -> CloudTrail
alert on spend -> Budgets
historical spend -> Cost Explorer
event-driven -> Lambda
queue -> SQS
pub/sub -> SNS
global low latency -> CloudFront
```

---

## Quick Reference

```text
Security of the cloud -> AWS
Security in the cloud -> Customer
Object -> S3
Block -> EBS
File -> EFS
Managed SQL -> RDS/Aurora
NoSQL -> DynamoDB
Audit -> CloudTrail
Metrics -> CloudWatch
Least privilege -> minimum required permissions
```
