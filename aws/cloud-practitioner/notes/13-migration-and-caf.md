# AWS Migration Strategies & Cloud Adoption Framework

## What is This File? & Why It Matters

Domain 1 Task 1.3 explicitly tests **migration benefits and strategies** and the **Cloud Adoption Framework (CAF)**. This is a small but high-density area — learners who skip it often lose 3-5 easy points.

---

## Part 1: The AWS Cloud Adoption Framework (CAF)

AWS CAF helps organizations plan a cloud transformation. It organizes guidance into **6 perspectives**. Think of perspectives as "lenses" through which different stakeholders view the cloud journey.

### The 6 CAF Perspectives

Mnemonic: **"Big People Get Power, Security, Operations"** → Business, People, Governance, Platform, Security, Operations

| # | Perspective | Who owns it | Focus |
|---|-------------|-------------|-------|
| 1 | **Business** | CFO, CIO, CTO, business managers | Ensure cloud investment aligns with business outcomes |
| 2 | **People** | HR, talent leads | Build cloud skills, organizational change management, training |
| 3 | **Governance** | CIO, program managers, finance | Manage and measure cloud initiatives, risk, compliance |
| 4 | **Platform** | CTO, engineering, architects | Build and operate hybrid cloud platforms; modernize workloads |
| 5 | **Security** | CISO, security teams | Confidentiality, integrity, availability of data and systems |
| 6 | **Operations** | COO, IT operations | Run cloud services at levels the business needs |

### Quick Grouping

- **Business capabilities** (non-technical): Business, People, Governance
- **Technical capabilities**: Platform, Security, Operations

### CAF Transformation Phases

The CAF recommends 4 iterative phases:

1. **Envision** — Identify transformation opportunities tied to business outcomes
2. **Align** — Identify capability gaps and stakeholder concerns across the 6 perspectives
3. **Launch** — Deliver pilot initiatives in production, demonstrate value
4. **Scale** — Expand pilots and business value to the desired scale

---

## Part 2: The 7 Rs of Migration

When you migrate a workload to AWS, you pick one of 7 strategies. AWS used to call this "6 Rs" (based on Gartner's 5 Rs). Today it is **7 Rs**. CLF-C02 may still refer to "6 Rs" or "7 Rs" — know both.

### The 7 Strategies

| # | Strategy | Also Known As | What It Means | When to Use |
|---|----------|---------------|---------------|-------------|
| 1 | **Rehost** | Lift-and-shift | Move as-is without changes | Fast migration, minimal app changes |
| 2 | **Replatform** | Lift-tinker-and-shift | Minor optimizations (e.g., self-managed DB → RDS) | Small wins without rewrite |
| 3 | **Relocate** | Hypervisor-level lift | Move infrastructure without rewriting apps (e.g., VMware Cloud on AWS) | Large VMware estates |
| 4 | **Repurchase** | Drop-and-shop | Replace with a different product (e.g., CRM → Salesforce) | Legacy software with SaaS alternatives |
| 5 | **Refactor** | Re-architect | Rewrite application for cloud-native benefits (microservices, serverless) | Need scalability, agility, or new features |
| 6 | **Retire** | Decommission | Turn off applications no longer needed | Unused or redundant apps |
| 7 | **Retain** | Revisit / Do nothing | Keep in source environment for now | Compliance, cost, or timing blockers |

### Mnemonic: **"Run Really Really Really Really Ready Retail"**
Rehost, Replatform, Relocate, Repurchase, Refactor, Retire, Retain

### Effort vs Benefit

```text
Low effort  ----------------------->  High effort
Rehost -> Relocate -> Replatform -> Repurchase -> Refactor
```

- **Rehost** = fastest migration, lowest cloud-native benefit
- **Refactor** = slowest migration, highest cloud-native benefit
- **Retire/Retain** = not really migrations

### Exam-Style Scenarios

| Scenario | Right answer |
|----------|--------------|
| Move on-prem Oracle DB to RDS with minimal changes | Replatform |
| Rewrite monolith as Lambda + DynamoDB microservices | Refactor |
| Lift VMware VMs to VMware Cloud on AWS | Relocate |
| Replace on-prem CRM with Salesforce | Repurchase |
| Move EC2-sized workload as-is via AWS Application Migration Service | Rehost |
| Decommission an unused HR portal | Retire |
| Keep a mainframe on-prem for 2 years due to compliance | Retain |

---

## Part 3: Migration Tools

| Tool | Purpose |
|------|---------|
| **AWS Migration Hub** | Central place to discover, plan, and track migrations across multiple tools |
| **AWS Application Migration Service (MGN)** | Automated lift-and-shift for servers (replaces CloudEndure) |
| **AWS Database Migration Service (DMS)** | Migrate databases with minimal downtime |
| **AWS Schema Conversion Tool (SCT)** | Convert database schema (e.g., Oracle → PostgreSQL) for heterogeneous migrations |
| **AWS DataSync** | Online data transfer between on-prem storage and AWS |
| **AWS Transfer Family** | SFTP/FTPS/FTP file transfer to S3/EFS |
| **AWS Snow Family** | Physical device-based offline data transfer (see file `14-service-deep-dives.md`) |
| **AWS Application Discovery Service** | Collect data about on-prem apps to plan migrations |

### Migration Tool Selection

| Need | Tool |
|------|------|
| Plan and track migration across services | Migration Hub |
| Move servers as-is to AWS | Application Migration Service |
| Move databases live | DMS |
| Change DB engine during migration | SCT + DMS |
| Move large files offline (TBs to PBs) | Snow Family |
| Move large files online | DataSync |
| Collect inventory of on-prem infrastructure | Application Discovery Service |

---

## Part 4: Benefits of Cloud Migration

Common exam angles:

1. **Agility** — Provision resources in minutes
2. **Elasticity** — Scale up/down with demand
3. **Cost savings** — Move from CapEx to OpEx; pay only for what you use
4. **Global reach** — Deploy close to users
5. **Operational efficiency** — Focus on apps, not infrastructure
6. **Increased reliability** — Multi-AZ, Multi-Region options
7. **Faster time to market** — Experiment and release faster
8. **Innovation** — Use managed AI/ML, analytics, IoT services

---

## Quick Reference

```text
CAF perspectives:     Business, People, Governance, Platform, Security, Operations
CAF phases:           Envision -> Align -> Launch -> Scale
7 Rs:                 Rehost, Replatform, Relocate, Repurchase, Refactor, Retire, Retain
Lift & shift:         Rehost
Hypervisor lift:      Relocate
Rewrite for cloud:    Refactor
Buy a SaaS product:   Repurchase
```

---

## Interview Questions

- **Q:** How many perspectives are in the AWS CAF?
  **A:** Six — Business, People, Governance, Platform, Security, Operations.

- **Q:** Which migration strategy means rewriting an application for cloud-native benefits?
  **A:** Refactor (Re-architect).

- **Q:** What is the difference between Rehost and Relocate?
  **A:** Rehost moves individual servers as-is. Relocate moves infrastructure at the hypervisor level (e.g., VMware) without changing the VMs.

- **Q:** Which tool is used to track a complex multi-service migration?
  **A:** AWS Migration Hub.

- **Q:** Which migration strategy keeps the app on-prem temporarily?
  **A:** Retain.
