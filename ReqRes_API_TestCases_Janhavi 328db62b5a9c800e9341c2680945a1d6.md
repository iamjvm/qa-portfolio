# ReqRes_API_TestCases_Janhavi

# API Test Cases — JSONPlaceholder

**Tester:** Janhavi Morajkar
**Date:** 17th March 2026
**Tool:** Postman
**Base URL:** [https://jsonplaceholder.typicode.com](https://jsonplaceholder.typicode.com/)

---

## Test Cases

**TC_API_001**
Title: GET all users returns 200 and array of users
Method: GET
Endpoint: {{base_url}}/users
Request Body: N/A
Expected Status Code: 200
Expected Response: Array of 10 user objects each with id, name, username, email
Pass/Fail: ✅ PASS

**TC_API_002**
Title: GET single user with valid ID returns 200
Method: GET
Endpoint: {{base_url}}/users/1
Request Body: N/A
Expected Status Code: 200
Expected Response: Single user object with id, name, username, email
Pass/Fail: ✅ PASS

**TC_API_003**
Title: GET single user with invalid ID returns 404
Method: GET
Endpoint: {{base_url}}/users/999
Request Body: N/A
Expected Status Code: 404
Expected Response: Empty object {}
Pass/Fail: ✅ PASS

**TC_API_004**
Title: POST create user with all valid fields returns 201
Method: POST
Endpoint: {{base_url}}/users
Request Body: {"name": "Janhavi Morajkar", "username": "iamjvm", "email": "[janhaviimorajkar@gmail.com](mailto:janhaviimorajkar@gmail.com)"}
Expected Status Code: 201
Expected Response: Created user object with auto-generated id
Pass/Fail: ✅ PASS

**TC_API_005**
Title: POST create user with missing fields should return 400
Method: POST
Endpoint: {{base_url}}/users
Request Body: {"name": "Janhavi Morajkar"}
Expected Status Code: 400
Expected Response: Error message — missing required fields
Pass/Fail: ❌ FAIL — returned 201, user created without required fields

**TC_API_006**
Title: POST create user with empty body should return 400
Method: POST
Endpoint: {{base_url}}/users
Request Body: {}
Expected Status Code: 400
Expected Response: Error message — required fields missing
Pass/Fail: ❌ FAIL — API accepts empty body

**TC_API_007**
Title: PUT update post with valid data returns 200
Method: PUT
Endpoint: {{base_url}}/posts/1
Request Body: {"title": "Updated Title", "body": "Updated body content", "userId": 1}
Expected Status Code: 200
Expected Response: Updated post object with id and updated fields
Pass/Fail: ✅ PASS

**TC_API_008**
Title: DELETE post with valid ID returns 200
Method: DELETE
Endpoint: {{base_url}}/posts/1
Request Body: N/A
Expected Status Code: 200
Expected Response: Empty object {}
Pass/Fail: ✅ PASS

**TC_API_009**
Title: GET single post with valid ID returns 200
Method: GET
Endpoint: {{base_url}}/posts/1
Request Body: N/A
Expected Status Code: 200
Expected Response: Single post object with id, title, body, userId
Pass/Fail: ✅ PASS

**TC_API_010**
Title: GET posts by user ID returns 200 and filtered posts
Method: GET
Endpoint: {{base_url}}/posts?userId=1
Request Body: N/A
Expected Status Code: 200
Expected Response: Array of posts belonging to userId 1
Pass/Fail: ✅ PASS

**TC_API_011**
Title: GET single post with invalid ID returns 404
Method: GET
Endpoint: {{base_url}}/posts/999
Request Body: N/A
Expected Status Code: 404
Expected Response: Empty object {}
Pass/Fail: ✅ PASS

**TC_API_012**
Title: GET all posts returns 200 and array of 100 posts
Method: GET
Endpoint: {{base_url}}/posts
Request Body: N/A
Expected Status Code: 200
Expected Response: Array of 100 post objects
Pass/Fail: ✅ PASS

**TC_API_013**
Title: GET comments for a specific post returns 200
Method: GET
Endpoint: {{base_url}}/posts/1/comments
Request Body: N/A
Expected Status Code: 200
Expected Response: Array of comments for post 1
Pass/Fail: ✅ PASS

**TC_API_014**
Title: POST create post with valid data returns 201
Method: POST
Endpoint: {{base_url}}/posts
Request Body: {"title": "Test Post", "body": "Test body", "userId": 1}
Expected Status Code: 201
Expected Response: Created post with auto-generated id
Pass/Fail: ✅ PASS

**TC_API_015**
Title: GET all todos returns 200 and array of todos
Method: GET
Endpoint: {{base_url}}/todos
Request Body: N/A
Expected Status Code: 200
Expected Response: Array of 200 todo objects each with id, title, completed
Pass/Fail: ✅ PASS

---

## Execution Summary

Total: 15
PASS: 13
FAIL: 2
Pass Rate: 87%
Bugs Found: 2