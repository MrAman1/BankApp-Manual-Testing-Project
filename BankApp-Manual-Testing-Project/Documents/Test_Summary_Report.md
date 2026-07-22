# Test Summary Report – SecureBank Banking Application

**Cycle:** Sample Execution Cycle 1
**Report Date:** July 2026
**Prepared By:** QA Team

> This is a sample/template Test Summary Report showing how results would be reported once the test cases in `TestCases/` are executed. Update the figures below after each real execution cycle.

## 1. Summary of Testing

| Module | Total TCs | Passed | Failed | Blocked | Not Executed | Pass % |
|---|---|---|---|---|---|---|
| Login & Authentication | 15 | – | – | – | 15 | – |
| Registration & Account Opening | 12 | – | – | – | 12 | – |
| Fund Transfer | 14 | – | – | – | 14 | – |
| Account Management | 11 | – | – | – | 11 | – |
| Bill Payment & Recharge | 8 | – | – | – | 8 | – |
| Loan Module | 8 | – | – | – | 8 | – |
| **Total** | **68** | – | – | – | **68** | – |

*(Fill in Passed/Failed/Blocked counts as execution progresses — each module's workbook has an auto-calculating Summary tab.)*

## 2. Defect Summary

| Severity | Open | Fixed | Closed | Total |
|---|---|---|---|---|
| Critical | 1 | 1 | 0 | 2 |
| Major | 2 | 0 | 0 | 2 |
| Minor | 2 | 0 | 1 | 3 |
| Cosmetic | 0 | 0 | 0 | 0 |

See `Bug_Reports/Sample_Bug_Reports.xlsx` for details of the sample defects referenced above.

## 3. Test Coverage

Requirement coverage is tracked in `Traceability_Matrix/RTM.xlsx`. All 16 sample requirements across the 6 modules currently map to at least one test case (100% design coverage).

## 4. Key Risks / Open Issues at Time of Reporting

- BUG_002 (Critical) – server-side validation gap allowing negative transfer amounts via API manipulation — blocks sign-off for Fund Transfer module until fixed and retested.
- Two Major defects open in Fund Transfer and Bill Payment areas — recommend fixing before next release candidate.

## 5. Recommendation

Based on the (sample) defect status above, the release is **not recommended** until BUG_002 is resolved and retested successfully, given its direct impact on financial transaction integrity.

## 6. Sign-off

| Role | Name | Status |
|---|---|---|
| QA Lead | — | Pending |
| Project Manager | — | Pending |
