# AWS Service Deep Dives

## What is This File? & Why It Matters

This file covers high-frequency exam topics in more detail than the basic notes. Cloud Practitioner questions often hinge on small details like S3 storage classes, EC2 instance families, or VPC endpoint types. Know these cold.

---

## Part 1: Amazon S3 Deep Dive

### Durability and Availability

| Metric | Value |
|--------|-------|
| Durability | **99.999999999% (11 nines)** — designed to lose 1 object per 10,000 years per 10M objects |
| Availability (Standard) | 99.99% |
| Availability (One Zone-IA) | 99.5% |
| Max object size | 5 TB |
| Max single-PUT upload | 5 GB (use multipart upload for >100 MB) |

### S3 Storage Classes

| Class | Use Case | Retrieval | Min Duration | Availability |
|-------|----------|-----------|--------------|--------------|
| **S3 Standard** | Frequently accessed data | Millisecond | None | 99.99% |
| **S3 Intelligent-Tiering** | Unknown or changing access patterns | Millisecond | None | 99.9% |
| **S3 Standard-IA** | Infrequent access, rapid when needed | Millisecond | 30 days | 99.9% |
| **S3 One Zone-IA** | Infrequent, non-critical, reproducible | Millisecond | 30 days | 99.5% |
| **S3 Glacier Instant Retrieval** | Archive, need millisecond access | Millisecond | 90 days | 99.9% |
| **S3 Glacier Flexible Retrieval** | Archive, minutes-to-hours retrieval | 1 min–12 hrs | 90 days | 99.99% |
| **S3 Glacier Deep Archive** | Long-term archive (7-10+ years) | 12 hrs | 180 days | 99.99% |

### S3 Encryption Options

| Type | Who manages the key? | Use case |
|------|---------------------|----------|
| **SSE-S3** | AWS (AES-256) | Default, easiest |
| **SSE-KMS** | AWS KMS (customer-controlled) | Audit trail needed, key rotation |
| **SSE-C** | Customer provides key per request | You manage keys outside AWS |
| **Client-side encryption** | Customer encrypts before upload | Max control |

**Note:** As of Jan 2023, all new S3 objects are encrypted by default with SSE-S3.

### S3 Features

- **Versioning** — Keep multiple versions of an object; protect against accidental delete
- **Lifecycle policies** — Automatically transition objects between classes or delete them
- **Replication** — Cross-Region Replication (CRR) and Same-Region Replication (SRR)
- **MFA Delete** — Require MFA for permanent delete
- **Object Lock** — WORM (Write Once Read Many) for compliance
- **Static website hosting** — Host HTML/CSS/JS from a bucket
- **Presigned URLs** — Time-limited access to private objects
- **Transfer Acceleration** — Use CloudFront edge locations to speed uploads

### S3 Exam Traps

| Wording | Answer |
|---------|--------|
| "Lowest cost long-term archive, 12h retrieval OK" | Glacier Deep Archive |
| "Unknown access pattern, optimize cost automatically" | Intelligent-Tiering |
| "Frequently accessed, need highest availability" | S3 Standard |
| "Infrequent access, but reproducible if lost" | One Zone-IA |
| "Archive but need millisecond access" | Glacier Instant Retrieval |

---

## Part 2: EC2 Instance Types

### Pricing Options (In Detail)

| Option | Commitment | Discount | Use Case |
|--------|-----------|----------|----------|
| **On-Demand** | None | 0% | Short-term, unpredictable |
| **Reserved Instances (Standard 1yr)** | 1 year, specific instance | Up to 40% | Steady workloads |
| **Reserved Instances (Standard 3yr)** | 3 years, specific instance | Up to 60% | Very steady workloads |
| **Reserved Instances (Convertible)** | 1 or 3 years, flexible | Up to 54% | Steady but may change instance types |
| **Savings Plans (Compute)** | 1 or 3 years, $/hour commitment | Up to 66% | Flexible across EC2, Lambda, Fargate |
| **Savings Plans (EC2 Instance)** | 1 or 3 years, specific family/region | Up to 72% | Known family in known region |
| **Spot Instances** | None (can be interrupted) | Up to 90% | Interruptible, batch, big data |
| **Dedicated Hosts** | On-demand or reserved | Varies | Compliance, BYOL licenses |
| **Dedicated Instances** | On-demand or reserved | Varies | Isolated hardware, no host control |
| **Capacity Reservations** | None (just reservation) | None | Guaranteed capacity in an AZ |

### EC2 Instance Families

Remember by **first letter**:

