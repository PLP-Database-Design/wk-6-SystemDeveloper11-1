# 🧪 CleanCity Test Plan

## 1. Introduction
**CleanCity: Waste Pickup Scheduler** is a React-based web application for waste management in African cities.  
The goal of this test plan is to outline the testing strategy, objectives, scope, resources, and schedule to ensure the quality and functionality of the application.

---

## 2. Test Objectives
The objectives of this QA process are to:
- Validate all input forms and submission behavior  
- Detect UI/UX and accessibility issues  
- Verify filtering, sorting, and data persistence  
- Check responsiveness across devices  
- Identify boundary and regression issues  
- Implement automated testing using **React Testing Library**

---

## 3. Scope of Testing

**In Scope:**
- Functional testing of all forms and pages  
- UI/UX consistency and layout responsiveness  
- Accessibility validation (alt text, contrast, ARIA roles)  
- Manual and automated tests using React Testing Library & Cypress  

**Out of Scope:**
- Backend and API testing (app uses localStorage)  
- Payment gateway or external API integrations  

---

## 4. Test Environment

| Component | Details |
|------------|----------|
| **Operating System** | Windows 10 (64-bit) |
| **Browser** | Google Chrome v129 |
| **Framework** | React 18.2.0 |
| **Testing Tools** | React Testing Library, Cypress, Lighthouse, Chrome DevTools |
| **Node.js Version** | 18.x |
| **Storage** | localStorage |
| **Devices Tested** | Laptop (1366x768), Mobile Emulator (Pixel 5) |

---

## 5. Test Approach

| Type | Description |
|------|--------------|
| **Manual Testing** | Verify forms, dashboard, admin panel, and feedback manually using defined test cases. |
| **Automated Testing** | Use React Testing Library and Cypress for form validation, filtering, and UI behavior. |
| **Regression Testing** | Re-run key tests after bug fixes. |
| **Accessibility Testing** | Ensure images, buttons, and tables meet accessibility standards. |
| **Performance Testing** | Observe app behavior with large datasets and long text inputs. |

---

## 6. Test Deliverables
- Test Cases & Checklists (`TestCases.md`)  
- Automated Test Scripts  
- Defect Log (`DefectLog.md`)  
- Test Summary Report  
- Updated Jira Tasks  

---

## 7. Roles and Responsibilities

| Role | Member | Responsibilities |
|------|---------|------------------|
| **Manager** |Brian Mbaka | Approves test plan, ensures resource allocation |
| **Analyst** |Denis Kiptum | Designs test cases and identifies defects |
| **Executor** |Nelson Ndinya | Runs manual and automated tests, documents results |

---

## 8. Schedule & Milestones

| Activity | Start Date | End Date |
|-----------|-------------|----------|
| Test Planning | Nov 5, 2025 | Nov 7, 2025 |
| Test Case Design | Nov 7, 2025 | Nov 9, 2025 |
| Test Execution | Nov 9, 2025 | Nov 12, 2025 |
| Bug Fix & Retesting | Nov 12, 2025 | Nov 13, 2025 |
| Test Closure | Nov 14, 2025 | Nov 15, 2025 |

---

## 9. Entry and Exit Criteria

**Entry Criteria**
- Application build is ready for testing  
- Test data and environment are set up  
- Test plan and cases are reviewed and approved  

**Exit Criteria**
- All high-severity bugs resolved  
- Test cases executed with >95% pass rate  
- Test summary report completed  

---

## 10. Risks & Mitigation

| Risk | Impact | Mitigation |
|------|---------|-------------|
| Incomplete requirements | High | Communicate with developer early |
| Time constraints | Medium | Prioritize high-risk areas first |
| UI layout inconsistencies | Medium | Regular UI reviews |
| Browser compatibility | Low | Use multiple browsers during tests |

---

## 11. Approval
| Name | Role | Signature | Date |
|------|------|------------|------|
|Brian Mbaka | QA Manager |Bm  |11 Nov 2025  |
|Denis Kiptum | QA Analyst |Dk  |11 Nov 2025  |
|Wilson Ndinya | Test Executor | Wn |11 Nov 2025  |
