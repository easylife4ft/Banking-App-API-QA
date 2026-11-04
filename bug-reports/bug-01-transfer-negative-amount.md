# Bug 01: API Allows Transfer of Negative Amount

**Severity:** High
**Priority:** High
**Environment:** Banking API v1, Postman

**Steps to Reproduce:**
1. Login with valid user
2. Send POST /transfer with body:
```json
{
  "toAccount": "123456",
  "amount": -5000
}
