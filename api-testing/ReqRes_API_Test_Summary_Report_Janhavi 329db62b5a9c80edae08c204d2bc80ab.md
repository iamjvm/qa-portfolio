# ReqRes_API_Test_Summary_Report_Janhavi

# API Test Summary Report — JSONPlaceholder Practice API

**Version:** 1.0
**Prepared By:** Janhavi Morajkar
**Date:** 20th March 2026
**Project:** API Testing Portfolio Project 3
**API Under Test:** [https://jsonplaceholder.typicode.com](https://jsonplaceholder.typicode.com/)**Tool Used:** Postman

---

## 1. Executive Summary

JSONPlaceholder public REST API was tested on 20th March 2026
as part of API Testing Portfolio Project 3. Endpoints tested
covered GET, POST, PUT and DELETE methods across the users
and posts resources.

A total of 35 test cases were executed across 4 testing layers —
happy path, negative testing, boundary testing and security basics.
15 test cases passed and 5 failed giving an overall pass rate of 75%.

5 bugs and observations were found during testing. The most notable
finding was a 500 Internal Server Error returned when attempting
to update a non-existent user — indicating the server crashes
instead of handling the error gracefully.

Overall JSONPlaceholder is a stable and well-structured practice
API. Core happy path flows work correctly and response times are
consistently under 700ms. However the API lacks input validation
on POST requests and does not handle edge cases gracefully in
some PUT operations.

## 2. Scope

### Endpoints Tested:

- GET /users — list all users
- GET /users/:id — single user by ID
- POST /users — create new user
- PUT /users/:id — update existing user
- DELETE /users/:id — delete user
- GET /posts — list all posts
- GET /posts/:id — single post by ID
- GET /posts?userId=1 — filter posts by user

### Testing Layers Covered:

- Happy Path
- Negative Testing
- Boundary Testing
- Security Basics

### Out of Scope:

- Authentication and OAuth testing
- Performance and load testing
- PATCH endpoint
- Comments and Albums endpoints

## 3. Test Execution Results

| Metric | Count |
| --- | --- |
| Total Test Cases | 35 |
| Executed | 35 |
| PASS | 28 |
| FAIL | 7 |
| Pass Rate | 80% |

### By Layer:

| Layer | Total | Pass | Fail |
| --- | --- | --- | --- |
| Happy Path | 6 | 6 | 0 |
| Negative Testing | 7 | 3 | 4 |
| Boundary Testing | 4 | 3 | 1 |
| Security Basics | 3 | 3 | 0 |
| Day 12 Cases | 15 | 13 | 2 |
| Total | 35 | 28 | 7 |

## 4. Findings Summary

| ID | Title | Endpoint | Type | Severity |
| --- | --- | --- | --- | --- |
| API-BUG-001 | POST create user accepts missing required fields | POST /users | Bug | Major |
| API-BUG-002 | POST create user accepts empty request body | POST /users | Bug | Major |
| API-BUG-003 | PUT update non-existent user returns 500 instead of 404 | PUT /users/999 | Bug | Major |
| API-BUG-004 | DELETE non-existent user returns 200 instead of 404 | DELETE /users/999 | Bug | Minor |
| API-BUG-005 | POST create user accepts very long name with no validation | POST /users | Bug | Minor |

### Finding Types:

- **Bug** — API behaved incorrectly — wrong status code, crash, wrong data
- **Observation** — API technically works but behaviour is worth flagging

## 5. Security Observations

JSONPlaceholder is a public practice API with no authentication
required. All endpoints are openly accessible without any token
or credentials — this is expected for a practice API but would
be a Critical security issue in a real production system.

Error responses are clean and do not expose internal system
details such as stack traces or server configuration. However
the 500 Internal Server Error on PUT /users/999 did expose
internal server file paths and Node.js error details in the
response body — this is a security concern as it reveals
implementation details to potential attackers.

No sensitive user data such as passwords or payment information
was exposed in any response. All user objects returned only
id, name, username, email, address and company fields.

## 6. Quality Assessment

JSONPlaceholder performs well on its core functionality. All
happy path flows work correctly — GET requests return accurate
data, POST creates records with auto-generated IDs, PUT updates
return correct timestamps and DELETE responds consistently.
Response times were excellent throughout, averaging under 700ms
across all requests.

However if this were a real production API several issues would
need to be addressed before release. The most critical concern
is the lack of input validation on POST requests — the API
accepts missing fields, empty bodies and extremely long strings
without any error. This would lead to corrupt or incomplete
records in a production database.

The 500 Internal Server Error on PUT to a non-existent resource
is also concerning — a well designed API should return a clean
404 with a descriptive error message instead of crashing and
exposing internal file paths.

Overall JSONPlaceholder is good quality for a practice API and
serves its purpose well. With proper input validation and better
error handling on edge cases it would meet production standards.

## 7. Recommendations

- POST /users should validate required fields and return 400
with a descriptive error message when name, username or
email are missing
- POST /users should reject empty request bodies with 400
instead of creating empty records
- PUT /users/:id should return 404 with a clean error message
when the user does not exist instead of returning 500
- DELETE /users/:id should return 404 when the resource does
not exist instead of returning 200
- Input length validation should be added to name and other
string fields to prevent extremely long values being accepted
- The 500 error response should not expose internal file paths
and Node.js stack traces — these should be logged server side
only and never returned to the client

## 8. Chained Flow Validation

| Step | Request | Status | Variables Passed |
| --- | --- | --- | --- |
| 1 | POST /users — Register User | 201 Created | user_id captured ✅ |
| 2 | GET /users/1 — Get User | 200 OK | user_email captured ✅ |
| 3 | PUT /users/{{user_id}} — Update User | 200 OK | Updated correctly ✅ |
| 4 | DELETE /users/{{user_id}} — Delete User | 200 OK | Chain completed ✅ |

All 4 steps in the chained flow passed successfully. Collection
variables were captured and passed correctly between requests.
The full end-to-end user journey — Register, Get, Update, Delete
— completed without any errors in 1.6 seconds total.

## 9. Sign-off

| Role | Name | Decision | Date |
| --- | --- | --- | --- |
| QA Tester | Janhavi Morajkar | Stable for practice purposes — needs fixes before production use | 20th March 2026 |

---

## Summary

JSONPlaceholder API testing is complete. The API is stable for
practice and learning purposes. Core flows work correctly and
response times are excellent. However 5 bugs were found related
to missing input validation and poor error handling on edge cases.

These findings have been documented in formal bug reports and
recommendations have been provided. The API is not recommended
for production use without addressing the Major bugs identified
in this report.