# AWS Cloud Fundamentals

## What is Cloud Fundamentals? & Why It Matters

Cloud fundamentals explain what cloud computing is, why AWS exists, and how AWS delivers infrastructure as on-demand services. This is the base layer for every other exam topic because service choices, cost models, and security decisions all depend on these ideas.

---

## Prerequisites & Related Concepts

- `Virtualization`: One physical server can run many isolated workloads. This is one reason cloud providers can sell compute efficiently.
- `Networking`: Applications need private and public connectivity. AWS services are only useful when you understand where traffic flows.
- `High availability`: Keeping a service running during failures matters because AWS infrastructure design is built around resiliency.

---

## Core Concepts

### What cloud computing means

Cloud computing is on-demand delivery of IT resources over the internet with pay-as-you-go pricing.

Key properties:

- On-demand self-service
- Broad network access
- Resource pooling
- Rapid elasticity
- Measured service

### Deployment models

| Model | Meaning | When it fits |
| --- | --- | --- |
| Public cloud | Infrastructure owned by provider | Fastest path, low upfront cost |
| Private cloud | Dedicated environment for one organization | Strict control or regulatory needs |
| Hybrid cloud | Mix of on-prem and cloud | Gradual migration, data locality needs |

### Benefits of AWS

- `Elasticity`: Capacity grows or shrinks with demand.
- `Agility`: Teams provision resources quickly.
- `Global reach`: Workloads can run close to users.
- `Operational shift`: AWS manages large parts of the infrastructure stack.
- `Consumption pricing`: You pay for usage instead of buying hardware first.

### CapEx vs OpEx

- `CapEx`: Large upfront purchase, such as buying servers.
- `OpEx`: Ongoing operational spend, such as monthly cloud bills.

The exam often frames AWS value around moving from CapEx to OpEx.

### AWS Global Infrastructure

| Term | Meaning | Why it matters |
| --- | --- | --- |
| Region | Separate geographic area | Choose for latency, compliance, DR |
| Availability Zone | One or more isolated data centers inside a Region | Build high availability by spreading workloads |
| Edge Location | Global sites for content delivery and DNS | Speed up delivery with CloudFront and Route 53 |

ASCII view:

```text
Region
|- AZ-a
|- AZ-b
`- AZ-c

Users -> Edge Location -> Region resources
```

### High availability, fault tolerance, disaster recovery

- `High availability`: Reduce downtime by using redundant components.
- `Fault tolerance`: Continue operating even when one component fails.
- `Disaster recovery`: Recover after major outages or region-level events.

### AWS Well-Architected Framework

The six pillars:

1. Operational Excellence
2. Security
3. Reliability
4. Performance Efficiency
5. Cost Optimization
6. Sustainability

You do not need deep architecture detail for this exam, but you must know why these pillars influence design.

### Shared Responsibility Model

AWS is responsible for `security of the cloud`. Customers are responsible for `security in the cloud`.

Examples:

- AWS manages physical buildings, hardware, and core managed service infrastructure.
- Customer manages IAM permissions, application data, guest OS patching on EC2, and security group rules.

---

## Practical Examples & Reference Snippets

Example mental model:

```text
Traditional data center:
Buy server -> rack it -> power it -> patch it -> scale slowly

AWS:
Request service -> configure it -> monitor it -> pay for use
```

A basic CLI example makes cloud feel concrete:

```bash
aws ec2 describe-regions
aws s3 ls
```

These commands show that AWS resources are API-driven, which is a core cloud operating model.

---

## 🏗️ Production Engineering Context (CRITICAL)

### 1. Decision Making: Why Choose This Design?

- Use multiple AZs when uptime matters.
- Choose the nearest Region that also satisfies compliance and service availability needs.
- Prefer managed services when the team wants less operational overhead.

### 2. Scaling Impact: What Happens If Traffic Increases?

- Fixed hardware becomes a bottleneck faster than autoscaled cloud resources.
- Global users need content caching and regional placement to reduce latency.

### 3. Failure Modes: What Might Break?

- Single-AZ design causes avoidable outages.
- Choosing the wrong Region can increase latency or violate compliance rules.
- Misunderstanding shared responsibility leads to exposed data or weak IAM controls.

### 4. Troubleshooting: How to Fix It?

- Verify Region and AZ architecture first.
- Check whether the outage is app-level, instance-level, or service-level.
- Review IAM permissions, route design, and deployment placement.

Concrete checks:

```bash
aws ec2 describe-availability-zones
aws sts get-caller-identity
```

---

## 🔮 Memory Hooks & Practical Scenarios

### Memory Hooks

- **When**: You hear “global design” or “resilience”
- **Say**: `Multi-AZ first, Multi-Region only when needed`
- **Remember**: Region is the geography, AZ is the isolation unit

### Real-World Scenario Q&A

Scenario 1:

- Context and environment: A web app runs in one AZ.
- Symptoms/signals: One AZ failure causes total downtime.
- Wrong approach and why it fails: Reboot the same instance and hope the AZ recovers.
- Right approach with commands: Redesign across multiple AZs behind a load balancer.
- Prevention actions: Use Multi-AZ architecture for production workloads.

Scenario 2:

- Context and environment: A company stores customer data in the wrong Region.
- Symptoms/signals: Compliance team raises data residency concerns.
- Wrong approach and why it fails: Keep using the same Region because migration is inconvenient.
- Right approach with commands: Select a compliant Region and plan data migration.
- Prevention actions: Treat Region selection as an early architecture decision.

### Mini Case Study

`Trigger -> Single-AZ database outage -> Impact -> Application downtime -> Investigation -> DB only existed in one AZ -> Mitigation -> Fail over to a redundant design -> Root Cause -> Availability not designed in -> Prevention -> Multi-AZ plus tested backup recovery`

---

## 🧪 Hands-On Drills

### Drill 1: Quick Lab (10-15 min)

- Objective: Recognize AWS geography and account context.
- Setup: AWS CLI configured.
- Commands:

```bash
aws configure list
aws sts get-caller-identity
aws ec2 describe-regions --output table
```

- Verification: You can explain Region, AZ, and account identity without looking it up.

### Drill 2: Production Simulation (20-40 min)

- Failure injection method: Pretend an AZ fails for your imaginary app.
- Expected signals: Lost instances, unavailable database, higher latency.
- Recovery playbook: Move design to at least two AZs, add ELB, validate backups.
- Rollback/cleanup steps: Document the improved architecture and remove wrong assumptions.

---

## Quick Reference

```bash
aws sts get-caller-identity
aws ec2 describe-regions
aws ec2 describe-availability-zones
aws s3 ls
```

---

## Interview Questions

- **Question**: What is the difference between a Region and an Availability Zone?
- **Answer**: A Region is a geographic area; an Availability Zone is an isolated location inside a Region.
- **Why this matters**: It drives resiliency and compliance decisions.

- **Question**: What does elasticity mean in AWS?
- **Answer**: Resources can scale up or down based on demand.
- **Why this matters**: It is a core cloud value proposition.

- **Question**: What is AWS responsible for in the Shared Responsibility Model?
- **Answer**: Security of the cloud, including physical facilities and underlying infrastructure.
- **Why this matters**: Many exam questions hinge on this boundary.

- **Question**: Why would a company choose multiple AZs?
- **Answer**: To improve availability and reduce the blast radius of data center-level failures.
- **Why this matters**: It is a standard production design pattern.

- **Question**: When is Multi-Region needed?
- **Answer**: When business continuity, regulatory, or global latency requirements exceed what one Region can provide.
- **Why this matters**: Multi-Region adds cost and complexity, so it should be intentional.
