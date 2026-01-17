**ID**: TC-JSP-001
**Title**: GET All posts
**Method:** GET
**Endpoint:** /posts
**Preconditions:** API is available.
**Steps**:

1. Open Postman.
2. Submit a GET request to endpoint.

**Expected result**:

- Status: 200 OK
- Body: array of posts

---

**ID**: TC-JSP-002
**Title**: GET One post
**Method:** GET
**Endpoint:** /posts/1
**Preconditions:** API is available.
**Steps**:

1. Open Postman.
2. Submit a GET request to endpoint.

**Expected result**:

- Status: 200 OK
- Body: one object

---

**ID**: TC-JSP-003
**Title**: GET One non-existing post
**Method:** GET
**Endpoint:** /posts/9999
**Preconditions:** API is available.
**Steps**:

1. Open Postman.
2. Submit a GET request to endpoint.

**Expected result**:

- Status: 404 Not Found
- Body: empty object

---

**ID**: TC-JSP-POST-001
**Title**: Happy path create post
**Method:** POST
**Endpoint:** /posts
**Preconditions:** API is available.
**Steps**:

1. Open Postman.
2. Submit a POST request to endpoint with the following parameters:

- Headers: Content-Type: application/json
- Body:
  {
  "title": "hello",
  "body": "world",
  "userId": 1
  }

**Expected result**:

- Status: 201 Created
- Body: Object contains title, body.
- Body: Oblect includes ID (number).

---

**ID**: TC-JSP-POST-002
**Title**: Missing required field
**Method:** POST
**Endpoint:** /posts
**Preconditions:** API is available.
**Steps**:

1. Open Postman.
2. Submit a POST request to endpoint with the following parameters:

- Headers: Content-Type: application/json
- Body:
  {
  "body": "world",
  "userId": 1
  }

**Expected result (real API)**:

- 400/422 with validation error details.

**Expected result (JSONPlaceholder mock)**:

- 201 Created (no validation enforced), response echoes payload + id.

---

**ID**: TC-JSP-POST-003
**Title**: Wrong data type
**Method:** POST
**Endpoint:** /posts
**Preconditions:** API is available.
**Steps**:

1. Open Postman.
2. Submit a POST request to endpoint with the following parameters:

- Headers: Content-Type: application/json
- Body:
  {
  "title": "hello",
  "body": "world",
  "userId": "abc"
  }

**Expected result (real API)**:

- 400/422 with validation error details.

**Expected result (JSONPlaceholder mock)**:

- 201 Created (no validation enforced), response echoes payload + id.

---
