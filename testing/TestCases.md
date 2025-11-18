# Phase 2 - Test Cases and Checklists

## Manual Test Cases
| Test ID | Description | Steps | Expected Result | Actual Result | Status |
|---------|-------------|-------|----------------|---------------|--------|
| TC001 | Submit empty waste pickup form | Go to Home → leave all fields empty → Click Submit | Validation errors should appear for all required fields | works as expected |Pass Closed |
| TC002 | Submit valid waste pickup form | Fill all required fields correctly → Click Submit | Form submitted successfully → Success message displayed | partially | open |
| TC003 | Filter requests by location | Open Dashboard → Apply filter “Eldoret” | Only Eldoret requests displayed |  |  |
| TC004 | Update request status in Admin Panel | Open Admin Panel → Click "Mark as Scheduled" | UI should update immediately |  |  |
| TC005 | Enter long text input | Enter 500+ characters in form fields → Submit | Layout should handle gracefully |  |  |
| TC006 | Responsive design | Resize browser or open on mobile emulator | Layout adjusts correctly for all screen sizes with no overlaps |  |  |
| TC007 | Feedback submission with valid Request ID | Go to Feedback page → Enter valid Request ID → Submit | Success message displayed |  |  |
| TC008 | Submit form with invalid email | Go to Home → Fill all fields → Enter invalid email → Submit | Validation error for email field |  |  |
| TC009 | Submit form with invalid phone number | Enter invalid phone format → Submit | Validation error for phone number |  |  |
| TC010 | Filter requests by status | Open Dashboard → Filter by “Scheduled” | Only requests with “Scheduled” status displayed |  |  |
| TC011 | Search requests by Request ID | Go to Dashboard → Enter valid Request ID in search → Submit | Only matching request displayed |  |  |
| TC012 | Update multiple request statuses | Admin Panel → Select multiple requests → Mark as Completed | All selected requests update status |  |  |
| TC013 | Attach image to request | Fill form → Upload image → Submit | Image successfully attached and preview shown |  |  |
| TC014 | Delete a request | Admin Panel → Select request → Delete → Confirm | Request removed from Dashboard |  |  |
| TC015 | Pagination in Dashboard | Navigate Dashboard → Click page 2 | Requests for page 2 displayed correctly |  |  |
| TC016 | Sort requests by date | Dashboard → Click “Sort by Date” | Requests displayed in ascending/descending order |  |  |
| TC017 | Feedback submission with invalid Request ID | Feedback page → Enter invalid Request ID → Submit | Error message displayed |  |  |
| TC018 | Logout functionality | Click Logout | User redirected to login page, session cleared |  |  |
| TC019 | Accessibility check | Navigate all pages with keyboard only | Focusable elements, ARIA labels, no inaccessible content |  |  |
| TC020 | Submit form with past date | Enter a date in the past → Submit | Validation error displayed; cannot submit past dates |  |  |
| TC021 | Submit form with future date beyond limit | Enter date more than 30 days ahead → Submit | Validation error displayed or warning shown |  |  |
| TC022 | Attempt to submit duplicate request | Fill form with same details as an existing request → Submit | System prevents duplicate submission |  |  |
| TC023 | User without admin rights tries to update status | Login as normal user → Attempt to mark request as Scheduled | Action denied; error message displayed |  |  |
| TC024 | Notification on status change | Admin updates request → Scheduled/Completed | User receives notification (email/in-app) |  |  |
| TC024 | User notifications not received on status change | 1. Login as a normal user → 2. Monitor the Dashboard after a request status is updated in the system | User should receive an in-app notification when request status changes | No notification appears in the Dashboard | ❌ Fail |
| TC025 | File upload option missing in Feedback section | Open Feedback page → Look for file upload button | User should see “Attach File” or “Upload” option | No file upload feature available | ❌ Fail |
| TC026 | No option available to change profile picture | Open Profile page → Look for edit profile picture option | User sees “Change Profile Picture” / “Upload Photo” button | No option exists; user cannot change picture | ❌Fail |
| TC027 | Session timeout | Remain idle for 15+ minutes → Try action | Session expires; user redirected to login |  | Open ,❌ Fail  |
| TC028 | Search with invalid characters | Login as Admin → Go to Dashboard → Enter invalid characters (#$%^&*) in search → Submit | System should reject invalid characters or show validation error | Test blocked – search field not visible without admin access | ❌ Blocked |
| TC029 | Bulk deletion confirmation | Select multiple requests → Delete → Confirm | Only requests confirmed are deleted; system warns before deletion |  | - |
| TC030 | Dashboard refresh after update | Update a Schedule request → Refresh Dashboard | Updated request reflects new status | The Dashboard still shows the old status that is zero. |❌ Fail |
| TC031 | Logout during active form submission | Fill form partially → Click Logout | Session ends, unsaved data warning displayed |  | ❌ Fail  |
| TC032 | Accessibility: screen reader | Navigate app with screen reader | All interactive elements are announced correctly | works as expected | Pass |
| TC033 | Check error messages consistency | Trigger multiple validation errors | All messages clear, consistent, and visible |  | - |
| TC034 | Role-based feature visibility | Login as different roles → View Admin Panel | Only authorized users see admin features | - | N|A |
| TC035 | Responsive layout edge case | Open app on very small screen (e.g., 200 - 320px width) | Layout still readable, no overlap or hidden elements |  | ❌ Fail |
| TC036 | Login with invalid password | Open login page → Enter valid email → Enter wrong password → Click Login | System should display error “Invalid username or password” and prevent login | System allows login :No error shown | ❌ Fail |
| TC037 | Schedule requests disappear from dashboard analytics | Schedule a pickup and check Dashboard analytic counters  | Counters reflect the new request | Counters remain unchanged | ❌Fail |
| TC038 | User receives confirmation notification on request pickup schedule | Submit a schedule request ,Check notifications in Dashboard or email message | User receives in-app notification or email trigured message when request is scheduled | No notifications appear in Dashboard or email | ❌ Fail |

|  |   |   |   |   |    |
| TC026 | File upload exceeding size limit | Upload image > 5MB → Submit | Validation error displayed; file not accepted |  |  |
| TC025 | File upload with unsupported format | Upload .exe or unsupported file → Submit | Validation error displayed; only images accepted |  |  |
---

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
