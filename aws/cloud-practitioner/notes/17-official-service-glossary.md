# AWS Official In-Scope Service Glossary

## What is the Service Glossary? & Why It Matters

This file is a compact recognition guide for the official AWS services that commonly appear in the current `CLF-C02` scope. For Cloud Practitioner, you do not need implementation depth for every service, but you do need to recognize the service name, its category, and its primary use case.

This glossary is designed to close the last-mile exam gap between “I know the main AWS services” and “I can quickly identify the correct answer when AWS names appear in options.”

---

## Prerequisites & Related Concepts

- `Service selection`: The exam often tests fit more than detail.
- `Official in-scope list`: AWS’s list is the cleanest boundary for what names you should recognize.
- `Foundational depth`: You usually need one-line purpose, not hands-on depth, for smaller services.

---

## Core Concepts

### Compute and application services

| Service | What it is | What to remember |
| --- | --- | --- |
| Amazon EC2 | Virtual machines in AWS | Full compute control, customer manages OS |
| EC2 Auto Scaling | Automatic EC2 scaling | Elasticity for EC2 fleets |
| Elastic Load Balancing | Managed traffic distribution | Sends traffic across healthy targets |
| AWS Lambda | Serverless function compute | Event-driven code with no server management |
| Amazon ECS | AWS-native container orchestration | Containers without Kubernetes |
| Amazon EKS | Managed Kubernetes | Use when Kubernetes is required |
| AWS Fargate | Serverless runtime for containers | Run containers without managing servers |
| AWS Elastic Beanstalk | Managed app deployment platform | Simpler application deployment |
| Amazon Lightsail | Simplified VPS-style service | Small workloads and quick starts |
| AWS Batch | Managed batch job scheduling | Large-scale batch processing |
| AWS Outposts | AWS infrastructure on-premises | Hybrid cloud use case |

### Containers and serverless services

| Service | What it is | What to remember |
| --- | --- | --- |
| Amazon Elastic Container Registry | Container image registry | Store and manage container images |
| Amazon ECS | AWS-native container orchestration | Run and orchestrate containers without Kubernetes |
| Amazon EKS | Managed Kubernetes | Use when Kubernetes is required |
| AWS Fargate | Serverless runtime for containers | Run containers without managing servers |
| AWS Lambda | Serverless function compute | Event-driven code with no server management |

### Cloud financial management services

| Service | What it is | What to remember |
| --- | --- | --- |
| AWS Budgets | Budget and alerting tool | Alerts when cost or usage crosses thresholds |
| AWS Cost and Usage Reports | Detailed billing dataset | Most detailed cost and usage data |
| AWS Cost Explorer | Cost analysis tool | Analyze historical spend and usage trends |
| AWS Marketplace | Software catalog and procurement service | Buy and deploy AWS and third-party software |

### Storage and backup services

| Service | What it is | What to remember |
| --- | --- | --- |
| Amazon S3 | Object storage | Static content, backups, storage classes |
| Amazon S3 Glacier | Archival storage classes | Low-cost long-term retention |
| Amazon EBS | Block storage for EC2 | Persistent attached disks |
| Amazon EFS | Shared managed file system | Linux file sharing across instances |
| Amazon FSx | Managed file systems | Specialized managed file workloads |
| AWS Backup | Centralized backup management | Policy-based backup across services |
| AWS Elastic Disaster Recovery | Disaster recovery service | Replicate and recover workloads |
| AWS Storage Gateway | Hybrid storage integration | Connect on-premises storage patterns to AWS |
| AWS Snow Family | Physical data transfer and edge devices | Large offline data movement and edge use cases |

### Database, cache, and analytics services

| Service | What it is | What to remember |
| --- | --- | --- |
| Amazon RDS | Managed relational databases | SQL workloads with managed operations |
| Amazon Aurora | AWS-optimized relational engine | High-performance managed relational option |
| Amazon DynamoDB | NoSQL key-value/document DB | Massive scale and low-latency access |
| Amazon ElastiCache | Managed in-memory cache | Offload reads and reduce DB pressure |
| Amazon Redshift | Data warehouse | Large-scale analytics, not transactional app DB |
| Amazon Athena | SQL query service for S3 data | Serverless SQL on S3 |
| Amazon EMR | Big data processing platform | Managed Hadoop/Spark style analytics |
| AWS Glue | Data integration and ETL | Prepares and moves data |
| Amazon QuickSight | BI dashboards and visualization | Business intelligence reporting |
| Amazon Kinesis | Streaming data platform | Real-time stream ingestion and processing |
| Amazon OpenSearch Service | Search and log analytics service | Search, observability, and analytics use cases |
| AWS Database Migration Service | Database migration service | Moves databases into AWS |
| AWS Schema Conversion Tool | Schema conversion tool | Converts schema during migrations |
| Amazon DocumentDB | Managed document database | MongoDB-compatible document workloads |
| Amazon Neptune | Managed graph database | Highly connected graph data |

