# Software Configuration Management Plan (SCMP)

## Project Title
**AASTU Library Management System – Update**

## Course
Software Configuration Management (SCM)  
Department of Software Engineering  
Addis Ababa Science and Technology University (AASTU)

## Prepared By
Elite team members

## Version
v1.1

## Date
12/25/2025

---

## 1. Purpose Scope and Objectives

### 1.1 Purpose
The purpose of this Software Configuration Management Plan (SCMP) is to define the policies, procedures, roles, and tools used to manage and control changes to the **AASTU Library Management System – Update** project.

This plan ensures that all project artifacts are:
- Identified as Configuration Items (CIs)
- Version-controlled
- Changed only through a formal change control process
- Auditable and traceable throughout the project lifecycle

### 1.2 Scope
This SCMP applies to all project artifacts including:
- Documentation (SRS, Implementation Document, SCMP, CI Register)
- Source code (frontend and backend)
- Configuration files and data
- Test artifacts
- Baselines and releases

The scope of this project is limited to a **prototype system**, and the emphasis is on SCM practices rather than full system functionality.

### 1.3 Objectives
- Ensure CI identification and ownership
- Maintain controlled change process via CRs
- Create stable baselines for releases
- Provide auditable evidence for PCA & FCA
- Support reproducible releases and rollback

---

## 2. Roles and Responsibilities

| Role | Name | Responsibilities |
|----|----|----|
| Project Manager | Kidus Asebe | Overall project oversight, baseline and release approval |
| SCM Lead | Kalkidan Amare | Owns SCMP, manages CIs, baselines, tagging, and audits |
| Development Lead | Kidus Hawoltu | Code integration, PR reviews, branch management |
| Frontend Developer | Kirubel Legese | Frontend implementation and updates |
| Backend Developer | Kirubel Wondwosen | Backend logic and data handling |
| QA / Tester | Hermela Dereje | Testing, verification, Functional Configuration Audit |
| Documentation & Release Engineer | Kidus Berhane | Documentation updates, release notes, audit reports |

**Approval Authorities**
- SCM Lead and Project Manager must sign off baselines and releases. Their approvals are recorded in baseline and release documents.

---

## 3. Configuration Item (CI) Identification

### 3.1 Configuration Items
Configuration Items (CIs) are project artifacts that are placed under configuration control.

Examples include:
- Software Requirements Specification (SRS)
- Implementation Document
- SCMP
- CI Register
- Source code (frontend and backend)
- Test documents
- Release notes
- Audit reports

### 3.2 CI Naming Convention
All CIs follow the naming format:

CI-Type-Name-v<Major>.<Minor>


Examples:
- DOC-SRS-v1.0
- DOC-SCMP-v1.0
- SRC-Frontend-v0.1
- SRC-Backend-v0.1

### 3.3 CI Ownership
Each CI has a clearly assigned owner responsible for:
- Updating the CI
- Ensuring version correctness
- Initiating Change Requests when modifications are required

---

## 4. Versioning Rules

### 4.1 Document Versioning
- Documents start at version **v1.0** when baselined
- Minor updates increment the minor version (e.g., v1.1)
- Major changes increment the major version (e.g., v2.0)

### 4.2 Source Code Versioning
- Development versions use **v0.x**
- Release versions use **v1.0**, **v1.1**, etc.
- Source code changes are tracked through Git commits and tags

### 4.3 Git Tagging
- Baselines are tagged as: `BL1`, `BL2`
- Releases are tagged as: `v1.0`, `v1.1`

---

## 5. Branching Model

### 5.1 Branch Types
The project uses the following branching strategy:

- `main`  
  Stable branch containing baselined and released code

- `dev`  
  Integration branch for ongoing development

- `feature/*`  
  Feature development branches (e.g., `feature/login-ui`)

- `docs/*`  
  Documentation-specific changes

- `hotfix/*`  
  Critical fixes (if required)

### 5.2 Branch Rules
1. Create `feature/` branch from `dev`.
2. Implement, commit locally, push to remote.
3. Open PR targeting `dev`.
4. At least one code reviewer + QA review required (Dev Lead or SCM Lead).
5. Merge to `dev` after approvals.
6. When `dev` is stable and candidate for release, create a release PR from `dev` → `main` (requires SCM Lead & Project Manager approval).
7. Commit SCM documents, tests, and CR closure evidence to `main` before tagging baseline.

---

## 6. Change Control Process

### 6.1 Change Request (CR)
Any modification to a baselined Configuration Item requires a **Change Request (CR)**.

Each CR includes:
- CR ID
- Description of change
- Affected CIs
- Impact analysis
- Approval status
- Implementation details
- Verification and closure

### 6.2 Change Workflow
1. CR is submitted and documented
2. CR is reviewed by SCM Lead and Project Manager
3. CR is approved or rejected
4. Approved CR is implemented on a feature branch
5. Changes are verified by QA
6. CR is closed and documented in the Change Log

---

## 7. Baseline Management

### 7.1 Baseline Definition
A baseline is a formally approved snapshot of the project placed under configuration control.

### 7.2 Project Baselines
- **Baseline 1 (BL1):**  
  Initial repository structure and documentation (SCMP, CI Register, SRS)

- **Baseline 2 (BL2):**  
  Working prototype with approved Change Requests implemented

### 7.3 Baseline Control
- Baselines are tagged in Git
- Each baseline has a Baseline Record document
- Changes to baselined items require approved CRs

---

## 8. Tools Used

| Tool | Purpose |
|----|----|
| Git | Version control |
| GitHub | Repository hosting, PRs, tagging, releases |
| Next.js | Frontend framework |
| Tailwind CSS | UI styling |
| Go (Golang) | Backend language |
| Gin | Backend framework |
| Markdown | Documentation |
| PDF | Formal documents |

---

## 9. Configuration Audits

### 9.1 Physical Configuration Audit (PCA)
Verifies that:
- All CIs exist in the repository
- CI names and versions are correct
- Repository matches documentation

### 9.2 Functional Configuration Audit (FCA)
Verifies that:
- Approved CRs are implemented
- System behavior matches basic requirements

Audit results are documented and stored in `/docs/audit_reports`.

---

## 10. SCMP Maintenance
This SCMP is a controlled document.  
Any updates to this plan require:
- A Change Request
- Version increment
- Approval by SCM Lead and Project Manager

---