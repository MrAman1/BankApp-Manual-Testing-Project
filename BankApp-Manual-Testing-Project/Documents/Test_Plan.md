# Test Plan – SecureBank Online & Mobile Banking Application

**Document Version:** 1.0
**Prepared By:** QA Team
**Date:** July 2026
**Status:** Final

---

## 1. Introduction

This Test Plan defines the scope, approach, resources, and schedule for manual testing activities on the **SecureBank** retail internet and mobile banking application. It covers the Login, Registration, Fund Transfer, Account Management, Bill Payment, and Loan modules.

## 2. Objectives

- Validate that all functional requirements of the banking application are met.
- Identify defects before release to ensure a secure, reliable, and user-friendly experience.
- Verify critical banking workflows (login, fund transfer, bill payment, loan application) work correctly under normal, boundary, and negative conditions.
- Ensure compliance with basic security expectations (authentication, session management, input validation).

## 3. Scope

### 3.1 In Scope
- Login & Authentication (including OTP/biometric, lockout, session handling)
- New User Registration & Account Opening (KYC)
- Fund Transfer – IMPS, NEFT, RTGS
- Account Management – balance, statements, profile updates, card management
- Bill Payment & Mobile Recharge (including auto-pay)
- Loan Module – EMI calculator, application, tracking, foreclosure
- Cross-browser and cross-device UI verification (Chrome, Firefox, Edge, Android, iOS)
- Basic security testing (SQL injection, session expiry, brute force lockout)

### 3.2 Out of Scope
- Backend/database-level testing (covered by separate SIT team)
- Performance/load testing (covered by dedicated performance testing team)
- Full penetration testing (covered by dedicated security team)
- Third-party payment gateway internal testing (only integration touchpoints are validated)

## 4. Test Approach

Manual black-box testing will be performed using functional, negative, boundary value, security, and usability test design techniques. Refer to `Test_Strategy.md` for detailed methodology.

## 5. Test Environment

| Item | Details |
|---|---|
| Application URL | https://staging.securebank-demo.local |
| Browsers | Chrome (latest), Firefox (latest), Edge (latest) |
| Mobile | Android 13+, iOS 16+ |
| Test Environment | Staging (isolated from Production, seeded with synthetic test data) |
| Test Data | See `Test_Data/Test_Data.xlsx` |

## 6. Entry Criteria

- Test environment is stable and accessible.
- Build is deployed to staging with release notes.
- Test cases are reviewed and approved.
- Required test data and test accounts are provisioned.

## 7. Exit Criteria

- 100% of planned High priority test cases executed.
- No open Critical or High severity defects.
- ≥ 95% of test cases passed (or documented/accepted deviations).
- Test Summary Report signed off by QA Lead.

## 8. Roles & Responsibilities

| Role | Responsibility |
|---|---|
| QA Lead | Test planning, review, sign-off, stakeholder communication |
| Manual QA Engineer | Test case design, execution, defect logging & retesting |
| Dev Team | Defect fixes, build support |
| Business Analyst | Requirement clarification |

## 9. Deliverables

- Test Plan (this document)
- Test Strategy
- Test Cases (module-wise, `TestCases/`)
- Requirement Traceability Matrix (`Traceability_Matrix/RTM.xlsx`)
- Defect Reports (`Bug_Reports/`)
- Test Summary Report (`Documents/Test_Summary_Report.md`)

## 10. Schedule (Sample)

| Phase | Duration |
|---|---|
| Requirement Analysis & Test Planning | 3 days |
| Test Case Design & Review | 5 days |
| Test Execution – Cycle 1 | 5 days |
| Defect Fixing & Retest Cycle 2 | 3 days |
| Regression & Sign-off | 2 days |

## 11. Risks & Mitigation

| Risk | Mitigation |
|---|---|
| Delayed builds impacting test schedule | Buffer days built into schedule; parallel test case prep |
| Test data unavailability (KYC docs, OTP) | Pre-provisioned test data set maintained in `Test_Data/` |
| Environment instability | Daily smoke test before full execution begins |
| Requirement ambiguity | Early clarification sessions with BA before test design |

## 12. Assumptions

- Staging environment mirrors production configuration closely enough for functional validation.
- Third-party services (SMS/OTP gateway, biller APIs) have working sandbox/mock endpoints.