| Letter | Family | Use Case |
|--------|--------|----------|
| **T** | Burstable general purpose | Low-cost dev, small web apps |
| **M** | General purpose (balanced) | Most workloads, balanced CPU/memory |
| **C** | Compute optimized | HPC, batch processing, gaming servers |
| **R** | Memory optimized | In-memory databases, caches |
| **X** | Extreme memory | SAP HANA, large in-memory DBs |
| **I** | Storage optimized (high IOPS) | NoSQL DBs, data warehousing |
| **D** | Dense storage (HDD) | Hadoop, distributed file systems |
| **G / P** | GPU optimized | ML training/inference, graphics |
| **Inf / Trn** | AI/ML accelerators | Deep learning inference/training |

**Mnemonic:** "**M**ost apps, **C**PU-heavy, **R**AM-heavy, e**X**treme RAM, **I**O-heavy"

### EC2 Dedicated Hosts vs Dedicated Instances

| Feature | Dedicated Host | Dedicated Instance |
|---------|---------------|-------------------|
| Isolation | Full host | Just isolated at hardware level |
| Visibility into sockets/cores | Yes | No |
| BYOL (licenses tied to host) | Yes | No |
| Cost | Higher | Lower |

---

## Part 3: EBS Volume Types

| Type | Performance | Use Case |
|------|------------|----------|
| **gp3** | General purpose SSD, configurable IOPS | Default choice, boot volumes, most workloads |
| **gp2** | General purpose SSD, IOPS tied to size | Older default (prefer gp3) |
| **io2 / io2 Block Express** | Max IOPS SSD, high durability | Mission-critical DBs (Oracle, SAP) |
| **io1** | Provisioned IOPS SSD (older) | Legacy IOPS-intensive |
| **st1** | Throughput-optimized HDD | Big data, log processing, streaming |
| **sc1** | Cold HDD | Infrequent access, cheapest block storage |

**Key facts:**
- EBS is AZ-specific. To move between AZs → take snapshot → restore in new AZ
- EBS snapshots are stored in S3 (internally, incremental)
- Root volumes are deleted on instance termination **by default** (can be changed)

---

## Part 4: VPC Networking Details

### VPC Components

- **VPC** — virtual network boundary (default CIDR: /16 to /28)
- **Subnets** — segments in an AZ (public or private)
- **Internet Gateway (IGW)** — internet access for public subnets
- **NAT Gateway** — outbound internet for private subnets
- **Route Tables** — define where network traffic is directed
- **Security Groups** — stateful, instance-level firewall (allow rules only)
- **Network ACLs (NACLs)** — stateless, subnet-level (allow + deny rules)

### Security Groups vs NACLs

| Feature | Security Group | NACL |
|---------|---------------|------|
| Level | Instance/ENI | Subnet |
| Stateful? | Yes (return traffic auto-allowed) | No (must allow both directions) |
| Rules | Allow only | Allow and Deny |
| Evaluation | All rules evaluated | Rules in order (lowest number first) |

### VPC Endpoints (Critical Exam Topic)

Use VPC endpoints to access AWS services **privately** without going over the internet.

| Type | Supports | How |
|------|----------|-----|
| **Gateway Endpoint** | S3 and DynamoDB only | Route table entry (free) |
| **Interface Endpoint (PrivateLink)** | Most AWS services, Marketplace, your own services | ENI with private IP in your subnet (paid per hour + data) |

**Why it matters:** Keeps traffic off the public internet → lower cost, better security, no NAT Gateway needed for S3/DynamoDB access from private subnets.

### VPC Connectivity Options

| Option | Purpose |
|--------|---------|
| **VPC Peering** | 1:1 connection between two VPCs (no transitive routing) |
| **Transit Gateway** | Hub-and-spoke for connecting many VPCs + on-prem |
| **Direct Connect** | Dedicated private line from on-prem to AWS (not over internet) |
| **Site-to-Site VPN** | Encrypted tunnel over internet from on-prem to AWS |
| **Client VPN** | Individual user VPN to AWS |
| **Direct Connect Gateway** | Connect DX to multiple VPCs across Regions |

### Transit Gateway vs VPC Peering

| Need | Answer |
|------|--------|
| Connect 2 VPCs | VPC Peering (simpler, cheaper) |
| Connect 10+ VPCs + on-prem | Transit Gateway (scales) |
| Transitive routing (A → B → C) | Transit Gateway |

### AWS Global Accelerator vs CloudFront

| Feature | Global Accelerator | CloudFront |
|---------|-------------------|------------|
| Type | Network-layer (Layer 4) | Content-layer (Layer 7 / HTTP) |
| Use case | Non-HTTP apps, gaming, VoIP, IoT | Static/dynamic websites, video, APIs |
| Static IPs | Yes (2 anycast IPs) | No |
| Caches content | No | Yes (at edge) |
| Protocol | TCP, UDP | HTTP, HTTPS |

