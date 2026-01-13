**ID**: TC-DJ-001

**Title**: Login with valid credentials

**Method:** POST

**Endpoint:** https://dummyjson.com/auth/login

**Preconditions:** API is available.

**Test data**:

- Headers: Content-Type: application/json
- Body:
  {
  "username": "emilys",
  "password": "emilyspass"
  }

**Steps**:

1. Open Postman.
2. Submit a POST request to endpoint with test data.

**Expected result**:

- Status: 200 OK
- Body: Contains accessToken and refreshToken (and user fields). Token fields present.

---

**ID**: TC-DJ-002

**Title**: Login with missing password

**Method:** POST

**Endpoint:** https://dummyjson.com/auth/login

**Preconditions:** API is available.

**Test data**:

- Headers: Content-Type: application/json
- Body:
  {
  "username": "emilys"
  }

**Steps**:

1. Open Postman.
2. Submit a POST request to endpoint with test data.

**Expected result**:

- Status: 400 Bad Request
- Body: Contains error message "Username and password required".

---

**ID**: TC-DJ-003

**Title**: Login with invalid password

**Method:** POST

**Endpoint:** https://dummyjson.com/auth/login

**Preconditions:** API is available.

**Test data**:

- Headers: Content-Type: application/json
- Body:
  {
  "username": "emilys",
  "password": "1234"
  }

**Steps**:

1. Open Postman.
2. Submit a POST request to endpoint with test data.

**Expected result**:

- Status: 400 Bad Request
- Body: Contains error message "Invalid credentials".

---
