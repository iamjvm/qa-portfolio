# Retest_Log_Janhavi

# Retest Log - guru99 Bank Demo

**Tester:** Janhavi Morajkar
**Date:** 13th March 2026
**Environment:** Chrome (latest), Windows 11

---

## BUG-001

**Title:** Session not invalidated after logout back button restores session
**Original Steps Followed:** Yes
**Result:** ❌ FAIL
**Action in JIRA:** Reopened
**Comment added:** Retest Result: FAIL. Issue still reproducible.
Pressed back button after logout logged-in dashboard restored
without credentials. Reopening and returning to developer.

---

## BUG-002

**Title:** Special characters accepted in Address field
**Original Steps Followed:** Yes
**Result:** NOT A BUG
**Action in JIRA:** Closed  Invalid
**Comment added:** On retest, special characters are correctly rejected
in Address field. Original observation was incorrect.
Closing as Invalid not a real bug.

---

## BUG-003

**Title:** Mobile number field accepts less/more than 10 digits
**Original Steps Followed:** Yes
**Result:** ❌ FAIL
**Action in JIRA:** Reopened — keep Open
**Comment added:** Retest Result: FAIL. Issue still reproducible.
Mobile number field still accepts less than 10 digits.
Keeping open — returning to developer.

## BUG-004

**Title:** Future date accepted in Date of Birth field
**Original Steps Followed:** Yes
**Result:** ❌ FAIL
**Action in JIRA:** Keeping Open
**Comment added:** Retest Result: FAIL. Future date still accepted
in DOB field. Issue still reproducible. Keeping open.

## BUG-005

**Title:** Misleading error message for invalid Customer ID
**Original Steps Followed:** Yes
**Result:** ❌ FAIL
**Action in JIRA:** Keeping Open
**Comment added:** Retest Result: FAIL. Misleading error message
still displayed for invalid Customer ID. Keeping open.

## BUG-006

**Title:** Deposit page throws HTTP 500 Internal Server Error
**Original Steps Followed:** Yes
**Result:** ❌ FAIL
**Action in JIRA:** Keeping Open
**Comment added:** Retest Result: FAIL. HTTP 500 error still
occurring on valid deposit submission. Keeping open.

## BUG-007

**Title:** Form data lost on back navigation after server error
**Original Steps Followed:** Yes
**Result:** ❌ FAIL
**Action in JIRA:** Keeping Open
**Comment added:** Retest Result: FAIL. False validation message
still appears after back navigation following HTTP 500 error.
Keeping open.

## Retest Summary

Total Bugs Retested: 7
PASS: 0
FAIL: 6
Invalid/Closed: 1
Environment Issues: 0

## Regression Testing

### Area 1 — Login

Test 1: Login with valid credentials → Dashboard loads ✅ PASS
Test 2: Login with spaces before/after username → Character
limit prevents spaces from being entered ✅ PASS
Test 3: Browser refresh after login → Session stays active ✅ PASS

### Area 2 — Session/Direct URL Access

Test 4: Accessing protected URL directly after logout →
Page shows "File Not Found" — does not redirect to login page
⚠️ OBSERVATION — should ideally redirect to login page

### Area 3 — New Customer Surrounding Areas

Test 5: Edit Customer with valid ID → Page loads correctly ✅ PASS
Test 6: Delete Customer with active accounts → Shows error
"Customer could not be deleted!! First delete all accounts
of this customer then delete the customer" ✅ PASS
— Correct behaviour, app prevents deletion of customer
with active accounts

## Regression Summary

Total Regression Tests: 7
PASS: 6
FAIL: 0
Observations: 1 (Test 4 — File Not Found instead of redirect)
New Bugs Found: 0