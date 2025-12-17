**ID**: TC-JSP-001

**Title**: GET All posts

**Method:** GET

**Endpoint:** https://jsonplaceholder.typicode.com/

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
