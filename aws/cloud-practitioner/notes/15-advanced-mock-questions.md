# AWS Advanced Mock Question Bank

## What is This File? & Why It Matters

These questions are in the **real exam format**: 4 options (A, B, C, D), plausible distractors, scenario wording. Use this file **after** you know the basics. The goal is elimination practice.

---

## How to Use

1. Cover the answer with your hand
2. Read the full scenario
3. Eliminate obviously wrong options FIRST
4. Choose between the 1-2 remaining options
5. Read the explanation — especially for why wrong options are wrong

Target: **80%+ on each set of 25** before booking the real exam.

---

## Set 1: Cloud Concepts & Well-Architected (Questions 1–25)

### Q1
A startup wants to minimize upfront costs and only pay for resources they use. Which AWS benefit best describes this?
- A) Elasticity
- B) Pay-as-you-go pricing
- C) High availability
- D) Fault tolerance

<details><summary>Answer</summary>

**B. Pay-as-you-go pricing**

- A is wrong: elasticity is about scaling, not cost structure
- C/D are wrong: these are reliability benefits, not pricing
</details>

### Q2
Which Well-Architected pillar focuses on minimizing the environmental impact of running cloud workloads?
- A) Operational Excellence
- B) Performance Efficiency
- C) Sustainability
- D) Reliability

<details><summary>Answer</summary>

**C. Sustainability**

Added in 2021 as the 6th pillar.
</details>

### Q3
A company deploys an application across multiple Availability Zones. Which Well-Architected pillar does this BEST support?
- A) Cost Optimization
- B) Reliability
- C) Security
- D) Sustainability

<details><summary>Answer</summary>

**B. Reliability**

Multi-AZ is the canonical Reliability pattern (HA, fault tolerance).
</details>

### Q4
Which statement best describes the shared responsibility model?
- A) AWS is responsible for all security
- B) The customer is responsible for all security
- C) AWS is responsible for security OF the cloud; customer is responsible for security IN the cloud
- D) Both parties share 50/50 responsibility for everything

<details><summary>Answer</summary>

**C**

The exact AWS phrasing. Memorize this sentence.
</details>

### Q5
A customer runs EC2 instances. Who is responsible for patching the guest operating system?
- A) AWS
- B) The customer
- C) AWS and the customer share responsibility
- D) The EC2 service handles it automatically

<details><summary>Answer</summary>

**B. The customer**

Customer = security IN the cloud = OS patching on EC2, IAM, data.
</details>

### Q6
A company needs to migrate to AWS while rewriting applications for cloud-native benefits like serverless. Which migration strategy applies?
- A) Rehost
- B) Replatform
- C) Refactor
- D) Retire

<details><summary>Answer</summary>

**C. Refactor**

Rewriting for cloud-native = Refactor / Re-architect. Rehost is lift-and-shift with no changes.
</details>

### Q7
Which AWS CAF perspective addresses organizational skills and training for cloud adoption?
- A) Business
- B) People
- C) Governance
- D) Operations

<details><summary>Answer</summary>

**B. People**

People = HR, talent, training, org change. Business = outcomes; Governance = risk/compliance; Operations = running services.
</details>

### Q8
A company wants to move VMware infrastructure to AWS without changing VMs. Which strategy?
- A) Rehost
- B) Relocate
- C) Repurchase
- D) Retire

<details><summary>Answer</summary>

**B. Relocate**

Relocate = hypervisor-level lift (e.g., VMware Cloud on AWS). Rehost moves individual servers.
</details>

### Q9
Which two benefits does AWS's global infrastructure provide? (Choose TWO)
- A) Eliminates the need for any security configuration
- B) Allows deployment closer to end users for lower latency
- C) Provides fault isolation via Availability Zones
- D) Guarantees 100% uptime
- E) Removes the need for monitoring

<details><summary>Answer</summary>

**B and C**

A, D, E are nonsense absolutes. AWS does not guarantee 100% uptime — SLAs are in the 99.9%+ range.
</details>

### Q10
A financial firm must store customer data in a specific country due to regulations. Which AWS concept is most relevant?
- A) Edge Location
- B) Availability Zone
- C) Region selection
- D) CloudFront distribution

<details><summary>Answer</summary>

**C. Region selection**

Data residency = pick the right Region.
</details>

### Q11
Which is NOT one of the 6 Well-Architected pillars?
- A) Operational Excellence
- B) Scalability
- C) Cost Optimization
- D) Sustainability

<details><summary>Answer</summary>

**B. Scalability**

Scalability is not a pillar name. The 6 pillars are: Operational Excellence, Security, Reliability, Performance Efficiency, Cost Optimization, Sustainability.
</details>

