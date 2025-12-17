**ID**: TC-CHK-001

**Title**: Checkout access when cart is empty

**Type**: Functional / Negative

**Preconditions**: Cart contains zero items.

**Steps**:

1. Open https://shop.polymer-project.org/checkout

**Expected result**:

- Checkout page displays a "Your cart is empty" message and provides navigation back to shopping.

---

**ID**: TC-CHK-002

**Title**: Checkout submits with valid required fields

**Type**: Functional / Happy path

**Preconditions**: Cart has at least 1 item.

**Test data**:

- Email: petromir@kolev.com
- Phone number: +359888888888
- Cardholder name: Petromir Kolev
- Card number: 1111111111111111
- Address: Trakia 1
- City: Plovdiv
- State/Province: Plovdiv
- Zip/Postal code: 4023

**Steps**:

1. Open checkout page.
2. Fill all required fields with test data values.
3. Submit/Place Order.

**Expected result**:

- Order is accepted (success state, confirmation message, or redirect to confirmation screen).
- No validation errors shown for filled fields.

---

**ID**: TC-CHK-003

**Title**: Submission blocked when a required field is missing

**Type**: Functional / Negative (validation)

**Preconditions**: Cart has at least 1 item.

**Steps**:

1. Open checkout page.
2. Fill all required fields except one required field:

- Phone number

3. Submit/Place Order.

**Expected result**:

- Submission is blocked.
- Missing field is highlighted and an error message is shown.
- Error message clearly indicates that the phone number field is required.

---

**ID**: TC-CHK-004

**Title**: Format validation (email) rejects invalid email

**Type**: Functional / Negative (format)

**Preconditions**: Cart has at least 1 item.

**Steps**:

1. Open checkout page.
2. Enter invalid email format (petro@).
3. Fill other required fields with valid values.
4. Submit/Place Order.

**Expected result**:

- Submission is blocked.
- Email field shows validation error.
- Error message indicates invalid email format.

---

**ID**: TC-CHK-005

**Title**: Submit cardholder name with trailing empty space

**Type**: Edge case

**Preconditions**: Cart has at least 1 item.

**Steps**:

1. In the cardholder name enter a valid name with a trailing space: "Petromir ".
2. Fill other required fields validly.
3. Submit/Place Order.

**Expected result**:

- Submission succeeds without validation error related to trailing whitespace in cardholder name.
