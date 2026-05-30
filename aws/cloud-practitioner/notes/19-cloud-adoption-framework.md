# AWS Cloud Adoption Framework (AWS CAF)

## What is AWS CAF? & Why It Matters

The **AWS Cloud Adoption Framework (CAF)** is AWS's official guidance for planning and executing a cloud transformation. It does not tell you *how to build* a system (that is the Well-Architected Framework). Instead it tells an *organization* what capabilities to develop, who owns them, and in what order to move — so cloud adoption succeeds as a business change, not just a tech project.

**Why it matters for CLF-C02:** Domain 1 (Cloud Concepts) explicitly tests CAF. Questions usually ask one of three things: (1) *which of the 6 perspectives* owns a given concern, (2) the *business vs technical* grouping, or (3) *what a transformation phase does*. These are easy, high-confidence points if you learn the structure — and easy to lose if you confuse CAF with Well-Architected.

---

## Prerequisites & Related Concepts

You need almost no prerequisites — CAF is a planning framework. But two related ideas prevent the most common exam mistake:

- **AWS Well-Architected Framework (WAF):** 6 *pillars* for designing a good **workload/architecture** (Operational Excellence, Security, Reliability, Performance Efficiency, Cost Optimization, Sustainability). It is **technical/architecture** guidance.
- **AWS CAF:** 6 *perspectives* for transforming an **organization** to adopt cloud. It is **business + technical readiness** guidance.

> **The trap:** Both have "6 of something" and both include "Security." If a question is about *designing a system*, it's Well-Architected. If it's about *an organization adopting the cloud / closing capability gaps / who owns what*, it's CAF.

---

## Core Concepts

### Mental Model

Think of CAF as a checklist for a company-wide move to the cloud, answered through **6 lenses (perspectives)**, applied across **4 areas of change (domains)**, executed in **4 repeating stages (phases)**.

```text
                       AWS CAF
   ┌─────────────────────────────────────────────┐
   │  6 PERSPECTIVES  (the lenses / who owns what) │
   │   Business · People · Governance              │  <- business capabilities
   │   Platform · Security · Operations            │  <- technical capabilities
   ├─────────────────────────────────────────────┤
   │  4 TRANSFORMATION DOMAINS (what changes)      │
   │   Technology · Process · Organization · Product│
   ├─────────────────────────────────────────────┤
   │  4 PHASES (how you move, iteratively)         │
   │   Envision → Align → Launch → Scale           │
   └─────────────────────────────────────────────┘
```

CAF 3.0 defines **47 foundational capabilities** spread across the 6 perspectives. You do **not** need to memorize all 47 for CLF-C02 — know the perspectives, their focus, the grouping, and the phases.

---

### The 6 Perspectives (most-tested)

Each perspective is a set of **capabilities** owned by **functionally related stakeholders**.

| # | Perspective | Group | Focus (what it ensures) | Typical owners |
|---|-------------|-------|-------------------------|----------------|
| 1 | **Business** | Business | Cloud investments accelerate digital transformation and **business outcomes** | CEO, CFO, COO, CIO, CTO |
| 2 | **People** | Business | Culture, org structure, leadership, **workforce skills**; bridge between tech and business | CIO, COO, CTO, cloud director |
| 3 | **Governance** | Business | **Orchestrate initiatives, maximize benefits, minimize risk**; manage and measure | Chief transformation officer, CIO, CTO, CFO, CDO, CRO |
| 4 | **Platform** | Technical | Build a scalable **hybrid cloud platform**, modernize workloads, build cloud-native | CTO, technology leaders, architects, engineers |
| 5 | **Security** | Technical | **Confidentiality, integrity, availability** of data and workloads | CISO, CCO, internal audit, security architects/engineers |
| 6 | **Operations** | Technical | **Run/deliver cloud services** at the level the business needs | Infra & ops leaders, SREs, IT service managers |

**Grouping (very common question):**
- **Business capabilities (non-technical):** Business, People, Governance
- **Technical capabilities:** Platform, Security, Operations