### Q12
A company's workload runs 24/7, usage is predictable for the next 3 years. Which pricing approach is MOST cost-effective?
- A) On-Demand Instances
- B) Spot Instances
- C) Reserved Instances or Savings Plans (3-year)
- D) Dedicated Hosts

<details><summary>Answer</summary>

**C. Reserved Instances or Savings Plans (3-year)**

Predictable + long-term = reservation for max savings (up to 72%).
</details>

### Q13
Which is a customer responsibility under the shared responsibility model?
- A) Patching the hypervisor
- B) Maintaining data center power
- C) Configuring IAM user permissions
- D) Securing physical hardware

<details><summary>Answer</summary>

**C. Configuring IAM user permissions**

A, B, D are all AWS responsibilities (security OF the cloud).
</details>

### Q14
A company wants to decommission a legacy application that no one uses. Which 7 Rs strategy applies?
- A) Rehost
- B) Retain
- C) Retire
- D) Repurchase

<details><summary>Answer</summary>

**C. Retire**

Retire = turn it off. Retain = keep on-prem for now.
</details>

### Q15
What does "elasticity" mean in AWS?
- A) Ability to scale resources up or down based on demand
- B) Physical durability of data centers
- C) Network speed between Regions
- D) Length of customer contracts

<details><summary>Answer</summary>

**A**
</details>

### Q16
A team wants to automate security checks and enforce IaC changes with reviews. Which Well-Architected pillar best covers this?
- A) Security only
- B) Operational Excellence
- C) Cost Optimization
- D) Performance Efficiency

<details><summary>Answer</summary>

**B. Operational Excellence**

"Perform operations as code" + "small reversible changes" = Operational Excellence design principles.
</details>

### Q17
Which AWS advantage is BEST described as "trade capital expense for variable expense"?
- A) Elasticity
- B) Fault tolerance
- C) CapEx to OpEx shift
- D) Global reach

<details><summary>Answer</summary>

**C. CapEx to OpEx shift**

Direct AWS marketing phrasing.
</details>

### Q18
What is AWS Artifact primarily used for?
- A) Building artifacts for CI/CD pipelines
- B) Accessing AWS compliance reports and agreements
- C) Storing deployment packages
- D) Managing S3 bucket artifacts

<details><summary>Answer</summary>

**B**

Distractor A is a trap — "artifact" sounds like CI/CD but it's compliance reports.
</details>

### Q19
Which two are characteristics of cloud computing per NIST? (Choose TWO)
- A) On-demand self-service
- B) Dedicated private hardware for each user
- C) Rapid elasticity
- D) Fixed monthly fees regardless of use
- E) No internet required

<details><summary>Answer</summary>

**A and C**

NIST 5 essentials: on-demand self-service, broad network access, resource pooling, rapid elasticity, measured service.
</details>

### Q20
Which AWS service helps review workloads against best practices based on the Well-Architected Framework?
- A) AWS Trusted Advisor
- B) AWS Well-Architected Tool
- C) AWS Config
- D) AWS Artifact

<details><summary>Answer</summary>

**B. AWS Well-Architected Tool**

Trusted Advisor also checks best practices but is not the WAF tool.
</details>

### Q21
A company uses the AWS Application Migration Service to move servers as-is. Which strategy is this?
- A) Rehost
- B) Replatform
- C) Refactor
- D) Retain

<details><summary>Answer</summary>

**A. Rehost**

MGN = lift-and-shift for servers.
</details>

### Q22
Which CAF perspective is responsible for risk, compliance, and measuring cloud initiatives?
- A) Business
- B) Governance
- C) Operations
- D) Platform

<details><summary>Answer</summary>

**B. Governance**
</details>

### Q23
An edge location is primarily used for:
- A) Running EC2 instances
- B) Hosting databases
- C) Caching content closer to end users
- D) Storing long-term archives

<details><summary>Answer</summary>

**C**

Edge locations = CloudFront CDN + Route 53 DNS.
</details>

### Q24
Which design principle BEST supports the Reliability pillar?
- A) Pay for what you use
- B) Automatically recover from failure
- C) Encrypt data at rest
- D) Use managed AI/ML services

<details><summary>Answer</summary>

**B**
</details>

### Q25
A company wants to replace an on-prem CRM with Salesforce. Which 7 Rs strategy?
- A) Refactor
- B) Replatform
- C) Repurchase
- D) Relocate

<details><summary>Answer</summary>

**C. Repurchase**

"Drop-and-shop" = buy a SaaS/different product.
</details>

---

## Set 2: Security & Compliance (Questions 26–50)

### Q26
Which AWS service records all API activity for audit purposes?
- A) Amazon CloudWatch
- B) AWS CloudTrail
- C) AWS Config
- D) AWS Trusted Advisor

<details><summary>Answer</summary>

**B. AWS CloudTrail**

