

EXPLORATORY TEST SESSION — 02

Charter: Explore New Customer + Edit Customer using Web App 
Testing Checklist
Tester: Janhavi Morajkar
Date: 11th March 2026
App: https://demo.guru99.com/
Start Time: [17:08]
Time Box: 90 minutes

[17:12] Test 1 — Script injection in Customer Name field
What I did: Entered <script>alert('xss')</script>
Expected: Should block script execution
Actual: Error shows "Special characters are not allowed"
Bug? No — validation working correctly
Security: PASS ?

[17:15] Test 2 — Script injection in Address field
What I did: Entered script tag in Address field
Expected: Should block it
Actual: "Special characters are not allowed"
Bug? No — Security PASS ?

[17:17] Test 3 — Invalid date 31/02/2000
What I did: Entered 31/02/2000 in DOB field
Expected: Should reject invalid date
Actual: Browser shows "Please enter a valid value" error
Bug? No — Validation working ?

[17:20] Test 4 — Single character name
What I did: Entered "A" in Customer Name field
Expected: Should require minimum character length
Actual: It ACCEPTS single character!
Bug? YES ?? No minimum length validation on Customer Name field

[17:22] Test 5 — Maximum character limit in Customer Name
What I did: Entered 200+ characters in Customer Name field
Expected: Should have a maximum character limit with validation error
Actual: Field accepts 200+ characters
Bug? YES ?? No maximum length validation on Customer Name field

[17:25] Test 6 — Edit Customer with non-existing ID
What I did: Entered "99999" in Customer ID field
Expected: Error "Customer does not exist"
Actual: Shows error but accepts 5 digit input
Bug? Partial ??App accepts any 5 digit number even if customer doesn't exist in the system

[17:30] Test 7 — Edit Customer field restrictions
What I did: Tried to edit Customer Name, Gender and DOB fields
Expected: All fields should be editable in Edit Customer form
Actual: Customer Name, Gender and DOB fields are locked cannot be edited
Bug? YES ?? Core customer details cannot be modified after creation
Impact: If a customer's name is spelled wrong or DOB entered incorrectly  there is no way to fix it!
Severity: Major

[17:35] Test 8 — Navigation sidebar links
What I did: Clicked every item in the left sidebar
Expected: All links open correct pages
Actual: All links working correctly
Bug? No  Navigation PASS ?

[17:45] Test 9 — Back button after logout
What I did: Logged out then pressed browser Back button
Expected: Should redirect to login page
Actual: Previous page opens user can see protected content without being logged in!
Bug? YES ?? — Critical Security Bug!
Severity: Critical
Impact: Anyone can access a logged out user's banking data!

[17:50] Test 10 — Sensitive data in URL
What I did: Checked URL bar while using the app
Expected: No sensitive data in URL
Actual: No sensitive info visible
Bug? No Security PASS ?

[18:01] Test 11 — Password masking
What I did: Typed in Change Password
Expected: Characters shown as dots
Actual: Characters are masked correctly
Bug? No Security PASS ?














SESSION SUMMARY

Total Time: 90 minutes
Areas Explored: 
- New Customer form
- Edit Customer
- Navigation
- Security basics

Bugs Found: 4
1. Single character name accepted — Minor
2. 200+ characters accepted — Major
3. Name/Gender/DOB locked in edit — Major
4. Back button after logout shows protected content — Critical ??

New Checklist Items to Add:
- After logout back button should not show protected content
- Fields should have minimum and maximum character length validation
- All customer fields should be editable after creation

One Thing I Tested Today I Wouldn't Have Thought Of Before Day 7:
I wouldn't have thought that small validation gaps like accepting a single character name or no maximum length limit could lead to serious data quality issues in a real banking application.


