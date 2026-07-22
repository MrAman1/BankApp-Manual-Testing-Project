# 🏦 SecureBank – Manual Testing Project (Portfolio)

A complete, end-to-end **manual QA testing project** built around a sample online/mobile **Banking Application**, created to showcase practical manual testing skills equivalent to **3+ years of QA experience**.

This repository contains everything a QA engineer would produce during a real banking-application testing engagement: a test plan, test strategy, module-wise test cases, a requirement traceability matrix, bug reports, test data, and QA checklists.

> **Disclaimer:** "SecureBank" is a fictional application created purely for demonstration/portfolio purposes. No real bank, customer data, or proprietary system is involved.

---

## 📁 Repository Structure

```
BankApp-Manual-Testing-Project/
│
├── README.md                          # This file
│
├── Documents/
│   ├── Test_Plan.md                   # Scope, approach, resources, schedule, entry/exit criteria
│   ├── Test_Strategy.md               # Testing levels, types, tools, risk-based approach
│   └── Test_Summary_Report.md         # Sample end-of-cycle test summary/closure report
│
├── TestCases/
│   ├── 01_Login_Authentication_TestCases.xlsx
│   ├── 02_Registration_AccountOpening_TestCases.xlsx
│   ├── 03_Fund_Transfer_TestCases.xlsx
│   ├── 04_Account_Management_TestCases.xlsx
│   ├── 05_Bill_Payment_Recharge_TestCases.xlsx
│   └── 06_Loan_Module_TestCases.xlsx
│   (each file has a "Test Cases" sheet + an auto-calculating "Summary" sheet)
│
├── Traceability_Matrix/
│   └── RTM.xlsx                       # Requirement-to-Test-Case mapping & coverage status
│
├── Bug_Reports/
│   ├── Bug_Report_Template.xlsx       # Blank, ready-to-use bug reporting template
│   └── Sample_Bug_Reports.xlsx        # 5 realistic filled-in sample defects
│
├── Test_Data/
│   └── Test_Data.xlsx                 # Reusable valid/invalid test data sets
│
└── Checklists/
    ├── UI_UX_Checklist.md
    ├── Security_Testing_Checklist.md
    └── Usability_Checklist.md
```

---

## 🎯 Application Under Test (AUT) – Overview

**SecureBank** is a hypothetical retail internet/mobile banking application with the following modules:

| Module | Key Features |
|---|---|
| **Login & Authentication** | Customer ID/password login, biometric/OTP login, account lockout, session timeout |
| **Registration & Account Opening** | New user onboarding, KYC document upload, OTP verification |
| **Fund Transfer** | IMPS / NEFT / RTGS transfers, beneficiary management, transaction limits |
| **Account Management** | Balance inquiry, statements, profile updates, MPIN change, card block |
| **Bill Payment & Recharge** | Utility bill payment, mobile recharge, auto-pay/standing instructions |
| **Loan Module** | EMI calculator, loan application, application tracking, foreclosure |

---

## 🧪 Testing Approach

This project follows a standard **STLC (Software Testing Life Cycle)**:

1. **Requirement Analysis** – Reviewed functional requirements per module
2. **Test Planning** – `Documents/Test_Plan.md` and `Documents/Test_Strategy.md`
3. **Test Case Design** – 68 detailed manual test cases across 6 modules, covering:
   - ✅ Positive / Functional flows
   - ❌ Negative & validation scenarios
   - 🔲 Boundary Value Analysis
   - 🔐 Security checks (SQL injection, session handling, OTP/2FA)
   - 🎨 UI/UX consistency
4. **Traceability** – `Traceability_Matrix/RTM.xlsx` maps every requirement to its covering test case(s)
5. **Test Execution** – Status columns (Pass/Fail/Blocked/Not Executed) with conditional formatting, ready for a real execution cycle
6. **Defect Reporting** – `Bug_Reports/` template + sample defects following a standard bug life cycle (New → Open → Retest → Closed)
7. **Reporting & Closure** – `Documents/Test_Summary_Report.md`

## 🛠️ Techniques & Concepts Demonstrated

- Equivalence Partitioning & Boundary Value Analysis
- Requirement Traceability Matrix (RTM)
- Risk-based prioritization (High/Medium/Low)
- Severity vs. Priority classification
- Defect life cycle management
- Positive, Negative, Security, UI, and Usability testing
- Test data management
- Test summary / closure reporting

## 📊 How to Use This Project

- Open any file in `TestCases/` — each has data-validation dropdowns for **Status**, **Priority**, **Severity**, and **Test Type**, plus a **Summary** tab that auto-calculates Pass % using `COUNTIF` formulas as you execute.
- Use `Bug_Reports/Bug_Report_Template.xlsx` to log new defects found during execution.
- Update `Traceability_Matrix/RTM.xlsx` to track requirement coverage and execution status at a glance.

## 👩‍💻 About This Project

Created as a **manual QA testing portfolio project** to demonstrate hands-on experience with:
- Writing clear, traceable, and reusable manual test cases for a financial domain application
- Structuring QA documentation the way a QA team would in a real banking project
- Defect reporting and tracking discipline

Feel free to fork, adapt the templates for your own project, or use it as a reference for interview preparation.

---
**Tech/Tools referenced:** Excel-based test case management, Markdown documentation — easily adaptable to Jira/Zephyr/TestRail/qTest workflows.
