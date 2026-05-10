# AWS Core Services

## What are Core Services? & Why It Matters

Core services are the main AWS building blocks used to run applications: compute, storage, databases, and networking. The exam repeatedly asks you to choose the most suitable service for a scenario, so service selection matters more than memorizing every feature.

---

## Prerequisites & Related Concepts

- `Cloud fundamentals`: You should already know Regions, AZs, elasticity, and managed service thinking.
- `Application architecture`: A web app usually needs compute, storage, a database, and networking controls working together.
- `Stateful vs stateless`: This matters when picking compute and storage services.

---

## Core Concepts

### Compute services

| Service | Best for | Key exam idea |
| --- | --- | --- |
| EC2 | Full VM control | You manage OS and patching |
| Lambda | Event-driven serverless code | No server management, pay per execution |
| ECS | Containers on AWS | Managed container orchestration |
| EKS | Kubernetes on AWS | Use when Kubernetes is required |
| Elastic Beanstalk | Simple app deployment | AWS helps with environment management |
| Lightsail | Simple small workloads | Easy starter VPS-style option |

Choose:

- `EC2` when you need OS-level control.
- `Lambda` for short event-driven functions.
- `ECS/EKS` for containers.
- `Beanstalk` for fast platform-style deployment.

### Storage services

| Service | Type | Best for |
| --- | --- | --- |
| S3 | Object storage | Files, backups, static content |
| EBS | Block storage | Disks attached to EC2 |
| EFS | File storage | Shared Linux file system |
| FSx | Managed file systems | Windows or specialized file needs |
| S3 Glacier | Archive object storage | Low-cost long-term retention |

Important S3 ideas:

- Durable object storage
- Storage classes for different access patterns
- Static website hosting
- Lifecycle policies
- Versioning
- Encryption

### Database services

| Service | Model | Best for |
| --- | --- | --- |
| RDS | Relational | Managed SQL databases |
| Aurora | Relational | High-performance managed relational engine |
| DynamoDB | NoSQL key-value/document | Low-latency large-scale workloads |
| Redshift | Data warehouse | Analytics over large datasets |
| ElastiCache | In-memory cache | Faster reads, lower DB pressure |

Choose:

- `RDS/Aurora` for relational apps with SQL.
- `DynamoDB` for massive scale with flexible key-based access.
- `Redshift` for analytics, not for transactional app storage.

### Networking services

| Service | Purpose | Key exam idea |
| --- | --- | --- |
| VPC | Private network boundary | Core AWS networking container |
| Subnet | Network segment in a VPC | Public or private placement |
| Route 53 | DNS | Routing users to endpoints |
| ELB | Load balancing | Spread traffic across targets |
| CloudFront | CDN | Cache content close to users |
| API Gateway | API front door | Managed API exposure |

Security controls:

- `Security Groups`: Stateful instance-level firewall.
- `Network ACLs`: Stateless subnet-level filter.

ASCII flow:

```text
User -> Route 53 -> CloudFront/ELB -> EC2/Lambda/ECS -> RDS/DynamoDB/S3
```

### Common selection patterns

| Need | Likely answer |
| --- | --- |
| Shared object storage | S3 |
| Attached disk for one EC2 instance | EBS |
| Shared file system for Linux fleet | EFS |
| Run code on file upload event | Lambda + S3 |
| Managed relational DB | RDS or Aurora |
| Massive low-latency NoSQL | DynamoDB |
| Reduce read load on DB | ElastiCache |
| Global content acceleration | CloudFront |

---

## Practical Examples & Reference Snippets

EC2 example:

```bash
aws ec2 describe-instances --max-items 5
```

S3 example:

```bash
aws s3 mb s3://my-demo-bucket-12345
aws s3 cp notes.txt s3://my-demo-bucket-12345/
```

RDS listing example:

```bash
aws rds describe-db-instances
```

These are useful because they connect abstract services to how operators actually inspect resources.

---

## 🏗️ Production Engineering Context (CRITICAL)

### 1. Decision Making: Why Choose This Design?

- `EC2` gives control but increases operational work.
- `Lambda` reduces server management but has execution constraints.
- `S3` is cheap and durable for objects but not a mounted operating system disk.
- `DynamoDB` scales fast but requires access-pattern-driven design.

### 2. Scaling Impact: What Happens If Traffic Increases?