Common trap: CloudWatch = metrics/logs; CloudTrail = API audit.
</details>

### Q27
An IAM user has an explicit DENY in one policy and an ALLOW for the same action in another. What happens?
- A) ALLOW wins
- B) DENY wins
- C) Random outcome
- D) User is prompted to choose

<details><summary>Answer</summary>

**B. DENY wins**

Explicit deny always overrides allow in IAM policy evaluation.
</details>

### Q28
Which AWS service provides managed DDoS protection at no extra cost for most AWS services?
- A) AWS WAF
- B) AWS Shield Standard
- C) AWS GuardDuty
- D) Amazon Inspector

<details><summary>Answer</summary>

**B. AWS Shield Standard**

Free and automatic. Shield Advanced is paid and more comprehensive.
</details>

### Q29
A developer needs to grant an EC2 instance permission to read from an S3 bucket. What is the BEST practice?
- A) Store access keys on the instance
- B) Attach an IAM role to the instance
- C) Use the root user's credentials
- D) Hard-code keys in the application

<details><summary>Answer</summary>

**B. Attach an IAM role to the instance**

Roles = temporary credentials, no key rotation, no exposure.
</details>

### Q30
Which service detects compromised EC2 instances and unusual API calls?
- A) AWS Inspector
- B) Amazon Macie
- C) Amazon GuardDuty
- D) AWS WAF

<details><summary>Answer</summary>

**C. Amazon GuardDuty**

Inspector = vulnerability scanning; Macie = sensitive data in S3.
</details>

### Q31
A company wants to discover sensitive data (e.g., PII, credit cards) stored in S3. Which service?
- A) AWS Macie
- B) Amazon Inspector
- C) AWS GuardDuty
- D) AWS Shield

<details><summary>Answer</summary>

**A. AWS Macie**

Macie = PII/sensitive data discovery in S3.
</details>

### Q32
Which IAM feature provides temporary security credentials via role assumption?
- A) Access keys
- B) Password policies
- C) AWS STS (Security Token Service)
- D) KMS

<details><summary>Answer</summary>

**C. AWS STS**

STS issues the temporary credentials when a role is assumed.
</details>

### Q33
Which two are AWS responsibilities in the shared responsibility model? (Choose TWO)
- A) Managing physical security of data centers
- B) Patching guest OS on EC2
- C) Managing the hypervisor
- D) Configuring S3 bucket policies
- E) Rotating application secrets

<details><summary>Answer</summary>

**A and C**

Both are "security OF the cloud."
</details>

### Q34
Which service is used for centrally managing encryption keys?
- A) AWS Secrets Manager
- B) AWS KMS
- C) AWS CloudHSM
- D) AWS Certificate Manager

<details><summary>Answer</summary>

**B. AWS KMS**

KMS = common default. CloudHSM = dedicated hardware (specialized compliance).
</details>

### Q35
Which service provides best-practice checks for cost, security, performance, fault tolerance, and service limits?
- A) AWS Config
- B) AWS Trusted Advisor
- C) AWS Well-Architected Tool
- D) AWS CloudTrail

<details><summary>Answer</summary>

**B. AWS Trusted Advisor**
</details>

### Q36
A company needs to enforce MFA for all IAM users. What is the BEST approach?
- A) Manually ask each user to enable it
- B) Use an IAM policy to deny actions unless MFA is present
- C) Enable MFA once on the root account
- D) Use CloudTrail to find non-MFA users

<details><summary>Answer</summary>

**B**

Policy condition `aws:MultiFactorAuthPresent` enforces MFA for API calls.
</details>

### Q37
Which service helps protect web apps against SQL injection and XSS attacks?
- A) AWS Shield
- B) AWS WAF
- C) Amazon GuardDuty
- D) AWS KMS

<details><summary>Answer</summary>

**B. AWS WAF**

WAF = Layer 7 filtering. Shield = DDoS (Layer 3/4).
</details>

### Q38
A company has 20 AWS accounts and wants centralized guardrails to prevent deletion of CloudTrail logs. Which service?
- A) IAM
- B) AWS Organizations with Service Control Policies
- C) AWS Config
- D) AWS Artifact

<details><summary>Answer</summary>

**B**

SCPs = max-permission guardrails across accounts.
</details>

### Q39
What is the BEST way to protect the AWS root user account?
- A) Share credentials with a small team
- B) Enable MFA and use it only for tasks that require root
- C) Use the root user for daily admin tasks
- D) Create an access key for the root user

<details><summary>Answer</summary>

**B**

AWS explicitly recommends: don't use root daily, enable MFA, no access keys for root.
</details>

### Q40
Which service tracks resource configuration changes over time?
- A) CloudTrail
- B) CloudWatch
- C) AWS Config
- D) Trusted Advisor

<details><summary>Answer</summary>

