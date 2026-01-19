**ID**: TC-DJA-001

**Title**: GET current user (authorized)

**Method:** GET

**Endpoint:** /auth/me

**Preconditions:**

- API is available.
- {{accessToken}} is obtained from TC-DJ-001 login response

**Test data**:

- Headers: Authentication: Bearer {{accessToken}}

**Steps**:

1. Open Postman.
2. Submit a GET request to endpoint with test data.

**Expected result**:

- Status: 200 OK
- Body: User object (id/username/etc.)

---

**ID**: TC-DJA-002

**Title**: GET current user (missing token)

**Method:** GET

**Endpoint:** /auth/me

**Preconditions:** API is available.

**Steps**:

1. Open Postman.
2. Submit a GET request to endpoint.

**Expected result**:

- Status: 401 Unauthorized
- Body: Contains error message "Access Token is required".

---

**ID**: TC-DJA-003

**Title**: GET current user (invalid token)

**Method:** GET

**Endpoint:** /auth/me

**Preconditions:** API is available.

**Test data**:

- Headers: Authentication: Bearer abc

**Steps**:

1. Open Postman.
2. Submit a GET request to endpoint with test data.

**Expected result**:

- Status: 401 Unauthorized
- Body: Contains error message "Invalid token".

---