- Web tiers need load balancers and autoscaling.
- Databases can become the bottleneck long before stateless compute.
- Caching and CDNs reduce backend pressure.

### 3. Failure Modes: What Might Break?

- Storing app data only on one EC2 instance disk risks data loss.
- Using RDS where extreme single-digit millisecond key lookups at huge scale are needed can cause scaling pain.
- Misconfigured security groups can block healthy traffic.

### 4. Troubleshooting: How to Fix It?

- Check whether the issue is compute, network, storage, or database.
- Validate security groups, subnets, route tables, and target health.
- Separate latency issues from permission issues.

Useful commands:

```bash
aws ec2 describe-security-groups
aws elbv2 describe-load-balancers
aws dynamodb list-tables
aws cloudfront list-distributions
```

---

## 🔮 Memory Hooks & Practical Scenarios

### Memory Hooks

- **When**: You hear “files for an app”
- **Say**: `Object -> S3, Block -> EBS, Shared file -> EFS`
- **Remember**: Storage questions are often elimination questions

### Real-World Scenario Q&A

Scenario 1:

- Context and environment: A startup needs to host static website files cheaply.
- Symptoms/signals: No need for application server logic.
- Wrong approach and why it fails: Launch EC2 instances for simple static content.
- Right approach with commands: Use S3 static hosting and optionally CloudFront.
- Prevention actions: Match service complexity to workload complexity.

Scenario 2:

- Context and environment: An application needs short event-based image processing.
- Symptoms/signals: Work starts only after uploads.
- Wrong approach and why it fails: Keep EC2 instances running all day.
- Right approach with commands: Use S3 event triggers with Lambda.
- Prevention actions: Choose serverless for bursty event workloads.

Scenario 3:

- Context and environment: A relational app slows during read-heavy traffic.
- Symptoms/signals: DB CPU rises, read queries increase.
- Wrong approach and why it fails: Increase only app server count.
- Right approach with commands: Use read replicas or ElastiCache depending on pattern.
- Prevention actions: Identify the actual bottleneck before scaling.

### Mini Case Study

`Trigger -> Traffic spike during sale -> Impact -> Slow app and high DB load -> Investigation -> Web tier scaled but DB stayed hot -> Mitigation -> Add cache and read scaling -> Root Cause -> Architecture assumed compute was the only bottleneck -> Prevention -> Capacity review by layer`

---

## 🧪 Hands-On Drills

### Drill 1: Quick Lab (10-15 min)

- Objective: Classify 20 AWS services into compute, storage, database, or networking.
- Setup: Use the notes and AWS console names.
- Commands:

```bash
aws ec2 describe-instances --max-items 1
aws s3 ls
aws rds describe-db-instances
```

- Verification: You can explain why each service belongs to its category.

### Drill 2: Production Simulation (20-40 min)

- Failure injection method: Create five fake scenario questions and answer them without notes.
- Expected signals: Confusion between similar services like EBS vs EFS, RDS vs Redshift.
- Recovery playbook: Rewrite answers as “need -> service -> why not other options”.
- Rollback/cleanup steps: Keep a shortlist of confused pairs for next-day revision.

---

## Quick Reference

```bash
aws ec2 describe-instances
aws s3 ls
aws rds describe-db-instances
aws dynamodb list-tables
aws elbv2 describe-load-balancers
aws route53 list-hosted-zones
```

---

## Interview Questions

- **Question**: When would you choose Lambda over EC2?
- **Answer**: For event-driven workloads where server management should be minimized and execution is short-lived.
- **Why this matters**: It shows understanding of operational trade-offs.

- **Question**: What is the difference between EBS and EFS?
- **Answer**: EBS is block storage attached to EC2, while EFS is a managed shared file system for multiple Linux instances.
- **Why this matters**: This is a common exam trap.

- **Question**: Why use CloudFront with S3?
- **Answer**: To cache content at edge locations, lower latency, and reduce origin load.
- **Why this matters**: It links global infrastructure to application delivery.

- **Question**: When should you use DynamoDB instead of RDS?
- **Answer**: When you need NoSQL patterns, very low latency, and scale based on key-value or document access patterns.
- **Why this matters**: Correct database selection is a frequent scenario question.

- **Question**: What does a security group do?
- **Answer**: It acts as a stateful virtual firewall controlling inbound and outbound traffic for resources.
- **Why this matters**: Networking and security are tightly connected in AWS.
