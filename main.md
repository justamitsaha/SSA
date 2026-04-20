### What is DART Assessment?

**DART** is an internal **TCS delivery governance and assurance framework**. A **DART assessment** is conducted at the **project level** to objectively evaluate how well a project is adhering to defined delivery, risk, security, and assurance practices. 

### Purpose of DART

The DART assessment is used to:

-   Assess **delivery maturity** of projects
-   Identify **gaps in risk, security, and compliance**
-   Provide **actionable recommendations** for improvement
-   Track organizational maturity trends (BASIC / STANDARD / ADVANCED)

### What does DART typically assess?

From the emails and dashboards shared internally, DART assessment data feeds into **SSA (Secure Software Assurance)** and other governance metrics. Evaluated areas include:

-   Secure coding practices
-   Security testing (SAST, DAST, Pen Testing, SCA)
-   Threat modeling
-   Data protection & encryption
-   Compliance and audit readiness
-   Risk management and controls

These areas are explicitly referenced as being derived from **DART assessment data across projects**
### DART Maturity Levels

Projects are categorized based on maturity:

-   **BASIC** – Initial / foundational practices
-   **STANDARD** – Defined and followed practices
-   **ADVANCED** – Optimized, proactive, and measurable practices

Example (BFSI BG snapshot):

-   BASIC – ~36%
-   STANDARD – ~55%
-   ADVANCED – ~9%  
    

### How DART is used in practice

-   Conducted **periodically** (new assessment or re‑assessment)
-   Coverage and maturity are tracked at **BG / ISU level**
-   Feeds dashboards used by **Delivery Heads, SSA SPOCs, and DEG teams**
-   Used during **audits, compliance reviews, and continuous improvement initiatives** 
### Simple one‑line summary

> **DART assessment is a TCS internal project-level assessment framework used to evaluate delivery maturity, risk, security, and compliance, and to drive continuous improvement across projects.**

If you want, I can also explain:

-   Difference between **DART vs SSA**
-   **Who triggers DART assessments** in a project
-   **How to prepare a project** for DART assessment

Here’s a **clear, practical comparison of DART vs SSA**, grounded in how they are actually used in **TCS delivery and BFSI communications**.

----------

## DART vs SSA – What’s the difference?

### 1️⃣ What each one is

Aspect  		**DART**  **SSA**
Full form		**Delivery Assurance & Risk Transformation**  **Secure Software Assurance**
Nature      **Assessment framework**  **Security practice framework**
Focus        Overall **delivery, risk, and compliance maturity** of a project **Application & software security practices**
Scope Broad (delivery + security + governance) Narrow & deep (security only)

### 2️⃣ Core purpose

**DART**

-   A **project-level assessment** used to evaluate how well a project follows delivery, risk, and security standards.
-   Helps leadership track **coverage, gaps, and maturity** across projects.
-   Produces **BASIC / STANDARD / ADVANCED** maturity ratings.
**SSA**

-   A **set of recommended security practices** that should be implemented by projects.
-   Focuses on _how securely software is built, tested, and deployed_.
-   SSA adoption and compliance are **measured using DART data**.

**In short:**

> **DART measures** → **SSA practices implement**

----------

### 3️⃣ What is actually assessed or tracked?

#### ✅ DART assesses (high level):

-   Delivery & governance controls
-   Risk management
-   Compliance readiness
-   Security posture (inputs for SSA)
-   Overall project maturity

DART dashboards are generated **based on assessment data from projects that have taken the DART assessment**

#### ✅ SSA focuses on security practices such as:

-   Secure coding guidelines
-   SAST / DAST / IAST
-   OSS vulnerability scan (SCA)
-   Penetration testing
-   Threat modeling
-   Data encryption
-   Secrets management
-   Security reviews

These SSA metrics are **reported through dashboards derived from DART assessment data**.

### 4️⃣ Relationship between DART & SSA (very important)

They are **not alternatives**.

```
SSA = “What security practices should be done”
DART = “How well are they actually being done”

```

-   SSA practices are **embedded within DART assessments**
-   DART reports **coverage, maturity, and priority** for SSA items
-   Leadership monitors **SSA improvement via DART dashboards**


### 5️⃣ Output & reporting

Area DART SSA
Output Maturity levels, coverage %, gaps Security scores, priority indicators
Reporting BG / ISU dashboards SSA dashboard (fed by DART)
Frequency Periodic assessment & re-assessment Continuous practice improvement
Audience Delivery Heads, DEG, Auditors Dev teams, SSA SPOCs, Security leads

### 6️⃣ Simple analogy (easy to remember)

-   **SSA** → Security _syllabus_
-   **DART** → Security + delivery _exam & report card_

----------

### One‑line takeaway

> **SSA defines secure software practices, while DART is the authoritative assessment mechanism that measures how effectively those practices (and overall delivery controls) are implemented across projects.**

If you want, I can also explain:

-   Where **SPQA** fits with DART
-   How **DART maturity impacts audits**
-   Typical **gaps seen in SSA via DART** in BFSI projects


## Who triggers DART assessments in a project?

### ✅ Primary trigger: **Project / Delivery Leadership**

DART assessments are **triggered at the project level**, typically by:

-   **Delivery Manager (DM)**
-   **Project Manager (PM)**
-   **Delivery Lead / Account Delivery Lead**

These roles are responsible for ensuring that projects comply with **delivery governance, risk, and security assessments**, including **SPQA / DART activities**, which are explicitly listed as mandatory quarterly activities in DEG governance calls.

### ✅ Governance trigger & oversight: **DEG / Quality / Risk Teams**

-   **Corporate DEG / SRE / Quality teams** mandate periodic DART assessments.
-   They track **DART coverage, maturity, and pending assessments** at BG / ISU level using dashboards.
-   Communications clearly state that **DART insights are derived only from projects that have taken the DART assessment**, indicating that projects are expected to trigger and complete them.

### ✅ Functional coordination: **SSA SPOCs**

-   **SSA SPOCs (Secure Software Assurance SPOCs)** do **not usually trigger** DART themselves, but:
    -   They **follow up with projects**
    -   Use **DART data** to review and improve SSA practices
    -   Coordinate remediation actions based on DART outcomes

This linkage is explicitly stated in mails asking SSA SPOCs to use **DART assessment data to connect with accounts and review security practices**.

### ✅ Typical situations when a DART assessment is triggered

A DART assessment is usually initiated when:

-   A **new project** starts
-   A **periodic / quarterly governance cycle** is due
-   A **re‑assessment** is required (explicitly mentioned in dashboards) 
-   There is:
    -   Audit readiness requirement
    -   Compliance review
    -   DEG / SPQA tracking requirement

## Simple responsibility map

Role                                                    Responsibility 
**PM / DM / Delivery Lead** ✅ Triggers and completes DART assessment

**DEG / Quality / Risk Teams** ✅ Mandate, govern, and track coverage

**SSA SPOC** ✅ Reviews results, follows up on security gaps

**BG / ISU Leadership** ✅ Reviews dashboards and maturity trends

## One‑line summary

> **DART assessments are triggered by the Project/Delivery leadership (PM/DM), mandated and tracked by DEG/Quality teams, and leveraged by SSA SPOCs for security improvement.**

If you want, I can also explain:

-   **When re‑assessment is mandatory**
-   **What delays a DART assessment**
-   **What evidence projects need before triggering DART**
