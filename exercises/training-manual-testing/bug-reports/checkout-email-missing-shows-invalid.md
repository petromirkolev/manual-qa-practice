# Checkout shows "Invalid email" error when email field is empty

**Type:** Validation / UX bug  
**Severity:** Medium

**Environment:**

- OS: macOS 15.7.1
- Browser: Chrome 143.0.7499.147 (arm64)
- URL: https://shop.polymer-project.org/checkout

**Preconditions:**

- Cart contains at least one item.

**Steps to Reproduce:**

1. Open the checkout page.
2. Leave the Email field empty.
3. Fill all other required fields with valid values.
4. Submit the order.

**Expected Result:**

- Submission is blocked.
- A validation error is shown indicating the Email field is required (e.g., “Email is required”).

**Actual Result:**

- Submission is blocked.
- Error message shown is “Invalid email”.