### Networking, content delivery, and API services

| Service | What it is | What to remember |
| --- | --- | --- |
| Amazon VPC | Private AWS network boundary | Subnets, route tables, security design |
| Amazon Route 53 | Managed DNS | Routing users to endpoints |
| Amazon CloudFront | CDN | Low-latency content delivery from edge locations |
| Amazon API Gateway | Managed API front door | Expose and manage APIs |
| AWS Direct Connect | Dedicated network link to AWS | Private connectivity from on-premises |
| AWS VPN | Encrypted network tunnel over internet | Secure remote/private connectivity |
| AWS Site-to-Site VPN | VPN between a network and AWS | Common hybrid connectivity pattern |
| AWS Client VPN | VPN for individual client devices | Secure user access to AWS networks |
| AWS PrivateLink | Private connectivity to services | Keeps traffic on private AWS network paths |
| AWS Transit Gateway | Network hub for VPCs and networks | Central network connectivity |
| AWS Global Accelerator | Traffic acceleration using AWS network | Improves path performance for global apps |

### Security, identity, governance, and operations services

| Service | What it is | What to remember |
| --- | --- | --- |
| AWS IAM | Identity and access management | Users, roles, policies, least privilege |
| AWS IAM Identity Center | Central workforce access | SSO across accounts and apps |
| AWS KMS | Key management service | Managed encryption keys |
| AWS CloudHSM | Dedicated hardware security module service | Specialized strict key-control requirements |
| AWS Secrets Manager | Secret storage and rotation | Store app secrets safely |
| AWS Certificate Manager | TLS certificate management | Certificates for AWS-integrated services |
| Amazon Cognito | App user identity service | Sign-up and sign-in for applications |
| Amazon Detective | Security investigation service | Investigates findings and relationships |
| AWS Directory Service | Managed directory service | Microsoft AD and directory integration |
| AWS CloudTrail | API activity audit | Who did what in the account |
| Amazon CloudWatch | Metrics, logs, alarms | Monitoring and observability |
| AWS Config | Configuration tracking and compliance | Resource state history |
| AWS Artifact | Compliance reports and agreements | Audit/compliance evidence |
| Amazon GuardDuty | Threat detection | Detect suspicious behavior |
| Amazon Inspector | Vulnerability findings | Workload vulnerability scanning |
| Amazon Macie | Sensitive data discovery | Finds sensitive data such as PII in S3 |
| AWS Resource Access Manager | Resource sharing service | Share AWS resources across accounts |
| AWS WAF | Web application firewall | Filter malicious web requests |
| AWS Shield | DDoS protection | Protect against denial-of-service attacks |
| AWS Security Hub | Central security findings aggregation | Consolidated security posture view |
| AWS Audit Manager | Compliance evidence collection | Audit workflow support |
| AWS Firewall Manager | Central policy management for security controls | Governance across accounts |
| AWS Organizations | Multi-account governance and billing | Consolidated billing and guardrails |
| AWS Control Tower | Multi-account landing zone setup | Standardized account governance |
| AWS Auto Scaling | Scaling coordination service | Scale multiple AWS resource types |
| AWS CloudFormation | Infrastructure as code service | Provision AWS resources with templates |
| AWS Systems Manager | Operations management service | Manage fleets, patching, automation, and inventory |
| AWS Service Catalog | Approved service portfolio | Govern self-service provisioning |
| Service Quotas | Quota visibility and increase requests | Know and manage AWS service limits |
| AWS License Manager | License tracking and governance | Manage software license usage |
| AWS Compute Optimizer | Resource recommendation service | Rightsizing recommendations |
| AWS Trusted Advisor | Best-practice checks | Cost, security, reliability guidance |
| AWS Well-Architected Tool | Workload review service | Review workloads against Well-Architected best practices |
| AWS Health Dashboard | AWS events affecting workloads | Service and account health events |
| AWS Management Console | Web UI for AWS | Browser-based AWS management |

