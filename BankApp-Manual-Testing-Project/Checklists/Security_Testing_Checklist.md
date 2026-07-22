# Security Testing Checklist (Black-box / Manual QA Level) – Banking Application

> Note: This checklist covers black-box security checks a manual QA engineer can perform. It does **not** replace a dedicated penetration test or security audit.

## Authentication
- [ ] Account locks after configured number of failed login attempts
- [ ] Password field is masked; no password shown in plain text anywhere (UI, URL, browser autofill exposure)
- [ ] Password/MPIN policy enforced (min length, complexity) both client-side and server-side
- [ ] Login form is not vulnerable to basic SQL injection (`' OR '1'='1`) or script injection (`<script>alert(1)</script>`)
- [ ] Forgot Password flow does not reveal whether a given Customer ID/email exists (no user enumeration)

## Session Management
- [ ] Session expires after configured inactivity period
- [ ] Session token/cookie is invalidated on logout (verify browser back button doesn't restore session)
- [ ] Session ID is not exposed in the URL
- [ ] Concurrent session behavior matches business requirement (single-session vs multi-session policy)

## Authorization
- [ ] User cannot access another user's account data by manipulating URL/IDs (IDOR check, e.g., changing account number in request)
- [ ] Sensitive actions (fund transfer, profile update) require re-authentication (MPIN/OTP), not just an active session

## Transaction Security
- [ ] OTP/2FA is mandatory for fund transfers above the configured threshold
- [ ] Server-side validation exists for transaction amount (not just client-side) — verify via basic request manipulation
- [ ] Duplicate/replay of the same transaction request does not result in double debit

## Data Exposure
- [ ] Sensitive data (account number, PAN) is masked in UI where full display isn't required (e.g., XXXX1234)
- [ ] No sensitive data is exposed in browser console logs or network responses beyond what's necessary
- [ ] HTTPS is enforced on all pages handling sensitive/financial data

## Input Validation
- [ ] All input fields reject script/SQL injection patterns gracefully (no raw error/stack trace shown to user)
- [ ] File upload fields (KYC docs) restrict file type and size, and reject executable file types

## Error Handling
- [ ] Generic error messages are shown to end users (no stack traces, SQL errors, or internal server details exposed)
