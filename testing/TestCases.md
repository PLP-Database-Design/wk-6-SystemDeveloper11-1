# Phase 2 - Test Cases and Checklists

## Manual Test Cases

| Test ID | Description | Steps | Expected Result | Actual Result | Status |
|---------|------------|-------|----------------|---------------|--------|
| TC001 | Submit empty waste pickup form | Go to Home → leave all fields empty → Click Submit | Validation errors should appear for all required fields | Date field doesn’t show error | ❌ Fail |
| TC002 | Submit valid waste pickup form | Fill all required fields correctly → Click Submit | Form submitted successfully → Success message displayed | Works correctly | ✅ Pass |
| TC003 | Filter requests by location | Open Dashboard → Apply filter “Eldoret” | Only Eldoret requests displayed | Shows Nairobi requests as well | ❌ Fail |
| TC004 | Update request status in Admin Panel | Open Admin Panel → Click "Mark as Scheduled" | UI should update immediately | UI doesn’t refresh automatically | ❌ Fail |
| TC005 | Enter long text input | Enter 500+ characters in form fields → Submit | Layout should handle gracefully | Layout breaks slightly | ⚠️ Partial |
| TC006 | Responsive design | Resize browser or open on mobile emulator | Layout adjusts correctly for all screen sizes | Works mostly fine | ✅ Pass |
| TC007 | Feedback submission | Go to Feedback page → Enter valid Request ID → Submit | Success message displayed | Works correctly | ✅ Pass |

---

## Checklists

- [ ] Home Page loads correctly
- [ ] Waste pickup form validations work
- [ ] Dashboard filters function properly
- [ ] Admin Panel status updates persist
- [ ] Feedback page submissions accepted
- [ ] Awareness page accessibility (images have alt text)
- [ ] UI responsive on mobile and desktop
- [ ] Long input data handled gracefully
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