### Messaging, integration, end-user, and developer services

| Service | What it is | What to remember |
| --- | --- | --- |
| Amazon SQS | Managed queue | Decouple components |
| Amazon SNS | Pub/sub notifications | Fan-out alerts and events |
| Amazon EventBridge | Event bus | Route events across systems |
| AWS Step Functions | Workflow orchestration | Coordinate multi-step serverless workflows |
| Amazon SES | Email sending service | Transactional and application email |
| Amazon Connect | Cloud contact center | Customer support/contact center use |
| AWS CLI | Command-line interface | Script and automate AWS operations |
| AWS CodeBuild | Build service | CI build steps |
| AWS CodePipeline | Pipeline orchestration | Delivery workflow automation |
| AWS X-Ray | Distributed tracing | Trace requests across systems |
| AWS Amplify | Frontend/mobile app platform | Build and host web/mobile frontends |
| AWS AppSync | Managed GraphQL API service | GraphQL APIs |
| Amazon WorkSpaces | Cloud desktops | Virtual desktops |
| Amazon AppStream 2.0 | App streaming | Stream desktop applications |
| Amazon WorkSpaces Secure Browser | Isolated managed browser service | Secure browsing use cases |
| AWS IoT Core | Device connectivity and messaging | Managed IoT entry point |
| AWS Marketplace | Third-party software catalog | Buy and deploy partner software |

### AI/ML and intelligent services

| Service | What it is | What to remember |
| --- | --- | --- |
| Amazon SageMaker AI | Managed machine learning platform | Main ML platform in AWS |
| Amazon Lex | Conversational bot service | Chatbots and voice/text bots |
| Amazon Textract | Document text extraction | OCR and form/table extraction |
| Amazon Transcribe | Speech-to-text | Audio transcription |
| Amazon Translate | Machine translation | Translate text |
| Amazon Comprehend | NLP service | Sentiment and entity analysis |
| Amazon Rekognition | Image/video analysis | Computer vision tasks |
| Amazon Kendra | Intelligent enterprise search | Search across enterprise data |
| Amazon Polly | Text-to-speech | Convert text into speech |
| Amazon Q | Generative AI assistant family | AI assistant capability across AWS and business contexts |

### Migration and transfer services

| Service | What it is | What to remember |
| --- | --- | --- |
| AWS Application Discovery Service | Discovery service for migrations | Collects on-premises environment data |
| AWS Application Migration Service | Lift-and-shift server migration | Replaces CloudEndure Migration naming for modern prep |
| AWS Database Migration Service | Database migration service | Moves databases into AWS |
| Migration Evaluator | Migration business case tool | Helps assess migration cost and planning |
| AWS Migration Hub | Migration tracking hub | Central place to track migration progress |
| AWS Schema Conversion Tool | Schema conversion tool | Converts schemas during database migrations |
| AWS Snow Family | Physical data transfer and edge devices | Large offline data movement and edge use cases |

### Support and learning resources

| Service or resource | What it is | What to remember |
| --- | --- | --- |
| AWS Support plans | Official support tiers | Basic, Developer, Business, Enterprise |
| AWS Documentation | Official technical docs | Primary source for current behavior |
| AWS Whitepapers | Architecture and service guidance | Conceptual study support |
| AWS re:Post | Community and knowledge platform | Troubleshooting and Q&A |
| AWS Prescriptive Guidance | Architecture and implementation guidance | Best-practice design help |

### Official out-of-scope names you might see in courses

These names appear in some broad AWS courses or older material, but the current AWS CLF-C02 out-of-scope list marks them as not exam priorities.

| Service | Why it matters |
| --- | --- |
| Amazon MSK | Useful Kafka service, but out of scope for CLF-C02 |
| Amazon WorkDocs | Older business app topic, out of scope for CLF-C02 |
| Amazon WorkMail | Older business app topic, out of scope for CLF-C02 |
| AWS App Runner | Useful compute service, but out of scope for CLF-C02 |
| AWS CodeDeploy | Useful developer tool, but out of scope for CLF-C02 |
| AWS CloudShell | Useful browser shell service, but out of scope for CLF-C02 |
| AWS Network Firewall | Useful network security service, but out of scope for CLF-C02 |
| Amazon FSx for Lustre | Specific FSx variant, out of scope for CLF-C02 |

### What not to do with this glossary