**Mnemonic for the 6 (in order):** **"B**ig **P**eople **G**et **P**latform **S**ecurity **O**perations" → Business, People, Governance, Platform, Security, Operations.

#### Representative capabilities per perspective (for recognition, not memorization)

These total 47 in CAF 3.0. You only need to *recognize* that a capability belongs to a perspective.

| Perspective | Example capabilities |
|-------------|----------------------|
| **Business** | Strategy management, portfolio management, innovation management, product management, data monetization, business insights |
| **People** | Culture evolution, transformational leadership, cloud fluency, workforce transformation, change acceleration, org design |
| **Governance** | Program/project management, benefits management, risk management, **cloud financial management (FinOps)**, application portfolio management, data governance |
| **Platform** | Platform architecture, data architecture, platform engineering, provisioning & orchestration, modern app development, **CI/CD** |
| **Security** | Security governance, **identity & access management**, threat detection, vulnerability management, infrastructure protection, data protection, incident response |
| **Operations** | **Observability**, event management (AIOps), incident & problem management, change & release management, performance & capacity management, patch management |

---

### The 4 Transformation Domains (what changes)

CAF organizes transformation opportunities into four domains:

| Domain | Focus | Example |
|--------|-------|---------|
| **Technology** | Migrate and modernize legacy infrastructure, apps, data/analytics platforms | Move on-prem servers to AWS; modernize a monolith |
| **Process** | Digitize, automate, optimize business operations | Use ML for fraud detection; automate manual workflows |
| **Organization** | Reimagine the operating model; how teams orchestrate to create customer value | Move to product-oriented, cross-functional teams |
| **Product** | Reimagine business model; new revenue streams and customer experiences | Launch a new digital product or subscription |

> The Envision phase prioritizes opportunities **across these four domains**.

---

### The 4 Transformation Phases (how you move)

CAF recommends **four iterative and incremental** phases. They are a cycle, not a one-time waterfall.

```text
Envision  →  Align  →  Launch  →  Scale
   ▲                                  │
   └──────────── iterate ◄────────────┘
```

| Phase | What happens | One-line memory hook |
|-------|--------------|----------------------|
| **1. Envision** | Identify & **prioritize transformation opportunities** across the 4 domains, tied to strategic business objectives and measurable outcomes | "Picture the goal" |
| **2. Align** | Identify **capability gaps across the 6 perspectives**, cross-org dependencies, and stakeholder concerns; build improvement strategies (the CAF action plan) | "Find the gaps" |
| **3. Launch** | Deliver **pilots in production**, demonstrate incremental business value, learn before scaling | "Prove it small" |
| **4. Scale** | **Expand pilots** to full scale; ensure expected business benefits are realized and sustained | "Grow what works" |

**Mnemonic:** **E**very **A**doption **L**eads to **S**uccess → Envision, Align, Launch, Scale.

---

## CAF vs Well-Architected (the #1 confusion — memorize this table)

| Question is about... | Framework | Unit | The "6" are called... |
|----------------------|-----------|------|------------------------|
| An **organization** adopting cloud, capability gaps, who owns what | **CAF** | The whole organization | **Perspectives** |
| **Designing/building** a reliable, secure, cost-effective workload | **Well-Architected** | A single workload/architecture | **Pillars** |

If you see *strategy, people, skills, governance, transformation, readiness, stakeholders* → **CAF**.
If you see *reliability, performance, cost optimization, design, architecture, workload* → **Well-Architected**.

---

## How CAF Shows Up on the Exam (decision practice)

The most common question type is **"which perspective owns this?"** Train the mapping:

| Concern in the question | Perspective |
|-------------------------|-------------|
| Staff lack cloud skills; need training and change management | **People** |
| Need to measure ROI, manage risk, control cloud spend (FinOps) | **Governance** |
| Align cloud spend to revenue/business outcomes; new revenue streams | **Business** |
| Build the landing zone / hybrid platform, CI/CD, modernization | **Platform** |
| Data confidentiality, IAM, threat detection, compliance of workloads | **Security** |
| Keep services running, observability, incident/change management, SLAs | **Operations** |

