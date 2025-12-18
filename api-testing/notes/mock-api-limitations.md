# Mock API Limitations — JSONPlaceholder

## Purpose

This document describes known limitations of the JSONPlaceholder API used during API testing practice.

JSONPlaceholder is a mock API intended for learning. It does not provide real backend validation logic.

---

## Observed limitations

### 1. No input validation on POST requests

- Missing required fields do not result in 4xx errors.
- Invalid data types (e.g. string instead of number) are accepted.
- API responds with "201 Created" even for malformed requests.

### 2. No persistence

- Created resources are not actually stored.
- Subsequent GET requests do not reflect previously created data.

### 3. Limited error handling

- Validation errors are not returned.
- Error messages are not representative of production APIs.

---

## Impact on Testing

Because of these limitations:

- Negative API test cases cannot validate backend input validation.
- Status codes do not reflect real-world API behavior.
- Bug reports should NOT be created based on JSONPlaceholder behavior.

---

## Mitigation Strategy

To validate real API behavior, additional testing was performed using:

- DummyJSON API — which enforces authentication and input validation.

This ensured realistic testing of:

- 4xx error handling
- authentication flows
- backend validation logic
