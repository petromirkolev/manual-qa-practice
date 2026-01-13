# City and State fields accept numeric-only input

**Type:** Validation bug  
**Severity:** Medium

**Environment:**

- OS: macOS 15.7.1
- Browser: Chrome 143.0.7499.147 (arm64)
- URL: https://shop.polymer-project.org/checkout

**Preconditions:**

- Cart contains at least one item.

**Steps to Reproduce:**

1. Open the checkout page.
2. Fill all required fields with valid values.
3. Enter numeric-only values in City and State (e.g., City="123", State="123").
4. Submit the order.

**Expected Result:**

- Submission is blocked.
- Validation errors are shown for City and State indicating invalid input.

**Actual Result:**

- Submission succeeds (order completion success message is shown).