**C. AWS Config**

Config = "What is the state of my resources, and did it change?"
</details>

### Q41
A team wants to store and automatically rotate database passwords. Which service?
- A) AWS Systems Manager Parameter Store (Standard tier)
- B) AWS Secrets Manager
- C) AWS KMS
- D) AWS Artifact

<details><summary>Answer</summary>

**B. AWS Secrets Manager**

Has built-in automatic rotation. Parameter Store can store secrets but doesn't rotate automatically in Standard tier.
</details>

### Q42
Which AWS compliance program reports would you find in AWS Artifact? (Choose TWO)
- A) SOC 2
- B) Source code of AWS services
- C) ISO 27001
- D) EC2 instance metadata

<details><summary>Answer</summary>

**A and C**

SOC, ISO, PCI DSS reports. AWS source code is not public.
</details>

### Q43
Which best describes the principle of least privilege?
- A) Give users admin access, then remove what they don't need
- B) Grant only the permissions needed to perform a task, nothing more
- C) Always deny all access by default
- D) Share credentials within teams for simplicity

<details><summary>Answer</summary>

**B**
</details>

### Q44
A workforce needs to log in to multiple AWS accounts with one identity. Which service?
- A) AWS IAM users in each account
- B) AWS IAM Identity Center
- C) AWS Organizations
- D) AWS STS

<details><summary>Answer</summary>

**B. AWS IAM Identity Center**

Single sign-on across accounts + apps.
</details>

### Q45
Which service is used to inspect EC2 instances and container images for vulnerabilities?
- A) GuardDuty
- B) Amazon Inspector
- C) Macie
- D) Shield

<details><summary>Answer</summary>

**B. Amazon Inspector**
</details>

### Q46
Which IAM policy statement applies to ALL AWS identities in the account?
- A) Identity-based policy
- B) Resource-based policy
- C) Service Control Policy (SCP)
- D) Session policy

<details><summary>Answer</summary>

**C. SCP**

At org/OU level, applies to all identities in the account including root.
</details>

### Q47
A security team wants encryption keys under strict single-tenant hardware control for regulatory reasons. Which service?
- A) AWS KMS
- B) AWS CloudHSM
- C) AWS Secrets Manager
- D) ACM

<details><summary>Answer</summary>

**B. AWS CloudHSM**

Dedicated HSM hardware = strictest control. KMS is shared multi-tenant.
</details>

### Q48
A company's workload runs in a VPC and must access S3 without traffic going over the internet. What should they use?
- A) NAT Gateway
- B) Internet Gateway
- C) VPC Gateway Endpoint for S3
- D) VPN

<details><summary>Answer</summary>

**C. VPC Gateway Endpoint for S3**

Gateway endpoints for S3 and DynamoDB are free and route privately.
</details>

### Q49
Which is TRUE about Security Groups?
- A) They are stateless
- B) They support both allow and deny rules
- C) They are stateful and only support allow rules
- D) They apply at the subnet level

<details><summary>Answer</summary>

**C**

SGs = stateful, allow-only, instance-level. NACLs = stateless, allow+deny, subnet-level.
</details>

### Q50
Which service provides a centralized view of security alerts and compliance status across AWS accounts?
- A) AWS Security Hub
- B) AWS CloudTrail
- C) Amazon Macie
- D) AWS WAF

<details><summary>Answer</summary>

**A. AWS Security Hub**
</details>

---

## Set 3: Cloud Technology & Services (Questions 51–80)

### Q51
A company wants to run containerized microservices without managing servers. Which combination is BEST?
- A) EC2 + Docker
- B) ECS on Fargate
- C) Elastic Beanstalk
- D) Lightsail

<details><summary>Answer</summary>

**B. ECS on Fargate**

Fargate = serverless container runtime; ECS = orchestration. No EC2 management.
</details>

### Q52
Which service runs code in response to triggers without provisioning servers?
- A) EC2
- B) Lambda
- C) Elastic Beanstalk
- D) ECS

<details><summary>Answer</summary>

**B. Lambda**
</details>

### Q53
An application needs a single disk for one EC2 instance. Which storage?
- A) S3
- B) EBS
- C) EFS
- D) Glacier

<details><summary>Answer</summary>

**B. EBS**

EBS = block, attached to one instance (one AZ).
</details>

### Q54
Multiple Linux EC2 instances across AZs need shared file access. Which storage?
- A) EBS
- B) S3
- C) EFS
- D) FSx for Windows File Server

<details><summary>Answer</summary>

**C. EFS**

EFS = shared file system across AZs for Linux.
</details>

### Q55
Which S3 storage class is BEST for data accessed once or twice a year with retrieval in 12 hours?
- A) S3 Standard
- B) S3 Intelligent-Tiering
- C) S3 Glacier Deep Archive
- D) S3 One Zone-IA

