# Checkout displays incorrect validation message for missing phone number

**Type**: Validation / UX bug

**Severity**: Medium

**Environment:**

- OS: macOS 15.7.1
- Browser: Chrome Version 143.0.7499.147 (Official Build) (arm64)
- App: https://shop.polymer-project.org/checkout

**Preconditions:**

- Cart contains at least one item.

**Steps to Reproduce:**

1. Open the checkout page.
2. Fill all required fields except the phone number field.
3. Attempt to submit the order.

**Expected Result:**

- Submission is blocked.
- Phone Number field is highlighted.
- Error message clearly indicates that the Phone Number field is required (e.g. “Phone number is required”).

**Actual Result:**

- Submission is blocked.
- Phone Number field is highlighted.
- Error message shown is “Invalid phone number”.

**Notes:**

- The error message is misleading because no phone number is provided, so the issue is missing input, not invalid format.
