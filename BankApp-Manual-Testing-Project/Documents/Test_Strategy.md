# Test Strategy – SecureBank Banking Application

## 1. Purpose

This document describes the overall testing methodology, techniques, levels, and tools used for manual testing of the SecureBank application.

## 2. Testing Levels Covered

| Level | Owner | Notes |
|---|---|---|
| Unit Testing | Development Team | Not part of this QA scope |
| Integration Testing | QA + Dev | Module-to-module data flow (e.g., Fund Transfer → Statement) |
| System Testing | QA Team | Primary focus of this project — end-to-end functional flows |
| UAT | Business/Client | Supported by QA with UAT test case handover |

## 3. Types of Testing Performed

- **Functional Testing** – Validating each feature against requirements (e.g., successful fund transfer)
- **Negative Testing** – Invalid inputs, error handling (e.g., wrong password, invalid PAN)
- **Boundary Value Analysis (BVA)** – Testing at limits (e.g., transaction limit ± 1, min/max tenure)
- **Equivalence Partitioning (EP)** – Grouping valid/invalid input classes to reduce redundant cases while maintaining coverage
- **Security Testing (Black-box level)** – SQL injection attempts, session expiry, account lockout, OTP/2FA enforcement
- **Usability / UI Testing** – Layout consistency, field masking, responsive behavior across browsers/devices
- **Regression Testing** – Re-running affected test cases after each defect fix / build
- **Smoke Testing** – Quick sanity check of critical flows (login, transfer, balance check) before full-cycle execution
- **Cross-Browser / Cross-Device Testing** – Chrome, Firefox, Edge, Android, iOS

## 4. Test Design Techniques

| Technique | Where Applied |
|---|---|
| Equivalence Partitioning | Amount fields, mobile number, PAN validation |
| Boundary Value Analysis | Transaction limits, tenure, interest rate, file size |
| Decision Table / Scenario-based | OTP verification, lockout after N attempts |
| Error Guessing | Duplicate transaction on double-click, network failure mid-transaction |
| State Transition | Loan application status flow (Submitted → Under Review → Approved/Rejected → Disbursed) |

## 5. Severity vs. Priority Classification

| Term | Definition | Example |
|---|---|---|
| **Severity** | Impact of the defect on the system | Critical: Login broken for all users |
| **Priority** | Urgency of fixing the defect | High: Must be fixed before next release |

Standard combinations used in this project:
- **High Priority + Critical Severity** → Fix immediately (e.g., fund transfer allows negative amount)
- **Low Priority + Minor Severity** → Fix in a later release (e.g., cosmetic alignment issue)

## 6. Defect Life Cycle

```
New → Open → In Progress → Fixed → Retest → Closed
                    │                  │
                    └──────► Reopened ◄┘  (if retest fails)

Alternate paths: Rejected / Deferred / Duplicate
```

## 7. Test Case Design Standards

Each test case includes: ID, Module, Scenario, Description, Pre-conditions, Steps, Test Data, Expected Result, Actual Result, Status, Priority, Severity, Test Type, and Execution metadata — see any file in `TestCases/`.

## 8. Tools Referenced (adaptable)

| Purpose | Tool (this repo) | Real-world equivalent |
|---|---|---|
| Test Case Management | Excel (`.xlsx`) | Jira/Zephyr, TestRail, qTest |
| Defect Tracking | Excel (`.xlsx`) | Jira, Bugzilla, Azure DevOps |
| Requirement Traceability | Excel RTM | Jira + Xray, TestRail Requirements |
| Documentation | Markdown | Confluence |

## 9. Risk-Based Testing Approach

Modules are prioritized by business-criticality and risk:

| Module | Risk Level | Rationale |
|---|---|---|
| Fund Transfer | Very High | Direct financial impact, regulatory sensitivity |
| Login & Authentication | Very High | Security gateway to entire application |
| Loan Module | High | Financial commitment, eligibility/compliance logic |
| Account Management | Medium | Data integrity, but lower financial risk per action |
| Bill Payment | Medium | Financial but typically lower value/frequency |
| Registration | Medium | Onboarding gate, KYC/compliance relevant |

High and Very High risk modules receive deeper test coverage (more boundary/negative/security cases), as reflected in the `TestCases/` files.

## 10. Suspension & Resumption Criteria

- **Suspend testing** if a Critical defect blocks a core flow (e.g., login is completely broken) or the environment becomes unavailable.
- **Resume testing** once the blocking defect is fixed and verified in a new build, or the environment is restored.