<details><summary>Answer</summary>

**C. S3 Glacier Deep Archive**

Cheapest class, 12h retrieval, for rarely-accessed archive.
</details>

### Q56
Which feature automatically moves S3 objects between storage classes based on rules?
- A) S3 Versioning
- B) S3 Lifecycle policies
- C) S3 Object Lock
- D) S3 Transfer Acceleration

<details><summary>Answer</summary>

**B. S3 Lifecycle policies**
</details>

### Q57
A company has 500 GB of data to transfer from a remote site with unreliable internet. Which is BEST?
- A) DataSync
- B) Direct Connect
- C) Snowball Edge
- D) S3 Transfer Acceleration

<details><summary>Answer</summary>

**C. Snowball Edge**

No/unreliable internet + large offline transfer = Snow Family. (Note: as of Nov 2025, new customers can't order; exam still tests this.)
</details>

### Q58
Which database is BEST for millisecond key-value lookups at massive scale?
- A) RDS for MySQL
- B) DynamoDB
- C) Redshift
- D) Aurora

<details><summary>Answer</summary>

**B. DynamoDB**

NoSQL key-value, single-digit ms latency.
</details>

### Q59
A company wants to run analytics queries over terabytes of historical data. Which service?
- A) RDS
- B) DynamoDB
- C) Redshift
- D) ElastiCache

<details><summary>Answer</summary>

**C. Redshift**

Redshift = data warehouse for analytics.
</details>

### Q60
What is the purpose of Auto Scaling?
- A) To automatically back up data
- B) To adjust compute capacity up or down based on demand
- C) To distribute traffic across instances
- D) To encrypt EBS volumes

<details><summary>Answer</summary>

**B**

Traffic distribution = ELB; that's a different service.
</details>

### Q61
Which service distributes incoming traffic across multiple targets?
- A) Route 53
- B) Elastic Load Balancing (ELB)
- C) CloudFront
- D) Auto Scaling

<details><summary>Answer</summary>

**B. ELB**
</details>

### Q62
Which service is AWS's content delivery network (CDN)?
- A) Route 53
- B) CloudFront
- C) Global Accelerator
- D) Direct Connect

<details><summary>Answer</summary>

**B. CloudFront**

Global Accelerator = network-layer routing, NOT caching.
</details>

### Q63
A gaming company needs low-latency TCP/UDP routing globally with static IPs. Which service?
- A) CloudFront
- B) Route 53
- C) Global Accelerator
- D) ELB

<details><summary>Answer</summary>

**C. Global Accelerator**

Non-HTTP + static IPs = Global Accelerator.
</details>

### Q64
Which connectivity option provides a dedicated private network link from on-prem to AWS?
- A) Site-to-Site VPN
- B) AWS Direct Connect
- C) Internet Gateway
- D) NAT Gateway

<details><summary>Answer</summary>

**B. Direct Connect**

DX = dedicated line, not over internet. VPN = encrypted over internet.
</details>

### Q65
A company has 15 VPCs and wants to connect them with simple transitive routing. Which service?
- A) VPC Peering
- B) AWS Transit Gateway
- C) Direct Connect Gateway
- D) Internet Gateway

<details><summary>Answer</summary>

**B. Transit Gateway**

VPC Peering is 1:1 and not transitive — doesn't scale to 15 VPCs.
</details>

### Q66
Which service is used for infrastructure as code (IaC) on AWS?
- A) AWS Config
- B) AWS CloudFormation
- C) AWS CodeDeploy
- D) Elastic Beanstalk

<details><summary>Answer</summary>

**B. CloudFormation**
</details>

### Q67
Which service is BEST for a highly available, managed PostgreSQL-compatible database with 5x performance?
- A) RDS for PostgreSQL
- B) Aurora PostgreSQL
- C) DynamoDB
- D) Redshift

<details><summary>Answer</summary>

**B. Aurora PostgreSQL**

Aurora = AWS-optimized, 5x MySQL / 3x PostgreSQL performance claim.
</details>

### Q68
A company has a static website. Which combination is MOST cost-effective?
- A) EC2 + EBS
- B) S3 + CloudFront
- C) Lambda + DynamoDB
- D) Lightsail

<details><summary>Answer</summary>

**B. S3 + CloudFront**

S3 for static hosting, CloudFront for global caching.
</details>

### Q69
Which compute service is BEST for running a monolithic Java web app with easy deployment?
- A) Lambda
- B) ECS
- C) Elastic Beanstalk
- D) Batch

<details><summary>Answer</summary>

**C. Elastic Beanstalk**

Upload code → Beanstalk handles env (EC2, ELB, autoscaling).
</details>

### Q70
Which messaging service decouples microservices with a queue?
- A) SNS
- B) SQS
- C) EventBridge
- D) SES

