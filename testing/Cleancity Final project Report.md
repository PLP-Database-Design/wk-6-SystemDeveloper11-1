# CleanCity Software Testing Report

## 1. Executive Summary

This report summarizes all software testing activities conducted for the CleanCity Waste Pickup Scheduler web application. Testing covered functional validation, UI/UX checks, accessibility, responsiveness, and regression across all major modules. A total of 38 manual test cases were executed, alongside several automated tests using React Testing Library. Multiple high-severity defects were identified in key functional areas such as form validation, date handling, login authentication, notifications, dashboard analytics, and missing core features.

## 2. Project Overview

**Project Name:** CleanCity – Waste Pickup Scheduler

**Technology Stack:** React 18.2.0, localStorage, Chrome v129, Node.js 18.x

**Purpose:** To streamline waste pickup scheduling and feedback management across .

**Modules Tested:**

* Waste Pickup Request Form
* Dashboard & Analytics
* Feedback Submission
* Notifications
* User Authentication
* Admin Panel (limited access)
* Profile Page
* Responsive UI

---

## 3. Test Objectives

* Validate all user input fields and form submission behavior.
* Identify UI/UX inconsistencies and layout issues.
* Verify data filtering, sorting, search, and dashboard updates.
* Confirm accessibility compliance using keyboard navigation and screen readers.
* Check responsiveness across devices and small screen widths.
* Detect boundary issues (long inputs, invalid dates, duplicates).
* Execute automated validation tests.

---

## 4. Scope of Testing

### In Scope

* Functional testing of all pages.
* UI/UX checks and consistency.
* Accessibility (ARIA roles, screen reader, keyboard navigation).
* Responsive behavior on laptop and mobile.
* Automated unit/UI tests.

### Out of Scope

* Backend or API testing.
* External integrations.
* Performance or load testing.

---

## 5. Test Environment

* **OS:** Windows 10 (64-bit)
* **Browser:** Chrome v129
* **Framework:** React 18.2.0
* **Tools:** Cypress, React Testing Library, Lighthouse, DevTools
* **Devices:** Laptop (1366×768), Pixel 5 Emulator
* **Storage:** localStorage

---

## 6. Test Approach

* Manual testing for functional flow, error handling, UI behavior.
* Automated tests for form validation and submission flows.
* Regression retesting after defect logging.
* Accessibility testing using keyboard navigation and screen reader.
* Responsive testing at breakpoints including 200–320px widths.

---

## 7. Test Deliverables

* Full test plan
* Test cases & checklists
* Automated test scripts
* Defect log (BUG-002 to BUG-038)
* Test summary report (this document)

---

## 8. Roles & Responsibilities

* **Manager – Brian Mbaka:** Approvals, oversight
* **Analyst – Denis Kiptum:** Test design, defect identification
* **Executor – QA Tester:** Manual and automated test execution

---

## 9. Schedule & Milestones

* Test Planning: Nov 5–7, 2025
* Test Case Design: Nov 7–9, 2025
* Test Execution: Nov 9–12, 2025
* Bug Fix & Retesting: Nov 12–13, 2025
* Test Closure: Nov 14–15, 2025

---

## 10. Test Cases Summary

Out of **38 total test cases**:

* **Passed:** 9
* **Failed:** 18
* **Blocked / Not Testable:** 9
* **Replaced:** 1
* **N/A:** 1

### Key Areas Failing:

* Form validations (email, dates, duplicates)
* Dashboard analytics not updating
* Missing upload features
* Notifications not appearing
* Invalid login allowed
* Responsive layout failures on small screens

---

## 11. Major Defects Summary (Phase 2 – Defect Log)

### High Severity Defects

* **BUG-013:** Missing image upload feature in request form
* **BUG-017:** Feedback accepts invalid Request IDs
* **BUG-020:** App allows submission of past dates
* **BUG-021:** App allows submission beyond year limit
* **BUG-022:** Duplicate request submission allowed
* **BUG-024:** No user notifications on status change
* **BUG-030:** Dashboard not updating after status change
* **BUG-036:** Login allows invalid passwords
* **BUG-037:** Dashboard analytics not reflecting scheduled requests
* **BUG-038:** Notification panel and email notifications missing

### Medium Severity Defects

* **BUG-002:** Missing success message after submission
* **BUG-008:** Invalid email accepted
* **BUG-019:** Some elements not keyboard-focusable
* **BUG-025:** File upload missing in feedback page
* **BUG-026:** No profile picture upload option
* **BUG-031:** Logout does not warn about unsaved data
* **BUG-033:** Inconsistent error messages
* **BUG-035:** Layout overlaps at 200–320px widths

### Blocked Items

* **BUG-028:** Cannot test invalid characters in search (admin access required)

---

## 12. Checklists Summary

* Home Page loads: ✔️
* Form validations: ❌ Several failures
* Duplicate prevention: ❌ Not working
* Dashboard filters/search: ❌ Blocked / Not functional
* Admin status updates: ❌ Inaccessible / Not testable
* Notifications: ❌ Not working
* Accessibility: ⚠️ Partially compliant
* Responsive test: ❌ Layout break at small widths
* File upload: ❌ Missing
* Session timeout: ❌ Not expiring
* UI consistency: ⚠️ Mixed results
* Automated tests: ✔️ Basic validation tests passed

---

## 13. Automated Test Summary

Automated tests validated basic form behavior:

* Empty form submission shows error
* Valid form submission displays success message
  These worked in isolation but **failed in the real UI**, indicating implementation gaps.

---

## 14. Risks & Mitigations

| Risk                                          | Impact | Mitigation                                        |
| --------------------------------------------- | ------ | ------------------------------------------------- |
| Missing core features (upload, notifications) | High   | Prioritize in next sprint                         |
| Dashboard not updating                        | High   | Fix logic + add regression tests                  |
| Weak validation (email, dates, login)         | High   | Implement stricter rules with regex & date checks |
| Accessibility gaps                            | Medium | Add labels, ARIA roles, focus states              |
| Layout breaks on small screens                | Medium | Add new CSS breakpoints                           |
| No session timeout                            | High   | Implement inactivity timer                        |

---

## 15. Recommendations

* Improve validation rules for emails, phone, dates
* Add missing features (file upload, notifications)
* Implement proper dashboard data syncing
* Strengthen role-based access control
* Add automated end-to-end tests with Cypress
* Perform UI refactor to support ultra-small screens
* Add global error handling for consistency
* Implement session timeout functionality

---

## 16. Final QA Status

**Overall Quality:** Needs Improvement

**Readiness for Deployment:** ❌ Not ready

**Reason:** Multiple high-severity defects across core functionality and user flows.

---

## 17. Approval

| Name         | Role       | Signature | Date        |
| ------------ | ---------- | --------- | ----------- |
| Brian Mbaka  | QA Manager | Bm        | 11 Nov 2025 |
| Denis Kiptum | QA Analyst | Dk        | 11 Nov 2025 |
| QA Executor  | Tester     |           | 11 Nov 2025 |
