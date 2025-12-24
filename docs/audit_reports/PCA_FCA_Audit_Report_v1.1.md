# Configuration Audit Report — PCA & FCA  
**Project:** AASTU Library Management System – Update  
**Release:** v1.1 (Built from Baseline BL3)  
**Prepared by:** Kalkidan Amare (SCM Lead)  
**Date:** 2025-12-25

---

## 1. Executive Summary
This Configuration Audit Report presents the results of the Physical Configuration Audit (PCA) and the Functional Configuration Audit (FCA) for Release v1.1 of the AASTU Library Management System. The objective was to verify that all Configuration Items (CIs) are properly identified, named, versioned, and that approved Change Requests (CR-003, CR-004, CR-005) were implemented and validated by QA.

**Audit conclusion:** PCA = PASS; FCA = PASS. Release v1.1 is approved for formal release.

---

## 2. Audit Scope & Methodology

### 2.1 Scope
- Documentation under `docs/` (SCMP.md, CI_Register.md, Baseline records, Change Requests)
- Source code in `src/` (frontend & backend)
- Tests located in `/tests`
- Git artifacts: annotated tags (BL2, BL3, v1.1), commit hashes, PRs

### 2.2 Methodology
- Verified existence and content of documents
- Cross-checked CI_Register entries against repository files and tags
- Traced CRs to implementation commits and PRs
- Executed selected acceptance tests from `tests/Manual_Test_Cases.md`
- Reviewed test report `Test_Report_V1.1.md`
- Interviewed owners for approvals (recorded in Baseline and CR files)

---

## 3. Physical Configuration Audit (PCA)

### 3.1 Documents Verification
- `docs/SCMP.md` — present and updated (v1.1)
- `docs/CI_Register.md` — present and updated (includes CI-007..CI-010 with v1.1)
- `docs/baselines/BL2-Record.md` — present (BL2)
- `docs/baselines/BL3-Record.md` — present (BL3)
- `docs/change_requests/Change_Request_CR-003.md` — present and signed
- `docs/change_requests/Change_Request_CR-004.md` — present and signed
- `docs/change_requests/Change_Request_CR-005.md` — present and signed
- `docs/releases/Release_Notes_R1.1.md` — present
- `tests/Test_Report_V1.1.md` — present

### 3.2 CI Identification & Naming
- Random sample checks taken across repo:
  - `DOC-SCMP-v1.1` referenced in file header (SCMP.md)
  - `SRC-Backend-v1.1` mapped to backend folder in CI Register
  - All CI IDs are consistent with register entries

### 3.3 Tag & Version Check (commands verified in audit)
- `git tag --list` returned: BL1, BL2, BL3, v1.0, v1.1
- `git show BL3` → commit `a3f...` (baseline commit hash recorded in BL3-Record.md)
- `git show v1.1` → commit `b7d...` (release commit hash recorded)

**PCA findings:** No missing files; naming conventions followed; versions consistent.

---

## 4. Functional Configuration Audit (FCA)

### 4.1 Change Request Implementation Traceability
- **CR-003 (Kalkidan Amare)** — Forgot password & OTP
  - PR: `feature/forgot-password` → merged into `dev` then `main`
  - Commits: `0b2f6fd`, `db0de90` (OTP service & email delivery)
  - Test evidence: `tests/Manual_Test_Cases.md` (TC-AUTH-01..TC-AUTH-04) — all PASS

- **CR-004 (Kirubel Legese / Proffesorgreen)** — Book analytics
  - PR: `feature/analytics` → merged
  - Commits: `e6a5883`, `3b9f62d`, `7de9cfd`
  - Test evidence: `tests/Manual_Test_Cases.md` (TC-ANALYTICS-01..03) — PASS

- **CR-005 (Kidus Asebe)** — Integration & validation
  - PR: `feature/integration` or merges to `dev` documented
  - Implementation evidence: Baseline BL3-Record.md and `Test_Report_V1.1.md`

All CRs have implementation commits and PR merges and are updated in CI_Register.

### 4.2 Functional Tests & Results

The following functional acceptance tests were executed for **Release 1.1**, focusing on the newly introduced authentication recovery features.

| Test ID | Scenario | Result | Notes |
|---:|---|---:|---|
| **TC-FP-01** | Forgot Password – Request OTP using registered email | PASS | OTP generated and email delivered successfully |
| **TC-OTP-01** | OTP Validation – Verify correct OTP and reset password | PASS | OTP validated; password reset completed |

### 4.3 Non-conformances
- Minor UX inconsistencies (not a functional defect).
- No blocking defects found.

---

## 5. Audit Findings & Recommendations

### Findings
- Documentation and repo artifacts are consistent and complete.
- All CRs were implemented and verified.
- Baseline BL3 and Release v1.1 reflect stable, tested code.

### Recommendations
- Maintain strict PR -> dev -> main process and always update CI_Register prior to baseline tagging.
- Add small UX fixes to next sprint (post-release patch).
- Archive final artifacts (SCMP, BL3-Record, Release notes, Test Report) in `docs/archive/` after release.

---

## 6. Conclusion & Signatures
Based on the PCA and FCA activities, Release v1.1 is **approved**.

**Auditor / SCM Lead:**  
Name: Kalkidan Amare  
Signature: kal
Date: 2025-12-25

**Project Manager:**  
Name: Kidus Asebe  
Signature: kidus
Date: 2025-12-25
