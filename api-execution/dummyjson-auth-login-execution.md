# DummyJson Test Execution Log

## Environment

- OS: macOS 15.7.1
- Tool: Postman
- URL: https://dummyjson.com/auth/login

## Execution Date

- 2025-18-12

## Test Results

**Test Case ID**: TC-DJ-001

**Description**: Login with valid credentials

**Result**: PASS

**Notes**: Response code 200 OK. Body contains accessToken and refreshToken.

---

**Test Case ID**: TC-DJ-002

**Description**: Login with missing password

**Result**: PASS

**Notes**: Response code 400 Bad Request. Body contains error message "Username and password required".

---

**Test Case ID**: TC-DJ-003

**Description**: Login with invalid password

**Result**: PASS

**Notes**: Response code 400 Bad Request. Body contains error message "Invalid credentials".

---
