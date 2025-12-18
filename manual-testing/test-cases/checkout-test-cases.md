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

---

**ID**: TC-CHK-006

**Title**: Missing email blocks submission

**Type**: Functional / Negative (validation)

**Preconditions**: Cart has at least 1 item.

**Steps**:

1. Open checkout page.
2. Leave email field empty.
3. Fill all other fields validly.
4. Submit the order.

**Expected result**:

- Submission is blocked with a validation error that email is required.

---

**ID**: TC-CHK-007

**Title**: Missing card number blocks submission

**Type**: Functional / Negative (validation)

**Preconditions**: Cart has at least 1 item.

**Steps**:

1. Open checkout page
2. Leave card number field empty.
3. Fill all other fields validly.
4. Submit the order.

**Expected result**:

- Order submission is blocked with a validation error that credit card number is required.

---

- **ID**: TC-CHK-008

**Title**: Invalid card number is rejected

**Type**: Functional / Negative (validation)

**Preconditions**: Cart has at least 1 item.

**Steps**:

1. Fill credit card number field with invalid data e.g. card number: "123".
2. Fill all other fields validly.
3. Submit the order.

**Expected result**:

- Order submission is blocked with a validation error that credit card number is invalid.

---

**ID**: TC-CHK-009

**Title**: Validation error for postal/ZIP field

**Type**: Functional / Negative (validation)

**Preconditions**: Cart has at least 1 item.

**Steps**:

1. Enter invalid postal code e.g. postal code: "asdf".
2. Fill all other fields validly.
3. Submit the order.

**Expected result**:

- Order submission is blocked with validation error showing invalid postal code.

---

**ID**: TC-CHK-010

**Title**: Email with leading/trailing whitespaces is handled

**Type**: Edge case

**Preconditions**: Cart has at least 1 item.

**Steps**:

1. Fill email field with leading/trailing whitespace e.g. " petromir@kolev.com ".
2. Fill all other fields validly.
3. Submit the order.

**Expected result**:

- Order submission succeeds without validation errors related to leading/trailing whitespace in email.

---

**ID**: TC-CHK-011

**Title**: Extremely long address input handling

**Type**: Edge case

**Preconditions**: Cart has at least 1 item.

**Steps**:

1. Fill a long address (paste a 200+ chars long string).
2. Fill all other fields validly.
3. Submit the order.

**Expected result**:

- Order submission succeeds OR order submission is blocked with clear max-length/validation error for address.

---

**ID**: TC-CHK-012

**Title**: Non-latin characters in name/city are handled properly

**Type**: Edge case

**Preconditions**: Cart has at least 1 item.

**Steps**:

1. Fill in name or city with non-latin characters e.g. "Петромир Колев".
2. Fill all other fields validly.
3. Submit the order.

**Expected result**:

- Order submission succeeds OR fails with a clear validation error.

---

**ID**: TC-CHK-013

**Title**: Basic performance: submit completes within reasonable time

**Type**: Non-functional

**Preconditions**: Cart has at least 1 item.

**Steps**:

1. Fill all required fields validly.
2. Submit the order.
3. Wait for successful order completion screen redirect to happen.

**Expected result**:

- Order submission takes less than 3 seconds.

---

**ID**: TC-CHK-014

**Title**: Basic responsiveness: layout usable at narrow viewport

**Type**: Non-functional

**Preconditions**: Cart has at least 1 item.

**Steps**:

1. Go to the checkout page at https://shop.polymer-project.org/checkout
2. Open Chrome > More Tools > Developer Tools.
3. Toggle device toolbar (responsive mode).
4. Set width to 375px.
5. Scroll through checkout form.

**Expected result**:

- Checkout layout is changing proportionally to the chosen width.

---

**ID**: TC-CHK-015

**Title**: Refresh behavior mid-filled form

**Type**: State/Flow test

**Preconditions**: Cart has at least 1 item.

**Steps**:

1. Fill all of the required fields validly.
2. Refresh the form.

**Expected result**:

- Form fields behavior on refresh is observed (cleared or persisted).
- Cart items remain intact.
