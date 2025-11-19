# Phase 2 - Defect Log

| Bug ID | Test Case | Description | Severity | Feature/Page | Steps to Reproduce | Expected Result | Actual Result | Status | Issue Link |
|--------|-----------|-------------|----------|---------------|--------------------|-----------------|----------------|--------|------------|
| BUG-001 | TC001 | Empty form submission is allowed | High | Waste Request Form | Open Home → Submit with all fields empty | Validation errors for all fields | Form submits or no errors | Open | [Link]() |
| BUG-002 | TC002 | Valid form fails to submit | High | Waste Request Form | Fill all fields correctly → Submit | Success message displayed | Submission fails | Open | [Link]() |
| BUG-003 | TC003 | Location filtering shows incorrect results | High | User Dashboard | Filter by “Eldoret” | Only Eldoret requests appear | Other locations appear | Open | [Link]() |
| BUG-004 | TC004 | Status update does not refresh automatically | High | User Dashboard | Update a request status | Dashboard updates immediately | Status remains old until reload | Open | [Link]() |
| BUG-005 | TC005 | Long text breaks layout | Medium | Waste Request Form | Enter long text (500+ chars) | Layout remains structured | Layout breaks/misaligned | Open | [Link]() |
| BUG-006 | TC006 | Responsive design not consistent | Medium | Entire UI | Resize screen / use mobile emulator | Layout adjusts properly | Elements overlap | Open | [Link]() |
| BUG-007 | TC007 | Feedback submission fails | Medium | Feedback Section | Enter valid Request ID → Submit | Feedback successfully saved | No success message or fails silently | Open | [Link]() |
| BUG-008 | TC008 | Invalid email accepted | Medium | Form Validation | Enter wrong email format | Email field shows validation error | No error displayed | Open | [Link]() |
| BUG-009 | TC009 | Invalid phone accepted | Medium | Form Validation | Enter invalid phone number | Validation error appears | No phone validation | Open | [Link]() |
| BUG-010 | TC010 | Status filter not working correctly | High | User Dashboard | Filter by “Scheduled” | Only Scheduled should show | Mixed statuses shown | Open | [Link]() |
| BUG-011 | TC011 | Search by Request ID not working | High | Dashboard Search Box | Enter valid Request ID → Search | Only matching request shows | No results or wrong results | Open | [Link]() |
| BUG-012 | TC012 | Multi-status update fails | Medium | User Dashboard | Select multiple requests → Update | All selected update status | Some fail to update | Open | [Link]() |
| BUG-013 | TC013 | Image upload preview missing | Medium | Request Form | Upload valid image | Preview appears before submit | Preview not showing | Open | [Link]() |
| BUG-014 | TC014 | Request deletion not working | High | User Dashboard | Delete a request → Confirm | Request removed | Still visible | Open | [Link]() |
| BUG-015 | TC015 | Pagination displays wrong items | Medium | User Dashboard | Go to page 2 | Page 2 requests appear | Page 1 items still show | Open | [Link]() |
| BUG-016 | TC016 | Sorting by date not correct | Medium | User Dashboard | Click sort by date | Sorted properly | Wrong order | Open | [Link]() |
| BUG-017 | TC017 | Invalid Request ID accepted in feedback | Medium | Feedback Page | Enter invalid Request ID → Submit | Error message appears | Accepts invalid values | Open | [Link]() |
| BUG-018 | TC018 | Logout does not clear session | High | User Dashboard | Click Logout | User redirected & session cleared | User still logged in | Open | [Link]() |
| BUG-019 | TC019 | Accessibility (keyboard navigation) fails | Medium | Whole System | Use Tab/Shift+Tab to navigate | All elements focusable | Some items not focusable | Open | [Link]() |
| BUG-020 | TC020 | Past date allowed | High | Request Form | Enter date before today | Error shown | Past date accepted | Open | [Link]() |
| BUG-021 | TC021 | Future date >30 days accepted | Medium | Request Form | Enter date >30 days ahead | Validation error | No validation applied | Open | [Link]() |
| BUG-022 | TC022 | Duplicate request allowed | High | Waste Request Form | Submit identical request twice | Should block duplicate submissions | Allows duplicates | Open | [Link]() |
| BUG-023 | TC023 | Notification not received after status change | High | User Dashboard | Change request status and monitor | Notification received | None received | Open | [Link]() |
| BUG-024 | TC024 | Unsupported file format accepted | Medium | File Upload | Upload .exe/.pdf → Submit | Validation error | Uploaded successfully | Open | [BUG-024](https://github.com/PLP-Database-Design/wk-6-SystemDeveloper11-1/issues/14#issue-3641223383) |
| BUG-024 | TC024 | User notifications not sent on status change | High | User Dashboard | Request status changes in system | User receives in-app notification when status changes | No notification appears in Dashboard | Open | [Link]() |
| BUG-025 | TC025 | File upload feature missing in Feedback page | Medium | Feedback Page | Open Feedback page → Look for upload option | User should be able to attach a file with feedback | No upload option shown in UI | Open | [BUG-025](https://github.com/PLP-Database-Design/wk-6-SystemDeveloper11-1/issues/11#issue-3632835647) |
| BUG-026 | TC026 | No option available to change or upload profile picture | medium | Profile Page | Open Profile page → edit picture option | User should see an option to upload /change profile picture | No option exists; user stuck with default profile photo | Open | [BUG-026](https://github.com/PLP-Database-Design/wk-6-SystemDeveloper11-1/issues/10#issue-3628833526) |
| BUG-027 | TC027 | Session does not expire after inactivity | High | All Pages | Stay idle 15+ minutes | Auto logout | Session stays active | Open | [BUG-027](https://github.com/PLP-Database-Design/wk-6-SystemDeveloper11-1/issues/8#issue-3628571542) |
| BUG-028 | TC028 | Invalid characters in search field may break page (Blocked) | Medium | Dashboard Search | User must have admin access → Attempt to enter invalid characters (#$%^&) | System validates input or safely rejects invalid characters | Search field not visible to non-admin users → Test cannot be executed | Blocked | [BUG-028](https://github.com/PLP-Database-Design/wk-6-SystemDeveloper11-1/issues/9#issue-3628763872) |
| BUG-029 | TC029 | Unsupported file format accepted | Medium | File Upload | Upload .exe/.pdf → Submit | Validation error | Uploaded successfully | Open | [Link]() | |
| BUG-029 | TC029 | Missing option to cancel or delete a schedule request | Medium | Dashboard | Open request analysis in Dashboard | User should be able to delete their own request | No button or feature available to cancel | Open | [BUG-029 ](https://github.com/PLP-Database-Design/wk-6-SystemDeveloper11-1/issues/13#issue-3640995318) |
| BUG-030 | TC030| Dashboard does not show updated request status in the Schedule Panel | High | User Dashboard | Refresh after update | Updated status visible in dashboard analysis| Old outdated data shown that is zero : no changes actually | Open | [BUG-030](https://github.com/PLP-Database-Design/wk-6-SystemDeveloper11-1/issues/7#issue-3628545764) |
| BUG-031 | TC031 |Logout during active form submission causes unsaved data loss | Medium | Form Handling & Logout Function |Fill schedule form partially → Click Logout| Layout still usable |Warn user about unsaved data; session ends only after confirmation | Open |[BUG-031](https://github.com/PLP-Database-Design/wk-6-SystemDeveloper11-1/issues/5#issue-3625723625)|
| BUG-032 | TC032 | Screen reader announcing all labels | Medium | Accessibility | Use screen reader | All elements announced | Works as expected | Closed| - |
| BUG-033 | TC033 | Error messages not consistent | Medium | Form Validation | Trigger different errors | Messages clear & consistent | Styles vary: not consistent | Open | [Link]() |
| N/A | TC034 | Role-based visibility incorrect | High | User Dashboard | Login as any user | Only user-specific components show | All components visible | Open | - |
| BUG-035 | TC035 | Layout breaks on very small screens | Medium | Responsive Layout | Open app at 200 - 320px width | Clean responsive layout | Overlaps and hidden text | Open | [BUG-035](https://github.com/PLP-Database-Design/wk-6-SystemDeveloper11-1/issues/3#issue-3625548793) |
| BUG-036 | TC036 | Login allows invalid password | High | Login Page | Open login page → Enter valid email → Enter wrong password → Click Login | Error message “Invalid username or password” appears; login blocked | System allows login and no error shown | Open | [BUG-036](https://github.com/PLP-Database-Design/wk-6-SystemDeveloper11-1/issues/4#issue-3625646291) |
| BUG-037 | TC037 | Scheduled Requests Dissapears from Dashboard Analytics| High |User Dashboard |Visit Dashboard after scheduling a pickup →check Total Requests,Missed Pickups| values should change | they are empty yet you,ve requested for a pickup |open |[BUG-037](https://github.com/PLP-Database-Design/wk-6-SystemDeveloper11-1/issues/6#issue-3628441122) | 
| BUG-038| TC038 | No notifications shown anywhere | High | User Dashboard | Make a request → Schedule → Update | Notification list updates | Notification panel empty nor email | Open | [BUG-038](https://github.com/PLP-Database-Design/wk-6-SystemDeveloper11-1/issues/12#issue-3634902912) |

<<<<<<< HEAD
| BUG-025 | TC025 | Missing File opload feature | Medium | File Upload | Upload 6MB+ image | Warning and rejection | Upload accepted | Open | [Link]() |


=======
>>>>>>> upstream/main

