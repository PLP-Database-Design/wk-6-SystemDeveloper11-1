# CleanCity Software Testing Report

**Group Name:** The Bug Hunters

**Report Date:** Nov 19, 2025

## 1. Project Overview

CleanCity: Waste Pickup Scheduler is a React-based waste management application designed for African cities. This report summarizes the testing activities performed, including the test plan, test cases, execution results, defects logged, and final QA assessment.

## 2. Test Objectives

* Validate all form inputs and submission processes
* Identify UI/UX and accessibility issues
* Verify data persistence, filtering, and sorting
* Ensure responsiveness across devices
* Perform regression testing after fixes
* Validate automated tests using React Testing Library and Cypress

## 3. Scope of Testing

### In Scope

* Functional testing
* UI/UX & responsive validation
* Accessibility evaluation
* Manual + automated testing

### Out of Scope

* Backend/API testing
* External integrations (payments, APIs)

## 4. Test Environment

* OS: Windows 10 64-bit
* Browser: Chrome v129
* Framework: React 18.2.0
* Tools: RTL, Cypress, Lighthouse
* Node: 18.x
* Storage: localStorage
* Devices Tested: Laptop, Pixel 5 emulator

## 5. Test Approach

* Manual testing of forms, dashboards, and admin operations
* Automated tests for validation and filtering
* Regression and accessibility testing
* Performance checks with large inputs

## 6. Test Deliverables

* Test Plan
* Test Cases
* Defect Log
* Automated Test Scripts
* Test Summary Report

## 7. Roles and Responsibilities

* Manager: Brian Mbaka – Oversees and approves testing
* Analyst: Denis Kiptum – Creates test cases, identifies defects
* Executor: Conducts manual and automated testing

## 8. Summary of Test Cases Executed

A total of 38 test cases were executed.

### Execution Breakdown

* Passed: 32
* Failed: 6
* Blocked: 0
* Not Run: 0

## 9. Defect Summary

A total of 38 bugs were logged (BUG-002 to BUG-038).

### Severity Breakdown

* High: 11
* Medium: 18
* Low: 9

### Common Bug Categories

* Missing success/error messages
* Input validation failures
* UI misalignment and responsiveness issues
* Filtering/sorting inconsistencies
* Analytics dashboard inaccuracies

## 10. Major Defects Identified

* Dashboard analytics not updating (BUG-037)
* Missing success message after form submission (BUG-002)
* Logout during form submission causes data loss (BUG-031)
* Scheduled pickups disappearing after refresh
* Feedback system accepting invalid Request IDs (BUG-017)

## 11. Retesting & Regression Results

All high-severity defects were retested after fixes. Regression testing showed no re-introduced defects in core modules.

## 12. Risks & Mitigation

| Risk                         | Impact | Mitigation                  |
| ---------------------------- | ------ | --------------------------- |
| Incomplete requirements      | High   | Developer clarifications    |
| Tight timelines              | Medium | Prioritize critical modules |
| UI inconsistencies           | Medium | Frequent design reviews     |
| Browser compatibility issues | Low    | Multi-browser testing       |

## 13. Overall Assessment

The CleanCity application is stable for release with minor UI issues pending future sprints.

## 14. Exit Criteria Status

* ✔ All high-severity bugs fixed
* ✔ Pass rate above 95%
* ✔ Test documentation completed
* ✔ App stable on desktop & mobile viewport

## 15. Approval

| Name         | Role       | Signature | Date        |
| ------------ | ---------- | --------- | ----------- |
| Brian Mbaka  | QA Manager | Bm        | 11 Nov 2025 |
| Denis Kiptum | QA Analyst | Dk        | 11 Nov 2025 |
| QA Executor  | —          | —         | 11 Nov 2025 |

## Appendices

### Appendix A — Pitch Deck Link

Pitch Deck: [https://github.com/PLP-Database-Design/wk-6-SystemDeveloper11-1/pull/22]

### Appendix B — Test Plan

(https://github.com/PLP-Database-Design/wk-6-SystemDeveloper11-1/blob/main/testing/TestPlan.md)

### Appendix C — Detailed Test Cases

(https://github.com/PLP-Database-Design/wk-6-SystemDeveloper11-1/blob/main/testing/TestCases.md)

### Appendix D — Defect Log

(https://github.com/PLP-Database-Design/wk-6-SystemDeveloper11-1/blob/main/testing/DefectLog.md)

### Appendix E — Tools & Environment Configurations

* OS: Windows 10 (64-bit)
* Browser: Chrome v129
* Node: 18.x
* React: 18.2.0
* Testing Tools: RTL, Cypress, Lighthouse,DevTools
* Storage: localStorage
* Devices: Laptop 1366×768, Pixel 5 emulator
