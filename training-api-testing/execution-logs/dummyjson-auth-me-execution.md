# DummyJSON Test Execution Log

## Environment

- OS: macOS 15.7.1
- Tool: Postman
- URL: https://dummyjson.com/auth/me

## Execution Date

- 2025-18-12

## Test Results

**Test Case ID**: TC-DJA-001

**Description**: GET current user (authorized)

**Result**: PASS

**Notes**:

- Status: 200 OK
- Body: User object: id: number; username: string; etc.

---

**Test Case ID**: TC-DJA-002

**Description**: GET current user (missing token)

**Result**: PASS

**Notes**:

- Status: 401 Unauthorized
- Body: Contains error message "Access Token is required".

---

**Test Case ID**: TC-DJA-003

**Description**: GET current user (invalid token)

**Result**: PASS

**Notes**:

- Status: 401 Unauthorized
- Body: Contains error message "Invalid token".

---