- Do not try to memorize every feature of every service.
- Do not spend equal time on all services.
- Use this glossary for `recognition`, then return to the core notes for the high-weight topics.

---

## Practical Examples & Reference Snippets

Recognition drill:

```text
Service name appears in options
-> identify its category
-> say its one-line purpose
-> ask whether it matches the scenario more directly than the alternatives
```

Example:

```text
"Need to know who changed an IAM policy"
CloudTrail -> audit API activity
CloudWatch -> metrics/logs
Correct direction -> CloudTrail
```

---

## 🏗️ Production Engineering Context (CRITICAL)

### 1. Decision Making: Why Choose This Design?

- Foundational exams reward correct service fit.
- A one-line service purpose is often enough to eliminate wrong answers quickly.

### 2. Scaling Impact: What Happens If Traffic Increases?

- Under time pressure, too much unstructured AWS knowledge becomes noise.
- A compact glossary improves retrieval speed and reduces confusion between similar services.

### 3. Failure Modes: What Might Break?

- Mixing up audit vs monitoring
- Mixing up object vs block vs file storage
- Confusing notification, queue, and event-routing services
- Treating every AI/ML service as “some ML thing” instead of learning one-line roles

### 4. Troubleshooting: How to Fix It?

- If you miss a question because a service name feels unfamiliar, add it to your rapid-recall list.
- Review by category, not alphabetically.
- Pair this glossary with `09-service-selection-matrix.md` and `08-flashcards.md`.

---

## 🔮 Memory Hooks & Practical Scenarios

### Memory Hooks

- **When**: A service name looks familiar but fuzzy
- **Say**: `Category first, purpose second`
- **Remember**: Recognition is enough for many CLF-C02 questions

### Real-World Scenario Q&A

Scenario 1:

- Context and environment: A learner knows core services but misses smaller AWS names on mocks.
- Symptoms/signals: Wrong answers even when the topic category is understood.
- Wrong approach and why it fails: Ignore lesser-known services because they seem uncommon.
- Right approach with commands: Learn one-line purpose for each official in-scope service.
- Prevention actions: Review this glossary in short daily bursts.

Scenario 2:

- Context and environment: An exam question lists SQS, SNS, EventBridge, and Lambda.
- Symptoms/signals: All options look “event-related.”
- Wrong approach and why it fails: Choose based on which service sounds most modern.
- Right approach with commands: Match `queue`, `pub/sub`, `event routing`, or `compute` to the scenario.
- Prevention actions: Memorize category boundaries.

### Mini Case Study

`Trigger -> Mock exam misses on unfamiliar service names -> Impact -> Score stalls despite strong core knowledge -> Investigation -> Recognition gaps in smaller official services -> Mitigation -> Build one-line glossary and revise by category -> Root Cause -> Study focused only on top 10 AWS services -> Prevention -> Keep an official in-scope recognition sheet`

---

## 🧪 Hands-On Drills

### Drill 1: Quick Lab (10-15 min)

- Objective: Recognize 30 AWS service names rapidly.
- Setup: Cover the “What to remember” column.
- Commands: Say category and one-line purpose aloud.
- Verification: Answer each in under 5 seconds.

### Drill 2: Production Simulation (20-40 min)

- Failure injection method: Mix service names from unrelated categories into one quiz.
- Expected signals: Confusion between adjacent services like CloudTrail and CloudWatch, SNS and SQS.
- Recovery playbook: Rewrite misses as `service -> category -> primary use case`.
- Rollback/cleanup steps: Revisit weak categories only.

---

## Quick Reference

```text
Audit -> CloudTrail
Metrics/logs -> CloudWatch
Object storage -> S3
Block storage -> EBS
File storage -> EFS
Managed SQL -> RDS/Aurora
NoSQL -> DynamoDB
Queue -> SQS
Pub/Sub -> SNS
Event bus -> EventBridge
```

---

## Interview Questions

- **Question**: How deep should you know smaller in-scope AWS services for CLF-C02?
- **Answer**: At least enough to identify category and primary use case.
- **Why this matters**: That level is often sufficient for answer elimination.

- **Question**: Why is a service glossary useful when you already have detailed notes?
- **Answer**: Detailed notes build understanding; the glossary speeds recall under exam pressure.
- **Why this matters**: Foundational exams are also a retrieval test.

- **Question**: Which categories create the most naming confusion for learners?
- **Answer**: Security/operations, messaging/integration, and storage.
- **Why this matters**: Those categories contain many similar-sounding services.
