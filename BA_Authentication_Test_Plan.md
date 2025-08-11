# British Airways — Authentication & Password Recovery Test Plan

**Version:** 1.0  
**Date:** 2025-08-11  
**Author:** Ekaterina

## 1. Scope
Covers web **User Authentication** and **Password Recovery** flows: Login (membership/email/username + password + CAPTCHA), lockout thresholds/messages, **Forgot password?**, password reset email (content/branding/accessibility), reset page (rules/expiry), success page (Back button), and Logout.

## 2. Out of Scope
Mobile apps, account creation/SSO, 2FA, payments, manage booking, performance/security pen-testing.

## 3. Test Items
- Login form & validation
- Lockout thresholds and user-facing messages
- Forgot password navigation and request
- Password reset email (sender/subject, branding, CTA, link target, expiry)
- Password reset page (rules, matching, token validity/expiry)
- Success page (confirmation + Back button)
- Logout (UI location & session end)

## 4. Environment
- **Browsers:** Chrome (stable), Firefox (stable), Edge (stable), Safari (latest)  
- **OS:** Windows 11, macOS 14  
- **Devices:** Desktop primary; quick responsive check for key pages  
- **Email:** Inbox capable of receiving external emails (e.g., Gmail/Outlook)

## 5. Assumptions & Risks
- Test account exists (valid membership/email/username + password).  
- Email deliverability may vary by client/spam filters.  
- Lockout thresholds and copy can differ between environments.

## 6. Approach
- **Functional:** happy paths + critical negatives.  
- **Usability/Accessibility:** branding consistency, error copy clarity, CTA contrast (WCAG AA).  
- **Compatibility:** sanity across listed browsers.  
- **Security-lite:** lockout behaviour, session invalidation after logout.  
- **Exploratory:** time-boxed sessions per area to discover edge cases.

## 7. Design Techniques
Equivalence Partitioning, Boundary Values (attempt counts, password length), State Transition (logged in/out; token valid/expired), Error Guessing, Exploratory.

## 8. Entry Criteria
- Environment reachable; test accounts available; inbox works.  
- Basic navigation and pages load without critical errors.

## 9. Exit Criteria
- Critical paths (Login → Forgot → Email → Reset → Success → Logout) pass.  
- All **High/Medium** defects triaged with next steps.  
- Known issues documented with workarounds where applicable.

## 10. Test Data
- Valid login IDs (membership/email/username) and password.  
- Invalid credentials (wrong password, unregistered email).  
- Email client access.  
- Optional: weak/strong password sets for rules validation.

## 11. Deliverables
- Test Cases (Excel/Sheets)  
- Checklist (Excel)  
- Bug Reports (PDF)  
- (Optional) Test Summary after a run

## 12. Defect Management
- Tracker: Jira (assumed).  
- Fields: Summary, Environment, Steps, Expected/Actual, Severity/Priority, Attachments, Links to test cases.  
- Severity model: Critical / High / Medium / Low.
