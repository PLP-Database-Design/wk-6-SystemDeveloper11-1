# Phase 2 - Test Cases and Checklists

## Manual Test Cases
| Test ID | Description | Steps | Expected Result | Actual Result | Status | 
|---------|-------------|-------|----------------|---------------|--------|
| TC001 | Submit empty waste pickup form | Go to Home → leave all fields empty → Click Submit | Validation errors should appear for all required fields| works as expected |✅Pass Closed|
| TC002 | Submit valid waste pickup form | Fill all required fields correctly → Click Submit | Form submitted successfully → Success message displayed | Form submits but no success message displayed | ❌ Fail, Open |
| TC003 | Filter requests by location | Open Dashboard → Apply filter “Eldoret” | Only Eldoret requests displayed | Cannot test — filter option not available | ⚠️ Blocked |
| TC004 | Update request status in Admin Panel | Open Admin Panel → Click "Mark as Scheduled" | UI should update immediately | ⚠️ Blocked — requires Admin access | N/A |
| TC005 | Enter long text input | Enter 500+ characters in form fields → Submit | Layout should handle gracefully | Works as expected | ✔️ Pass |
| TC006 | Responsive design | Resize browser or open on mobile emulator | Layout adjusts correctly for all screen sizes with no overlaps | Replaced by TC-035 | 🚀🚀Replaced  |
| TC007 | Feedback submission with valid Request ID | Go to Feedback page → Enter a valid Request ID → Enter feedback → Submit | Success message displayed |submitted successfully| ✔️ Pass |
| TC008 | Submit form with invalid email | Go to Schedule Pickup page → Fill all fields → Enter invalid email → Submit | Validation error for email field | Form accepts partially invalid emails like user@com which is not technically valid| due to insufficience , ❌ Fai| Open |
| TC009 | Submit form with invalid phone number | Enter invalid phone format → Submit | Validation error for phone number | Cannot test — phone number field not available in form |Not Testable |
| TC010 | Filter requests by status | Open Dashboard → Filter by “Scheduled” | Only requests with “Scheduled” status displayed | Cannot test — no requests visible | ❌Blocked |
| TC011 | Search requests by Request ID | Go to Dashboard → Enter valid Request ID in search → Submit | Only matching request displayed | Cannot test — no requests visible |⚠️Blocked |
| TC012 | Update multiple request statuses | Admin Panel → Select multiple requests → Mark as Completed | All selected requests update status | Cannot test — no access to Admin Panel thus no requests visible | Blocked |
| TC013 | Attach image to request | Fill Schedule a Waste Pickup form → Upload image as additional description  → Submit request | Image successfully attached and preview shown | No option available to attach image; upload not possible| ❌ Fail, Open |
| TC014 | Delete a request | Admin Panel → Select request → Delete → Confirm | Request removed from Dashboard | Cannot test — no requests visible in Admin Panel | Blocked⚠️ |
| TC015 | Pagination in Dashboard | Navigate Dashboard → Click page 2 | Requests for page 2 displayed correctly | Cannot test — pagination not available in current view | ⚠️Blocked |
| TC016 | Sort requests by date | Dashboard → Click “Sort by Date” | Requests displayed in ascending or descending order | Cannot test — no requests visible | ⚠️Blocked |
| TC017 | System accepts invalid Request ID in feedback form | Feedback page → Enter invalid Request ID →  enter feedback  → Submit | Error message should be displayed | Feedback submitted successfully with invalid ID no error shown | ❌ Fail, Open |
| TC018 | Logout functionality | Click Logout | User redirected to login page, session cleared | User redirected successfully; session cleared | ✅ Pass |
| TC019 | Accessibility check | Navigate all pages with keyboard only | Focusable elements, ARIA labels, no inaccessible content |  | - |
| TC020 | System allows submission of past dates | Enter a date in the past → Submit | System should prevent submission and display validation error | ❌ Fail : Submission allowed; no error shown | Open |
| TC021 | System allows submission of date beyond a year  limit | Enter date more than 300 days ahead → Submit | System should prevent submission and display validation error | Submission allowed; no error shown | ❌ Open |
| TC022 | Attempt to submit duplicate request| Fill form with same details as an existing request → Submit | System should prevent duplicate submission | Duplicate request submitted successfully; system does not deny submission | ❌Fail, Open|
| TC023 | User without admin rights tries to update status | Login as normal user → Navigate to request page → Attempt to mark request as “Scheduled” | Action denied; user cannot see options to update status | User cannot see or perform any status update actions | ✅Pass | N/A|
| TC024 | User notifications not received on status change | Login as a normal user → Monitor the Dashboard after a request status is updated in the system | User should receive an in-app notification when request status changes | No notification appears in the Dashboard | ❌ Fail |
| TC025 | File upload option missing in Feedback section | Open Feedback page → Look for file upload button | User should see “Attach File” or “Upload” option | No file upload feature available | ❌ Fail |
| TC026 | No option available to change profile picture | Open Profile page → Look for edit profile picture option | User sees “Change Profile Picture” / “Upload Photo” button | No option exists; user cannot change picture | ❌Fail |
| TC027 | Session timeout | Remain idle for 15+ minutes → Try action | Session expires; user redirected to login |  | Open ,❌ Fail  |
| TC028 | Search with invalid characters | Login as Admin → Go to Dashboard → Enter invalid characters (#$%^&*) in search → Submit | System should reject invalid characters or show validation error | Test blocked – search field not visible without admin access | ❌Blocked⚠️ |
| TC029 | No option available to cancel or delete a scheduled request | Go to Dashboard → Open request  | User should see a “Delete” or “Cancel Request” button | No option exists to delete or cancel scheduled requests | ❌ Fail |
| TC030 | Dashboard refresh after update | Update a Schedule request → Refresh Dashboard | Updated request reflects new status | The Dashboard still shows the old status that is zero. |❌ Fail |
| TC031 | Logout during active form submission | Fill form partially → Click Logout | Session ends, unsaved data warning displayed |  | ❌ Fail  |
| TC032 | Accessibility: screen reader | Navigate app with screen reader | All interactive elements are announced correctly | works as expected | ✅Pass |
| TC033 | Check error messages consistency | Trigger multiple validation errors | All messages clear, consistent, and visible |  | - |
| TC034 | Role-based feature visibility | Login as different roles → View Admin Panel | Only authorized users see admin features | - | N/A |
| TC035 | Responsive layout edge case | Open app on very small screen (e.g., 200 - 320px width) | Layout still readable, no overlap or hidden elements | overlapping Occurs | ❌ Fail |
| TC036 | Login with invalid password | Open login page → Enter valid email → Enter wrong password → Click Login | System should display error “Invalid username or password” and prevent login | System allows login :No error shown | ❌ Fail |
| TC037 | Schedule requests disappear from dashboard analytics | Schedule a pickup and check Dashboard analytic counters  | Counters reflect the new request | Counters remain unchanged | ❌Fail |
| TC038 | User receives confirmation notification on request pickup schedule | Submit a schedule request ,Check notifications in Dashboard or email message | User receives in-app notification or email trigured message when request is scheduled | No notifications appear in Dashboard or email | ❌ Fail |

## Checklists

- [ ] Home Page loads correctly
- [ ] Waste pickup form validations work (required fields, email, phone, dates)
- [ ] Duplicate submissions prevented
- [ ] Dashboard filters, search, sort, and pagination function properly
- [ ] Admin Panel status updates persist and role-based access enforced
- [ ] Notifications sent on request status change
- [ ] Feedback page submissions accepted (valid/invalid Request IDs)
- [ ] Awareness page accessibility (images have alt text)
- [ ] UI responsive on mobile and desktop; long inputs handled gracefully
- [ ] File uploads validated (format and size)
- [ ] Session timeout and logout during active submission handled correctly
- [ ] App navigable with keyboard; accessibility verified
- [ ] Validation messages consistent across the app
- [ ] Automated tests run without errors


---

## Early Automated Test Scripts (React Testing Library)

```javascript
import { render, screen, fireEvent } from "@testing-library/react";
import App from "../App";

test("shows error when submitting empty form", () => {
  render(<App />);
  const submitButton = screen.getByText(/submit/i);
  fireEvent.click(submitButton);
  expect(screen.getByText(/please fill all fields/i)).toBeInTheDocument();
});

test("submits form correctly with valid input", () => {
  render(<App />);
  const nameInput = screen.getByLabelText(/name/i);
  const locationInput = screen.getByLabelText(/location/i);
  const submitButton = screen.getByText(/submit/i);

  fireEvent.change(nameInput, { target: { value: "John Doe" } });
  fireEvent.change(locationInput, { target: { value: "Nairobi" } });
  fireEvent.click(submitButton);

  expect(screen.getByText(/request submitted successfully/i)).toBeInTheDocument();
});
### Manual Testing Workflow
- Open the application on Chrome or mobile emulator.
- Navigate through all pages: Home, Dashboard, Feedback, Awareness, Admin Panel.
- Perform the following:
  - Submit forms with empty and valid data.
  - Apply filters and sort tables on Dashboard.
  - Update request status in Admin Panel.
  - Submit feedback with valid Request IDs.
  - Test long input text to observe layout behavior.
  - Check responsive behavior on different screen sizes.
  - Inspect accessibility using DevTools and screen readers.

### Automated Test Scripts (React Testing Library)

```javascript
import { render, screen, fireEvent } from "@testing-library/react";
import App from "../App";

// Test 1: Submit empty form should show validation errors
test("shows error when submitting empty form", () => {
  render(<App />);
  const submitButton = screen.getByText(/submit/i);
  fireEvent.click(submitButton);
  expect(screen.getByText(/please fill all fields/i)).toBeInTheDocument();
});

// Test 2: Submit form with valid inputs
test("submits form correctly with valid input", () => {
  render(<App />);
  const nameInput = screen.getByLabelText(/name/i);
  const locationInput = screen.getByLabelText(/location/i);
  const submitButton = screen.getByText(/submit/i);

  fireEvent.change(nameInput, { target: { value: "John Doe" } });
  fireEvent.change(locationInput, { target: { value: "Nairobi" } });
  fireEvent.click(submitButton);

  expect(screen.getByText(/request submitted successfully/i)).toBeInTheDocument();
});
