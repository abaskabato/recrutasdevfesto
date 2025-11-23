# 📜 The Recrutas Development Manifesto: Code for Maintainability

**Preamble:** We believe that the speed of execution is measured not by how fast we write the first line of code, but by how fast we can continue to deliver quality features months from now. Our "vibe coding" is a commitment to discipline, structure, and quality, ensuring every line of code is human-readable, testable, and scalable, regardless of the platform or toolset we use.

---

## Phase 0: MVP Stabilization (The "As-Is" Baseline)

**Applicability:** Only required for transitioning existing, unstructured codebases. If starting a new project, begin at Phase 1.

| Step | SOP Action | Detailed Procedure | Generic Tool Function |
| :--- | :--- | :--- | :--- |
| **0.1. Current State TDD** | **MANDATORY Baseline Documentation.** Reverse-engineer the MVP architecture and data model. | **0.1.1. Codebase Ownership:** Lead Architect (LA) identifies primary contributors and high-churn files via Git history. **0.1.2. Data Model Reconstruction:** Analyze the live database schema to reconstruct the current data model (ERD). **0.1.3. Service/API Mapping:** Systematically document all existing API endpoints (inputs, outputs, side effects) to define the current external contracts. | **Version Control System (VCS)**, **Documentation Platform/Wiki**, **Diagramming Tool** |
| **0.2. Quality Assessment** | **Mandatory Static Analysis Run.** Quantify existing technical debt and security risks. | **0.2.1. Static Analysis Execution:** Run a **Static Analysis Tool** via the **Continuous Integration (CI) Pipeline** against the entire codebase on the main branch. **0.2.2. Report Analysis:** LA extracts all files with **high Cyclomatic Complexity** and all **Critical/Major** security issues to create the **Initial Refactoring Backlog**. | **Static Analysis Tool**, **CI/CD Platform** |
| **0.3. Feature Criteria Mapping** | **Behavioral Definition.** Document current functional behavior as testable criteria. | **0.3.1. Behavioral Definition:** PMs/Devs write **observable, black-box Acceptance Criteria (AC)** for the top 80% of MVP usage. **0.3.2. Code/Criteria Linking:** Link these AC tickets to the relevant files/API endpoints responsible for execution. | **Project Management Tool (PMT)**, **Shared Documentation** |

---

## Phase 1: Planning & Design (The Blueprint Vibe)

**Principle:** We invest in design upfront to prevent costly waste later. We **"front-load the pain."**

| Step | SOP Action | Detailed Procedure | Generic Tool Function |
| :--- | :--- | :--- | :--- |
| **1. Technical Design Document (TDD) Development** | **Documentation-First.** The TDD details the problem, proposed solution, architecture, data flow, API specifications, and integration points *before* writing code. | **1.1. Proposal & Design:** Write the TDD in **Markdown** (or a similar lightweight format). Architecture diagrams must be clear and included. **1.2. Subsystem Isolation (Transition only):** Clearly define how this new system interfaces with the legacy core via stable contracts. | **Documentation Platform/Wiki**, **Diagramming Tool** |
| **2. Design Review** | **Formal Risk Mitigation.** Formal review of the TDD to identify scalability, security, and maintenance risks. | **2.1. Circulation:** TDD is circulated 48 hours prior. **2.2. Senior Review:** Mandatory attendance by Senior Engineers who are instructed to **"shred"** the design. **2.3. Sign-off:** All open questions and risks are addressed and tracked in a linked review ticket before development is authorized. | **PMT**, **Video Conferencing** |

---

## Phase 2: Internal Preparation (The Empathy Vibe)

**Principle:** Code is written not just for machines, but for the next human to read it.

| Step | SOP Action | Detailed Procedure | Generic Tool Function |
| :--- | :--- | :--- | :--- |
| **3. Subsystem Documentation & Isolation** | **Define and Stabilize Interfaces.** Create internal documentation for developer onboarding and system stability. | **3.1. Interface Contract:** Define the stable, public interfaces for the new subsystem. **3.2. Auto-Documentation:** Write comprehensive docstrings/comments; use **Code Documentation Generators** to auto-generate API documentation directly from the code. **3.3. DoD:** Clearly define the Definition of Done (e.g., minimum test coverage, logging standards). | **Code Documentation Generators**, **VCS** |
| **4. Backlog Development & Sprint Planning** | **Atomic Task Definition.** Translate design components into granular, manageable work items. | **4.1. Task Creation:** PMs/TPMs collaborate with devs to create atomic **PMT Tickets** that link back to the TDD. **4.2. Refactoring Priority (Transition only):** The **Initial Refactoring Backlog (0.2.2)** takes priority in the first dedicated stabilization sprints. **4.3. Acceptance Criteria (AC):** Every ticket must include clear, measurable AC written from a **testing perspective**. | **Project Management Tool (PMT)** |

---

## Phase 3: Execution & Quality Assurance (The TDD Vibe)

**Principle:** We use AI to execute faster, but human-written tests define the contract.

| Step | SOP Action | Detailed Procedure | Generic Tool Function |
| :--- | :--- | :--- | :--- |
| **5. Software Development (TDD & AI)** | **Mandatory Test-Driven Development (TDD).** Tests define the contract, code fulfills the contract. | **5.1. Test-First:** The developer **must write tests first** (Unit and Integration) that satisfy the ticket's AC. **5.2. Legacy Code Touch:** If modifying legacy code, **regression tests** must be added to cover existing behavior before any changes. **5.3. AI Force Multiplier:** Use **AI Coding Assistant** to assist code generation *only after* tests are written. Developer owns, reviews, and refactors all generated code. | **IDE**, **Testing Frameworks**, **AI Coding Assistant** |
| **6. Code Submission & Review** | **Strict Quality Gate & Human Vetting.** Automated analysis performs the initial filter; humans enforce architecture and clarity. | **6.1. AI Pre-Review:** Pull Request (PR) triggers **CI Pipeline** to run **Static Analysis**. **6.2. Quality Gate Block:** PR merging is **BLOCKED** if the Static Analysis tool reports a failure (e.g., introducing new critical debt). **6.3. Human Review:** Mandatory **Two-Developer Approval**. Reviewers focus on **architectural alignment, logic simplicity, and human readability** (e.g., descriptive naming, clear structure) to ensure the code is maintainable. | **Code Review Platform**, **Static Analysis Tool** |
| **7. Testing and Deployment** | **Consistent Delivery.** Ensure reliable, production-ready release of the verified artifact. | **7.1. CI/CD Pipeline:** The **CI/CD pipeline** runs all tests (new and regression), builds the final artifact (e.g., container image), and tags the build. **7.2. Staging Verification:** The artifact is deployed to a Staging Environment. QA/PM verify all ACs are met. **7.3. Production Push:** The **identical artifact** is pushed to Production only after explicit sign-off. | **CI/CD Platform**, **Container Orchestration Tools** |



---
## 🔑 Our Commitment to Maintainability

The **Recrutas Development Manifesto** is our promise, grounded in these three universal truths:

1.  **If it's undocumented, it doesn't exist (Steps 1 & 3).**
2.  **If it's not tested, it's broken (Step 5).**
3.  **If it's not clear, it's debt (Step 6).**
