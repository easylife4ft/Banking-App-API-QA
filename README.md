# Banking-App-API-QA
Testing portfolio_ found 2 bug 14 tests,  postman

Overview
Manual API testing for a Banking Application using Postman. Focused on functional testing, negative testing, and validation testing to ensure financial data integrity.

Tools Used
- Postman / Postman Runner
- JSONPlaceholder as mock Banking API
- GitHub for documentation

Test Coverage
Total: 11 Test Scenarios | 14 Test Assertions*
Endpoint	Scenario	Type	Status Code
### Screenshots
![Run Results 1](run-results-01.png)
![Run Results 2](run-results-02.png)
1	GET /users	Get all users	Positive	200
2	GET /users	Get all users (Regression)	Positive	200
3	POST /users	Create valid user	Positive	201
4	POST /users	**BUG-001: Create user without email**	Negative	400 Expected / 201 Actual
5	GET /users/1	Get single user	Positive	200
6	GET /posts?userId=1	Get user transactions	Positive	200
7	POST /posts	Create valid transaction	Positive	201
8	POST /posts	Create second transaction	Positive	201
9	POST /users/1	**BUG-003: Insufficient funds check**	Negative	400 Expected / 201 Actual
10	PUT /users/1	Update user	Positive	200
11	GET /users/1	Verify update (2 assertions)	Positive	200
Execution Result
- *Date:* Nov 4, 2026 - 08:07 AM
- *Duration:* 7s 508ms
- *Scenarios:* 11
- *Assertions:* 14
- *Passed:* 12
- *Failed:* 2 (Documented as Bugs)
- *Errors:* 0
- *Avg Response Time:* 375 ms
- *Evidence:* Screenshots attached

🐞 Bugs Found

*BUG-001: Missing Email Validation Bypass*
- Severity: High
- Repro: POST /users without email field
- Expected: 400 Bad Request
- Actual: 201 Created — Invalid user created
- Test Result: FAIL

*BUG-003: Insufficient Funds Validation Missing*
- Severity: Critical
- Repro: POST /users/1 with insufficient funds
- Expected: 400 Bad Request
- Actual: 201 Created — Transaction allowed
- Impact: Financial risk

Why This Matters
- 0 Runner Errors — Clean execution
- Proved ability to write both positive and negative tests
- Found 2 critical business logic bugs

How to Run
1. Import collection to Postman
2. Run collection: Run Banking App API
3. Result: 11 scenarios, 14 assertions, 12 pass, 2 fail (bugs)

---
*Tester:* Abdulfatai - QA Engineer
*Link:* Postman Runner Results — 7.5s, 375ms avg