<details><summary>Answer</summary>

**B. SQS**
</details>

### Q71
Which service is BEST for one-to-many pub/sub notifications?
- A) SQS
- B) SNS
- C) SES
- D) Kinesis

<details><summary>Answer</summary>

**B. SNS**
</details>

### Q72
Which service routes events between AWS services and custom applications using rules?
- A) SNS
- B) SQS
- C) EventBridge
- D) Step Functions

<details><summary>Answer</summary>

**C. EventBridge**

Event bus with rule-based routing, SaaS integrations.
</details>

### Q73
A company wants to query data directly in S3 using SQL without loading into a database. Which service?
- A) Redshift
- B) Athena
- C) EMR
- D) QuickSight

<details><summary>Answer</summary>

**B. Athena**

Serverless SQL over S3.
</details>

### Q74
Which service is AWS's main managed ML platform?
- A) SageMaker AI
- B) Comprehend
- C) Rekognition
- D) Polly

<details><summary>Answer</summary>

**A. SageMaker AI**
</details>

### Q75
Which service extracts text from scanned PDF documents?
- A) Rekognition
- B) Textract
- C) Comprehend
- D) Transcribe

<details><summary>Answer</summary>

**B. Textract**

Rekognition = images/video; Transcribe = speech-to-text; Comprehend = NLP analysis.
</details>

### Q76
Which 3 are ways to interact with AWS? (Choose THREE)
- A) AWS Management Console
- B) AWS CLI
- C) SDKs and APIs
- D) SSH directly to AWS servers
- E) Physical keyboard at a data center

<details><summary>Answer</summary>

**A, B, C**
</details>

### Q77
Which service provides virtual desktops to end users?
- A) WorkSpaces
- B) AppStream 2.0
- C) Lightsail
- D) EC2

<details><summary>Answer</summary>

**A. WorkSpaces**

AppStream = stream applications (not full desktops).
</details>

### Q78
Which two services help monitor and trace microservices? (Choose TWO)
- A) CloudWatch
- B) AWS X-Ray
- C) Trusted Advisor
- D) AWS Artifact

<details><summary>Answer</summary>

**A and B**

X-Ray = distributed tracing; CloudWatch = metrics/logs.
</details>

### Q79
Which service is designed for real-time streaming data ingestion at scale?
- A) Kinesis
- B) SQS
- C) Glue
- D) Athena

<details><summary>Answer</summary>

**A. Kinesis**
</details>

### Q80
Which service provides managed, scalable Kubernetes?
- A) ECS
- B) EKS
- C) Fargate
- D) Beanstalk

<details><summary>Answer</summary>

**B. EKS**
</details>

---

## Set 4: Billing, Pricing & Support (Questions 81–100)

### Q81
Which two services help estimate AWS costs BEFORE building? (Choose TWO)
- A) AWS Pricing Calculator
- B) AWS Cost Explorer
- C) AWS Budgets
- D) AWS TCO Calculator
- E) AWS Trusted Advisor

<details><summary>Answer</summary>

**A and D**

Pricing Calculator = current AWS pricing. TCO Calculator = compare to on-prem total cost. Cost Explorer analyzes past spend, not future.
</details>

### Q82
Which service sends an alert when actual spend exceeds a threshold?
- A) Cost Explorer
- B) AWS Budgets
- C) Pricing Calculator
- D) Trusted Advisor

<details><summary>Answer</summary>

**B. AWS Budgets**

Explorer = analyze. Budgets = alert.
</details>

### Q83
A team with steady compute needs wants max savings but might change instance type later. Which is BEST?
- A) Standard Reserved Instances
- B) Convertible Reserved Instances
- C) Compute Savings Plans
- D) Spot Instances

<details><summary>Answer</summary>

**C. Compute Savings Plans**

Most flexible: works across EC2 families, Regions, Lambda, Fargate. Convertible RIs are flexible but limited to EC2.
</details>

### Q84
Which support plan includes access to a Technical Account Manager (TAM)?
- A) Basic
- B) Developer
- C) Business
- D) Enterprise

<details><summary>Answer</summary>

**D. Enterprise**

Also Enterprise On-Ramp (limited TAM). Business does NOT include a dedicated TAM.
</details>

### Q85
Which is the minimum support plan for 24/7 phone and chat access to Cloud Support Engineers?
- A) Basic
- B) Developer
- C) Business
- D) None of the above

<details><summary>Answer</summary>

**C. Business**

Basic = billing only. Developer = business-hours email.
</details>

### Q86
A company has 10 accounts and wants one bill with volume discounts. Which feature?
- A) AWS Budgets
- B) AWS Organizations consolidated billing
- C) Cost Explorer
- D) AWS Artifact

<details><summary>Answer</summary>

