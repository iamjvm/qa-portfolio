================================================
EXPLORATORY TEST SESSION — 01
================================================
Session Charter: Explore Guru99 Bank 
for undiscovered bugs and edge cases

Tester: Janhavi Morajkar
Date: 10th March 2026
Start Time: 11:50
Time Box: 80 minutes
App URL: https://demo.guru99.com/V4/
================================================

--- SESSION NOTES ---

[11:54] Test 1 — New Customer empty form
What I did: Clicked New Customer, clicked Submit with all fields empty
Expected: Validation errors on all fields
Actual: the error shows “please fill all fields”
Bug? No

[11:57] Test 2 — Numbers in Customer Name
What I did: Entered "12345" in Customer Name field
Expected: Only alphabets allowed
Actual: error shows “numbers are not allowed”
Bug? No

[11:59] Test 3 — Special characters in Name
What I did: Entered "@#$%" in Customer Name field
Expected: Validation error shown
Actual: error shows “Special characters are not allowed”
Bug? No
[12:02]Test 4 – In customer name field mixing of letters & numbers
What I did: Entered “John123” in Customer name field
Expected: Validation Error shown
Actual: error shows “numbers are not allowed”
Bug? No

[12:05]Test 5 – In DOB enter a future date
What I did: Entered “01/01/2050” in DOB field
Expected: Validation Error shown
Actual: It accepts it & no error shown
Bug? Yes

[12:08]Test 6 – In Customer name field entered only spaces
What I did: Entered spaces in customer name field
Expected: error msg like only spaces allowed or character needed
Actual: error shows “First character can not have space”
Bug? No

[12:10]Test 7 – Leave Customer field empty and fill everything & submit
What I did: Filled all the fields except customer name field & submit
Expected: Validation error shows
Actual: the error shows “please fill all fields”
Bug? No

[12:13]Test 8 – In PIN field entered letters
What I did: In PIN field, Entered “abcd”
Expected: Validation error shown
Actual: Error shows “Characters are not allowed”
Bug? No



[12:19]Test 9 – Entered special characters such as  “, . ;” in address field
What I did: Entered a address “Near, D Mart Rd, next to Parikh Peninsula Park,Y K Nagar”
Expected: Should accept it
Actual: Error shows “Special characters are not allowed”
Bug? Yes

[12:22]Test 10 – Enter a mobile number more than 10 numbers or less than 10 numbers
What I did: Entered “1234567890” or “23564”
Expected: only 10 digits allowed or Validation error
Actual: It accepts it even if there are more numbers
Bug? Yes

[12:26]Test 11 – Fund Transfer
What I did: Entered an non existing account number
Expected: Number doesn’t exists or put a correct number
Actual: Error shows “account number doesn’t exists”
Bug? No

[12:35] Test — Back Button after form submission
What I did: Submitted a form then clicked browser Back button
Expected: Should go back safely without resubmitting
Actual: Browser asks to resubmit 
the form again
Bug? YES








================================================
SESSION SUMMARY
================================================
Total Time: ~45 minutes
Areas Explored: 
- New Customer form
- Fund Transfer
- Navigation/Back button

Bugs Found: 4
1. Future date accepted in DOB field
2. Address field rejects valid special characters (comma, period)
3. Mobile number accepts less/more than 10 digits
4. Back button allows form resubmission

Areas Needing More Testing: 
- Withdrawal with existing account
- Delete Customer behavior
- Edit Customer validation

One Thing That Surprised Me: 
The mobile number field accepting wrong digit counts and the address field rejecting valid punctuation like commas and periods surprised me the most these are basic validations that a banking app should never miss!
================================================

