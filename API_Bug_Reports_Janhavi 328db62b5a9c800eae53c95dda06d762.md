# API_Bug_Reports_Janhavi

# API Bug Reports — JSONPlaceholder

**Tester:** Janhavi Morajkar
**Date:** 17th March 2026
**Tool:** Postman
**API:** [https://jsonplaceholder.typicode.com](https://jsonplaceholder.typicode.com/)

---

# Bug Report — API-BUG-001

**Title:** POST create user accepts missing required fields
**Reported By:** Janhavi Morajkar
**Date:** 17th March 2026
**Severity:** Major
**Priority:** High

## Environment

- Tool: Postman
- API: [https://jsonplaceholder.typicode.com](https://jsonplaceholder.typicode.com/)
- Endpoint: /users
- Method: POST

## Steps to Reproduce

1. Open Postman
2. Create a POST request to {{base_url}}/users
3. Set Body to raw JSON: {"name": "Janhavi Morajkar"}
4. Click Send

## Expected Result

Status 400 Bad Request — missing required fields
error message explaining which fields are required

## Actual Result

Status 201 Created — user created successfully
with only name field — no validation error shown

## Evidence

Request Body: {"name": "Janhavi Morajkar"}
Response: {"name": "Janhavi Morajkar", "id": 11}

## Impact

In a real production API this would allow invalid
incomplete user records to be created in the database.
Username and email are critical fields for user
identification and communication — missing them
creates data integrity issues.

---

# Bug Report — API-BUG-002

**Title:** POST create post returns 200 instead of 201
**Reported By:** Janhavi Morajkar
**Date:** 17th March 2026
**Severity:** Minor
**Priority:** Low

## Environment

- Tool: Postman
- API: [https://jsonplaceholder.typicode.com](https://jsonplaceholder.typicode.com/)
- Endpoint: /posts
- Method: POST

## Steps to Reproduce

1. Open Postman
2. Create a POST request to {{base_url}}/posts
3. Set Body to raw JSON:
{"title": "Test Post", "body": "Test body", "userId": 1}
4. Click Send

## Expected Result

Status 201 Created — correct HTTP status for
successful resource creation

## Actual Result

Status 200 OK — incorrect status code returned
200 means success but not specifically creation

## Evidence

Request Body: {"title": "Test Post", "body": "Test body", "userId": 1}
Response Status: 200 OK

## Impact

In a real production API returning wrong status codes
causes confusion for frontend developers and other
API consumers who rely on 201 to confirm a new
resource was created. This is an API contract violation.