---

## Part 5: AWS Snow Family (Current State — Nov 2025)

> **Important:** As of November 7, 2025, AWS Snowball Edge is only available to **existing customers**. New customer orders have ended. Snowcone was discontinued in November 2024. Snowmobile was retired in March 2024. For new workloads, AWS recommends **DataSync** or **Direct Connect**.

The exam still tests Snow Family knowledge, so learn it:

### Snow Family Devices (Historical + Current)

| Device | Status | Capacity | Use Case |
|--------|--------|----------|----------|
| **Snowcone** | Discontinued Nov 2024 | 8 TB HDD / 14 TB SSD | Small edge computing, 4.5 lbs, portable |
| **Snowball Edge Storage Optimized** | Existing customers only | ~80 TB usable | Large data transfer (PB-scale) |
| **Snowball Edge Compute Optimized** | Existing customers only | ~42 TB + 52 vCPUs | Edge compute + data transfer |
| **Snowmobile** | RETIRED Mar 2024 | 100 PB per truck | Exabyte-scale transfer (replaced by DataSync / DX) |

### Snow Family Exam Questions

| Scenario | Answer |
|----------|--------|
| "Transfer 50 TB from data center, no reliable internet" | Snowball Edge |
| "Small portable device for edge compute" | Historically Snowcone; now treat it as course context and prioritize the Snow Family concept |
| "100 PB one-time migration" | Historically Snowmobile; now treat it as course context and prioritize current transfer options |
| "Ship a hard drive to AWS" | Snowball Edge |

### Modern Alternatives (post-Snow retirement)

| Need | Modern answer |
|------|---------------|
| Large online transfer | **AWS DataSync** |
| Dedicated private line | **AWS Direct Connect** |
| Move S3 across regions | **S3 Cross-Region Replication** |

---

## Part 6: Monitoring & Management Services

### CloudWatch Components

- **Metrics** — numeric data over time (CPU, memory, requests)
- **Logs** — ingest and search application/system logs
- **Alarms** — trigger actions when thresholds breached
- **Events / EventBridge** — respond to state changes
- **Dashboards** — visualize metrics
- **Agent** — collect system-level metrics (memory, disk) from EC2/on-prem

### CloudTrail Details

- Records all **API calls** in an AWS account
- Two event types:
  - **Management events** — account/resource operations (always logged, first copy free)
  - **Data events** — resource operations (S3 GetObject, Lambda Invoke — not logged by default, extra cost)
- Logs stored in S3
- Retention: 90 days event history free; longer retention needs S3 + trails

### CloudTrail vs CloudWatch vs Config

| Service | Question |
|---------|----------|
| **CloudTrail** | "Who did what, when?" (API audit) |
| **CloudWatch** | "Is it healthy? How's it performing?" (metrics, logs, alarms) |
| **AWS Config** | "What is the configuration state, and did it change?" (compliance, change history) |

---

## Part 7: AWS Organizations & Control Tower

### AWS Organizations

- **Manage multiple AWS accounts** from one management account
- **Consolidated billing** — one bill for all accounts, volume discounts shared
- **Service Control Policies (SCPs)** — max-permission guardrails at OU or account level
  - SCPs do NOT grant permissions — they define what IAM permissions **can** be granted
  - Affect all users including root in member accounts
- **Organizational Units (OUs)** — group accounts (e.g., prod, dev, security)

### AWS Control Tower

- **Set up and govern** a secure multi-account AWS environment
- Built on Organizations, SSO (IAM Identity Center), Config, CloudTrail
- Uses **Landing Zones** and **Guardrails** (preventive and detective)
- Pre-built blueprints for multi-account best practices

### Exam Comparison

| Need | Answer |
|------|--------|
| Central control + max-permission boundaries | Organizations + SCPs |
| Opinionated multi-account setup with best practices | Control Tower |
| Single sign-on across accounts | IAM Identity Center |
| One bill across accounts | Organizations consolidated billing |

---

## Quick Reference

```text
S3 durability              -> 11 nines
Glacier Deep Archive       -> Lowest cost, 12h retrieval
S3 default encryption      -> SSE-S3 (since 2023)
EBS volume types           -> gp3, io2, st1, sc1
VPC endpoint for S3        -> Gateway (free)
VPC endpoint for others    -> Interface (PrivateLink)
Many VPCs                  -> Transit Gateway
Non-HTTP global routing    -> Global Accelerator
Web content acceleration   -> CloudFront
Multi-account guardrails   -> Organizations + SCPs
Opinionated landing zone   -> Control Tower
```
