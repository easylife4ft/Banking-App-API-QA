
5. Commit

6. **Create second file:** `bug-reports/bug-02-no-auth-on-balance.md`
Paste:

```markdown
# Bug 02: Balance Endpoint Accessible Without Token

**Severity:** Critical
**Priority:** Critical

**Steps:**
1. Send GET /account/balance WITHOUT Authorization header
2. Observe response

**Expected:** 401 Unauthorized

**Actual:** 200 OK with balance data exposed

**Impact:** Security breach, data leak.