**B. Organizations consolidated billing**

Volume discounts (tiered pricing) apply across all linked accounts.
</details>

### Q87
Which is TRUE about AWS Free Tier?
- A) It's only available for 30 days
- B) It includes Always Free, 12-month Free, and Trial offers
- C) All AWS services have a free tier
- D) Free tier includes unlimited data transfer

<details><summary>Answer</summary>

**B**

Three tiers: Always Free (Lambda, DynamoDB basic), 12-month Free (EC2 t2.micro/t3.micro 750 hrs), and Trials (SageMaker Studio free period).
</details>

### Q88
Which is the BEST tool to allocate AWS costs to teams and projects?
- A) Cost and Usage Report
- B) Cost allocation tags
- C) AWS Artifact
- D) Trusted Advisor

<details><summary>Answer</summary>

**B. Cost allocation tags**

Tags are applied to resources, then shown in Cost Explorer/CUR.
</details>

### Q89
Which purchasing option offers up to 90% discount but can be interrupted with 2-minute notice?
- A) On-Demand
- B) Reserved Instances
- C) Savings Plans
- D) Spot Instances

<details><summary>Answer</summary>

**D. Spot Instances**
</details>

### Q90
Which tool provides recommendations for cost optimization, security, fault tolerance, service limits, and performance?
- A) Cost Explorer
- B) Trusted Advisor
- C) AWS Config
- D) CloudTrail

<details><summary>Answer</summary>

**B. Trusted Advisor**
</details>

### Q91
Which tool tracks AWS health events affecting YOUR specific resources?
- A) AWS Service Health Dashboard
- B) AWS Personal Health Dashboard (now part of AWS Health)
- C) CloudWatch
- D) Trusted Advisor

<details><summary>Answer</summary>

**B. AWS Personal Health Dashboard / AWS Health Dashboard**

Service Health = global status; Personal Health = specific to your account.
</details>

### Q92
A customer runs a workload 24/7 for 3 years with no expected changes. Which is MOST cost-effective?
- A) On-Demand
- B) 3-year Standard Reserved Instances (All Upfront)
- C) Spot
- D) Monthly On-Demand

<details><summary>Answer</summary>

**B**

3-year All Upfront = max discount (up to 72%).
</details>

### Q93
Which service provides detailed line-item billing data for finance teams?
- A) Cost Explorer
- B) AWS Budgets
- C) AWS Cost and Usage Report (CUR)
- D) AWS Artifact

<details><summary>Answer</summary>

**C. CUR**

Raw billing data, delivered to S3.
</details>

### Q94
Which two benefits are specific to AWS Business Support? (Choose TWO)
- A) 24/7 phone, chat, email
- B) Dedicated Technical Account Manager
- C) Full Trusted Advisor checks
- D) Infrastructure Event Management (always included)
- E) Free AWS certification exam vouchers

<details><summary>Answer</summary>

**A and C**

TAM = Enterprise only. IEM = Enterprise (or paid add-on for Business).
</details>

### Q95
A nonprofit wants to estimate the cost of moving an on-prem data center to AWS. Which is BEST?
- A) AWS Pricing Calculator
- B) AWS TCO Calculator
- C) AWS Cost Explorer
- D) AWS Budgets

<details><summary>Answer</summary>

**B. AWS TCO Calculator**

TCO = Total Cost of Ownership comparison (on-prem vs AWS). Pricing Calculator estimates AWS-only.
</details>

### Q96
Which of the following are valid support tiers? (Choose FOUR)
- A) Basic
- B) Developer
- C) Business
- D) Enterprise On-Ramp
- E) Enterprise
- F) Premium

<details><summary>Answer</summary>

**A, B, C, D, E — pick any 4**

Five tiers exist: Basic, Developer, Business, Enterprise On-Ramp, Enterprise. There is no "Premium."
</details>

### Q97
Which is the BEST resource to find AWS architecture best practices and reference patterns?
- A) AWS re:Post
- B) AWS Prescriptive Guidance
- C) AWS Whitepapers and Guides
- D) AWS Artifact

<details><summary>Answer</summary>

**C. AWS Whitepapers**

Also Well-Architected Framework docs. Prescriptive Guidance is implementation-level how-tos.
</details>

### Q98
Which is a valid way to contact AWS Support on a Basic support plan?
- A) Open a technical support case
- B) Call a Cloud Support Engineer
- C) Contact Customer Service for billing and account issues
- D) Request architectural review

<details><summary>Answer</summary>

**C**

Basic = billing & account questions only, no technical support.
</details>

### Q99
A customer wants flexible commitment-based pricing that applies across EC2, Lambda, and Fargate. Which option?
- A) Reserved Instances
- B) Compute Savings Plans
- C) EC2 Instance Savings Plans
- D) Spot Instances

