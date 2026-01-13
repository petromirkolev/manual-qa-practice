# JSONplaceholder Test Execution Log

## Environment

- OS: macOS 15.7.1
- Tool: Postman
- URL: https://jsonplaceholder.typicode.com/

## Execution Date

- 2025-17-12

## Test Results

**Test Case ID**: TC-JSP-001

**Description**: Get all posts

**Result**: PASS

**Notes**: Response code 200 OK. List of all posts.

---

**Test Case ID**: TC-JSP-002

**Description**: Get one post

**Result**: PASS

**Notes**: Response code 200 OK. Body - one post object.

---

**Test Case ID**: TC-JSP-003

**Description**: Get non-existing post

**Result**: PASS

**Notes**: Response code 404 Not Found. Body - empty object.

---

**Test Case ID**: TC-JSP-POST-001

**Description**: Happy path create post

**Result**: PASS

**Notes**: Response code 201 Created. Response echoes body/title/usedId; id present.

---

**Test Case ID**: TC-JSP-POST-002

**Description**: Missing required field

**Result**: PASS

**Expected Result includes**:

- title === "hello"
- body === "world"
- userId === 1
- id exists and is numeric

**Notes**: Response code 201 Created. Response echoes body/title/usedId; id present.

---

**Test Case ID**: TC-JSP-POST-003

**Description**: Wrong data type

**Result**: PASS

**Notes**: Response code 201 Created. Response echoes body/title/usedId; id present.

---
