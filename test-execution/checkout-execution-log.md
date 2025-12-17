# Checkout Test Execution Log

## Environment

- OS: macOS 15.7.1
- Browser: Chrome Version 143.0.7499.147 (Official Build) (arm64)
- URL: https://shop.polymer-project.org/checkout

## Execution Date

- 2025-17-12

## Test Results

**Test Case ID**: TC-CHK-001

**Description**: Checkout access when cart is empty

**Result**: PASS

**Notes**: Empty cart message displayed.

---

**Test Case ID**: TC-CHK-002

**Description**: Checkout submits with valid required fields

**Result**: PASS

**Notes**: Order completed successfully.

---

**Test Case ID**: TC-CHK-003

**Description**: Submission blocked when phone number is missing

**Result**: FAIL — see bug-report checkout-phone-number-error-message.md

**Notes**: Error message says “Invalid phone number”.

---

**Test Case ID**: TC-CHK-004

**Description**: Invalid email format is rejected

**Result**: PASS

**Notes**: Correct validation.

---

**Test Case ID**: TC-CHK-005

**Description**: Trailing whitespace in cardholder name accepted

**Result**: PASS

**Notes**: Submission successful.
