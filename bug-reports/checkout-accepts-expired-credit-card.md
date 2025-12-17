# Checkout accepts credit card with expiry date in the past

**Type:** Business logic / Validation bug  
**Severity:** High

**Environment:**

- OS: macOS 15.7.1
- Browser: Chrome 143.0.7499.147 (arm64)
- URL: https://shop.polymer-project.org/checkout

**Preconditions:**

- Cart contains at least one item.

**Steps to Reproduce:**

1. Open the checkout page.
2. Fill all required fields with valid values.
3. In the card expiry field, enter an expiry date in the past (e.g., "01/2020").
4. Submit the order.

**Expected Result:**

- Submission is blocked.
- A validation error is shown for the expiry date indicating the card is expired/invalid.

**Actual Result:**

- Submission succeeds (order completion success message is shown).
