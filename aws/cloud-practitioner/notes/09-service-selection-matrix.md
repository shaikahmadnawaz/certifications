# AWS Service Selection Matrix

## What is the Service Selection Matrix? & Why It Matters

This file maps common exam scenarios to the most likely AWS answer. Cloud Practitioner questions often look simple, but the real challenge is choosing the most fitting managed service and rejecting plausible distractors.

---

## Core Concepts

### Compute selection

| Need | Best-fit service | Why |
| --- | --- | --- |
| Full VM control | EC2 | You manage the operating system and instance behavior |
| Short event-driven code | Lambda | No server management, execution-based pricing |
| Containers without managing servers | Fargate | Serverless container runtime |
| Containers with AWS-managed orchestration | ECS | Simpler AWS-native container orchestration |
| Kubernetes workloads | EKS | Managed Kubernetes control plane |
| Fast platform-style app deployment | Elastic Beanstalk | Simplifies deployment and environment management |
| Small simple workloads | Lightsail | Easy and predictable starter option |

### Storage selection

| Need | Best-fit service | Why |
| --- | --- | --- |
| Static website files | S3 | Durable object storage, simple web delivery |
| Shared files for Linux fleet | EFS | Shared managed file system |
| Disk for one EC2 instance | EBS | Persistent block storage |
| Temporary fast host-attached storage | Instance store | Ephemeral storage on host |
| Archive retention | S3 Glacier | Lower-cost long-term storage |
| Backup across services | AWS Backup | Centralized backup management |
| Hybrid cached file access | Storage Gateway | Connects on-premises environments to AWS storage |

### Database selection

| Need | Best-fit service | Why |
| --- | --- | --- |
| Managed relational SQL database | RDS | Managed relational engine platform |
| High-performance managed relational database | Aurora | AWS-optimized relational engine |
| NoSQL key-value/document at scale | DynamoDB | High-scale low-latency NoSQL |
| In-memory cache | ElastiCache | Faster reads and lower DB load |
| Analytics warehouse | Redshift | Large-scale analytics workloads |
| Database migration | AWS DMS | Moves databases to AWS |
| Schema conversion | AWS SCT | Converts schema during migration |

### Networking selection

| Need | Best-fit service | Why |
| --- | --- | --- |
| Private AWS network | VPC | Core network boundary |
| DNS and domain routing | Route 53 | Managed DNS |
| Global content acceleration | CloudFront | CDN with edge caching |
| API front door | API Gateway | Managed API publishing |
| Dedicated private link from data center | Direct Connect | Private connectivity |
| Encrypted internet connection to AWS | VPN | Secure tunnel over the internet |

### Security and governance selection

| Need | Best-fit service | Why |
| --- | --- | --- |
| Identity and permissions | IAM | Core access management |
| Workforce SSO and account access | IAM Identity Center | Central access portal |
| Encryption key management | KMS | Managed key service |
| Secret storage and rotation | Secrets Manager | Built for secrets lifecycle |
| API activity audit | CloudTrail | Records API calls |
| Metrics, logs, alarms | CloudWatch | Observability and alerting |
| Config tracking and compliance | AWS Config | Resource state history and rules |
| Compliance reports | AWS Artifact | Official AWS compliance documents |
| Threat detection | GuardDuty | Managed threat detection |
| Web exploit filtering | WAF | Layer 7 request filtering |
| DDoS protection | Shield | DDoS defense |
| Best-practice recommendations | Trusted Advisor | Cost, security, and resilience checks |

### Messaging, integration, developer, and other categories

| Need | Best-fit service | Why |
| --- | --- | --- |
| Decoupled queue | SQS | Managed message queue |
| Fan-out notifications | SNS | Pub/sub notifications |
| Event routing | EventBridge | Event bus and routing |
| Email sending | SES | Managed email delivery |
| Contact center | Connect | Cloud contact center |
| Build step in CI | CodeBuild | Managed builds |
| Pipeline orchestration | CodePipeline | Delivery pipeline service |
| Distributed tracing | X-Ray | Request tracing across services |
| Frontend app hosting and workflow | Amplify | Frontend/web mobile workflows |
| GraphQL API layer | AppSync | Managed GraphQL API |
| Virtual desktops/app streaming | WorkSpaces/AppStream 2.0 | End-user computing |
| IoT device connectivity | IoT Core | Device messaging and management |

### AI/ML and analytics recognition

| Need | Best-fit service | Why |
| --- | --- | --- |
| Managed ML platform | SageMaker AI | Core ML platform |
| Chatbot/conversational interface | Lex | Voice and text bots |
| Document text extraction | Textract | OCR and document extraction |
| Speech to text | Transcribe | Audio transcription |
| Text translation | Translate | Machine translation |
| Text sentiment/entity analysis | Comprehend | NLP analysis |
| Search across enterprise data | Kendra | Intelligent search |
| Data in S3 queried with SQL | Athena | Serverless SQL queries |
| Streaming data ingestion | Kinesis | Stream processing |
| ETL/data prep | Glue | Data integration |
| Dashboards and BI | QuickSight | Visualization and BI |

### Migration and support recognition

| Need | Best-fit service | Why |
| --- | --- | --- |
| Large offline data transfer | Snow Family | Physical data transfer devices |
| Application migration to AWS | Application Migration Service | Lift-and-shift style app migration |
| Portfolio and migration tracking | Migration Hub | Migration visibility |
| AWS billing and account support | AWS Support | Official support plans |
| Marketplace third-party software | AWS Marketplace | Curated software catalog |
| Health events affecting environment | AWS Health Dashboard | AWS event visibility |

### Common traps

| If you see | Avoid choosing | Prefer |
| --- | --- | --- |
| Static website | EC2 | S3 |
| Shared Linux files | EBS | EFS |
| Audit API calls | CloudWatch | CloudTrail |
| Threshold alert on spend | Cost Explorer | Budgets |
| Future cost estimate | Cost Explorer | Pricing Calculator |
| Temporary service-to-service credentials | IAM user access keys | IAM role |
| Interruptible batch | On-Demand only | Spot |
| Event-driven function | EC2 | Lambda |

---

## Practical Examples & Reference Snippets

Scenario workflow:

```text
Question says:
"Company needs a shared file system for multiple Linux EC2 instances"
Category -> Storage
Pattern -> Shared file system
Answer -> EFS
```

Second workflow:

```text
Question says:
"Team wants to know who changed an IAM policy yesterday"
Category -> Security/Audit
Pattern -> API activity history
Answer -> CloudTrail
```

---

## Quick Reference

```text
Static site -> S3
Queue -> SQS
Notification -> SNS
Event routing -> EventBridge
SQL DB -> RDS
NoSQL -> DynamoDB
CDN -> CloudFront
DNS -> Route 53
Audit -> CloudTrail
Metrics/logs -> CloudWatch
```