<details><summary>Answer</summary>

**B. Compute Savings Plans**

Applies to EC2 (any family/region/OS), Fargate, Lambda. EC2 Instance Savings Plan is locked to family+region.
</details>

### Q100
Which feature helps you see AWS spend broken down by service, tag, or account?
- A) AWS Budgets
- B) Cost Explorer
- C) Pricing Calculator
- D) AWS Artifact

<details><summary>Answer</summary>

**B. Cost Explorer**
</details>

---

## Set 5: AWS CAF Focus (Questions 101–108)

### Q101
A company is planning its cloud adoption and wants to identify capability gaps across the six AWS CAF perspectives before running any pilots. Which CAF phase is this?
- A) Envision
- B) Align
- C) Launch
- D) Scale

<details><summary>Answer</summary>

**B. Align**

- A is wrong: Envision *identifies and prioritizes* transformation opportunities, it doesn't analyze capability gaps
- C is wrong: Launch delivers pilots in production
- D is wrong: Scale expands successful pilots
- Keyword "capability gaps across the perspectives" = **Align**
</details>

### Q102
Which AWS CAF perspective ensures cloud investments align with business outcomes and helps create new revenue streams?
- A) Business
- B) People
- C) Platform
- D) Operations

<details><summary>Answer</summary>

**A. Business**

- B (People) = skills, culture, training
- C (Platform) = build the platform, modernize workloads
- D (Operations) = run and deliver services
- "Business outcomes / revenue" = **Business**
</details>

### Q103
A company needs to ensure its cloud services run reliably with observability, incident management, and change management. Which CAF perspective covers this?
- A) Security
- B) Platform
- C) Operations
- D) Governance

<details><summary>Answer</summary>

**C. Operations**

- A (Security) = confidentiality, integrity, availability of data
- B (Platform) = *building* the platform, not running services day-to-day
- D (Governance) = risk, cost, measuring initiatives
- "Run/deliver services, observability, incident & change management" = **Operations**
</details>

### Q104
An organization is choosing a framework to guide its company-wide journey of adopting the cloud — assessing readiness, skills, and governance. Which framework is the BEST fit?
- A) AWS Well-Architected Framework
- B) AWS Cloud Adoption Framework (CAF)
- C) AWS Cloud Financial Framework
- D) AWS Shared Responsibility Model

<details><summary>Answer</summary>

**B. AWS Cloud Adoption Framework (CAF)**

- A (Well-Architected) guides the design of a *workload/architecture*, not organizational adoption
- C is not a real framework (distractor)
- D defines security duty split, not an adoption plan
- "Organizational adoption / readiness" = **CAF**
</details>

### Q105
Which CAF phase focuses on delivering pilot initiatives in production to demonstrate incremental business value before scaling?
- A) Envision
- B) Align
- C) Launch
- D) Scale

<details><summary>Answer</summary>

**C. Launch**

- Launch = run impactful pilots in production and learn before scaling
- Scale only comes after pilots prove value
</details>

### Q106
A CFO wants to control cloud spend, manage transformation risk, and measure the ROI of cloud initiatives. Which CAF perspective addresses these needs?
- A) Business
- B) Governance
- C) People
- D) Operations

<details><summary>Answer</summary>

**B. Governance**

- Common trap with **Business**: Business = aligning spend to *outcomes/strategy*; Governance = *controlling cost (cloud financial management), risk, and measuring* initiatives
- Governance owns risk management + cloud financial management
</details>

### Q107
Which of the following is NOT one of the four AWS CAF transformation domains?
- A) Technology
- B) Process
- C) Organization
- D) Security

<details><summary>Answer</summary>

**D. Security**

- The four transformation domains are **Technology, Process, Organization, Product**
- Security is a *perspective*, not a domain — a classic mix-up
</details>

### Q108
Which three CAF perspectives are considered the technical capabilities?
- A) Business, People, Governance
- B) Platform, Security, Operations
- C) Business, Platform, Security
- D) People, Governance, Operations

<details><summary>Answer</summary>

**B. Platform, Security, Operations**

- Business, People, Governance = business (non-technical) capabilities
- Platform, Security, Operations = technical capabilities
</details>

---

## Scoring Guide

| Score | Readiness |
|-------|-----------|
| 90-100% | Exam-ready; book with confidence |
| 80-89% | Strong; review weak topics |
| 70-79% | Almost there; do one more practice set |
| 60-69% | Re-study weak domains; retake |
| Below 60% | Revisit notes 01-11 and try again |

---

## Review Method

After each set of 25:
1. Count correct/incorrect by domain
2. For every wrong answer, write:
   - What clue word did I miss?
   - Why is the right answer right?
   - Why is the option I picked wrong?
3. Add the topic to your weak-area list in `03-progress-tracker.md`
