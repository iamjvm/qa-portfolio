# ReqRes_Full_TestSuite_Janhavi

# Full API Test Suite — JSONPlaceholder

**Tester:** Janhavi Morajkar
**Date:** 20th March 2026
**Tool:** Postman
**Base URL:** [https://jsonplaceholder.typicode.com](https://jsonplaceholder.typicode.com/)

---

## Layer 1 — Happy Path (6 test cases)

**TC_API_016**
Title: GET all users returns 200 and 10 users
Method: GET
Endpoint: {{base_url}}/users
Expected Status: 200
Expected Response: Array of 10 user objects
Pass/Fail: ✅ PASS

**TC_API_017**
Title: GET single user with valid ID returns correct data
Method: GET
Endpoint: {{base_url}}/users/1
Expected Status: 200
Expected Response: User object with id, name, username, email
Pass/Fail: ✅ PASS

**TC_API_018**
Title: POST create user with all fields returns 201
Method: POST
Endpoint: {{base_url}}/users
Request Body: {"name": "Janhavi", "username": "iamjvm", "email": "[janhaviimorajkar@gmail.com](mailto:janhaviimorajkar@gmail.com)"}
Expected Status: 201
Expected Response: Created user with auto-generated id
Pass/Fail: ✅ PASS

**TC_API_019**
Title: PUT update user with valid data returns 200
Method: PUT
Endpoint: {{base_url}}/users/1
Request Body: {"name": "Janhavi Updated", "email": "[updated@gmail.com](mailto:updated@gmail.com)"}
Expected Status: 200
Expected Response: Updated user object
Pass/Fail: ✅ PASS

**TC_API_020**
Title: DELETE user with valid ID returns 200
Method: DELETE
Endpoint: {{base_url}}/users/1
Expected Status: 200
Expected Response: Empty object {}
Pass/Fail: ✅ PASS

**TC_API_021**
Title: GET all posts returns 200 and 100 posts
Method: GET
Endpoint: {{base_url}}/posts
Expected Status: 200
Expected Response: Array of 100 post objects
Pass/Fail: ✅ PASS

---

## Layer 2 — Negative Testing (7 test cases)

**TC_API_022**
Title: GET user with non-existent ID returns 404
Method: GET
Endpoint: {{base_url}}/users/999
Expected Status: 404
Expected Response: Empty object {}
Pass/Fail: ✅ PASS

**TC_API_023**
Title: GET user with string ID returns 404
Method: GET
Endpoint: {{base_url}}/users/abc
Expected Status: 404
Expected Response: Empty object {}
Pass/Fail: ✅ PASS

**TC_API_024**
Title: POST create user with missing fields accepts request
Method: POST
Endpoint: {{base_url}}/users
Request Body: {"name": "Janhavi"}
Expected Status: 400
Expected Response: Error — missing required fields
Pass/Fail: ❌ FAIL — returns 201, no validation

**TC_API_025**
Title: POST create user with empty body
Method: POST
Endpoint: {{base_url}}/users
Request Body: {}
Expected Status: 400
Expected Response: Error — required fields missing
Pass/Fail: ❌ FAIL — returns 201, accepts empty body

**TC_API_026**
Title: PUT update non-existent user
Method: PUT
Endpoint: {{base_url}}/users/999
Request Body: {"name": "Test"}
Expected Status: 404
Expected Response: Error — user not found
Pass/Fail: ❌ FAIL — returns 500 Internal Server Error
instead of 404. Server crashes when updating non-existent user.
Severity upgraded to Major — server should handle gracefully.

**TC_API_027**
Title: DELETE non-existent user
Method: DELETE
Endpoint: {{base_url}}/users/999
Expected Status: 404
Expected Response: Error — user not found
Pass/Fail: ❌ FAIL — returns 200

**TC_API_028**
Title: GET user with negative ID
Method: GET
Endpoint: {{base_url}}/users/-1
Expected Status: 404
Expected Response: Empty object {}
Pass/Fail: ✅ PASS

---

## Layer 3 — Boundary Testing (4 test cases)

**TC_API_029**
Title: GET user with ID 0 — boundary below minimum
Method: GET
Endpoint: {{base_url}}/users/0
Expected Status: 404
Expected Response: Empty object {}
Pass/Fail: ✅ PASS

**TC_API_030**
Title: GET user with ID 10 — maximum valid user
Method: GET
Endpoint: {{base_url}}/users/10
Expected Status: 200
Expected Response: Valid user object
Pass/Fail: ✅ PASS

**TC_API_031**
Title: GET user with ID 11 — just above maximum
Method: GET
Endpoint: {{base_url}}/users/11
Expected Status: 404
Expected Response: Empty object {}
Pass/Fail: ✅ PASS

**TC_API_032**
Title: POST create user with very long name — 200+ characters
Method: POST
Endpoint: {{base_url}}/users
Request Body: {"name": "JanhaviJanhaviJanhaviJanhaviJanhaviJanhaviJanhaviJanhaviJanhaviJanhaviJanhaviJanhaviJanhaviJanhaviJanhaviJanhaviJanhaviJanhaviJanhaviJanhavi", "username": "iamjvm", "email": "[test@test.com](mailto:test@test.com)"}
Expected Status: 400
Expected Response: Error — name too long
Pass/Fail: ❌ FAIL — accepts very long name

---

## Layer 4 — Security Basics (3 test cases)

**TC_API_033**
Title: GET users without authentication header
Method: GET
Endpoint: {{base_url}}/users
Expected Status: 200
Expected Response: Returns data — API is public, no auth required
Pass/Fail: ✅ PASS — observation: no authentication required

**TC_API_034**
Title: Response does not expose sensitive server information
Method: GET
Endpoint: {{base_url}}/users/1
Expected Status: 200
Expected Response: No server version, no stack trace in response
Pass/Fail: ✅ PASS

**TC_API_035**
Title: Error response does not reveal internal system details
Method: GET
Endpoint: {{base_url}}/users/999
Expected Status: 404
Expected Response: Simple empty response — no internal error details
Pass/Fail: ✅ PASS

---

## Execution Summary

| Layer | Total | Pass | Fail |
| --- | --- | --- | --- |
| Happy Path | 6 | 6 | 0 |
| Negative Testing | 7 | 3 | 4 |
| Boundary Testing | 4 | 3 | 1 |
| Security Basics | 3 | 3 | 0 |
| Total | 20 | 15 | 5 |

Pass Rate: 75%