> Tip: **People = skills/culture**, **Governance = risk/money/measurement**, **Business = outcomes/strategy**. These three "business" perspectives are the ones learners most often mix up.

---

## 🔮 Memory Hooks

- **6 perspectives order:** **B**ig **P**eople **G**et **P**latform **S**ecurity **O**perations.
- **Business group = "the suits"** (Business, People, Governance). **Technical group = "the builders"** (Platform, Security, Operations).
- **4 phases:** **E-A-L-S** — Envision, Align, Launch, Scale ("Picture → Gaps → Pilot → Grow").
- **4 domains:** **Tech, Process, Org, Product** (TPOP).
- **CAF = company; Well-Architected = workload.**
- **"Capability gaps across perspectives" is ALWAYS the Align phase.**
- **"Pilot in production" is ALWAYS the Launch phase.**

---

## 🧪 Self-Test Drills (active recall)

Cover the answers and respond out loud, then check.

**Drill 1 — Name them cold (2 min)**
1. List the 6 perspectives in order. → Business, People, Governance, Platform, Security, Operations
2. Which 3 are business capabilities? → Business, People, Governance
3. List the 4 phases in order. → Envision, Align, Launch, Scale
4. List the 4 domains. → Technology, Process, Organization, Product

**Drill 2 — Map the scenario (5 min)**
- "Employees need cloud training" → **People**
- "We need to track whether the migration delivered ROI" → **Governance**
- "Build a secure landing zone and CI/CD pipeline" → **Platform**
- "Detect threats and protect customer data" → **Security**
- "Identify capability gaps before we start" → **Align phase**
- "Run a small pilot to prove value" → **Launch phase**

---

## Quick Reference

```text
AWS CAF = plan/accelerate ORGANIZATIONAL cloud adoption (not workload design).

6 PERSPECTIVES (own capabilities):
  Business  ─┐
  People     ├─ Business capabilities (non-technical)
  Governance ┘
  Platform  ─┐
  Security   ├─ Technical capabilities
  Operations ┘

4 DOMAINS  : Technology, Process, Organization, Product
4 PHASES   : Envision → Align → Launch → Scale  (iterative)
CAF 3.0    : 47 foundational capabilities

vs Well-Architected: CAF = perspectives (org) | WAF = pillars (workload)
```

---

## Exam Questions

- **Q:** How many perspectives are in AWS CAF, and what are they?
  **A:** Six — Business, People, Governance, Platform, Security, Operations.
  **Why it matters:** The single most common CAF fact tested.

- **Q:** Which perspectives are the "business" (non-technical) capabilities?
  **A:** Business, People, and Governance. (Platform, Security, Operations are technical.)
  **Why it matters:** Grouping questions are frequent and easy to miss.

- **Q:** A company's staff lack the skills to operate AWS and need training and change management. Which perspective addresses this?
  **A:** The **People** perspective.
  **Why it matters:** People (skills/culture) vs Business (outcomes) vs Governance (risk/cost) is the most-confused trio.

- **Q:** Which CAF phase focuses on identifying capability gaps across the six perspectives?
  **A:** The **Align** phase.
  **Why it matters:** Phase-purpose questions hinge on this exact keyword ("gaps").

- **Q:** What is the difference between AWS CAF and the AWS Well-Architected Framework?
  **A:** CAF guides **organizational** cloud adoption through 6 perspectives; Well-Architected guides the design of a **workload/architecture** through 6 pillars.
  **Why it matters:** Distractor answers routinely swap these two.

- **Q:** Managing cloud cost, risk, and measuring the value of cloud initiatives falls under which perspective?
  **A:** The **Governance** perspective (includes cloud financial management / FinOps and risk management).
  **Why it matters:** Cost/risk wording points to Governance, not Business.
