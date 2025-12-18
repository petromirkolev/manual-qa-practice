**ID**: TC-DJA-001

**Title**: GET current user (authorized)

**Method:** GET

**Endpoint:** https://dummyjson.com/auth/me

**Preconditions:** API is available.

**Test data**:

- Headers: Authentication: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwidXNlcm5hbWUiOiJlbWlseXMiLCJlbWFpbCI6ImVtaWx5LmpvaG5zb25AeC5kdW1teWpzb24uY29tIiwiZmlyc3ROYW1lIjoiRW1pbHkiLCJsYXN0TmFtZSI6IkpvaG5zb24iLCJnZW5kZXIiOiJmZW1hbGUiLCJpbWFnZSI6Imh0dHBzOi8vZHVtbXlqc29uLmNvbS9pY29uL2VtaWx5cy8xMjgiLCJpYXQiOjE3NjYwNDc0MDksImV4cCI6MTc2NjA1MTAwOX0.DscXhOBwReBCOtinIrsneSaTvnHi8q2hSz70M7Ayx0I

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

**Endpoint:** https://dummyjson.com/auth/me

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

**Endpoint:** https://dummyjson.com/auth/me

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
