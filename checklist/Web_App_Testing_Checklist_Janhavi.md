# Web App Testing Checklist
Author: Janhavi Morajkar
Version: 1.0
Last Updated: 11th March 2026

## 1. Functional Testing
- Every button performs the action its label describes
- Every form submits correctly with valid input
- Dropdown selections produce correct result
- Mandatory fields block submission when empty
- Success messages appear after completed actions
- Date fields should not accept future dates
- Mobile number fields should not accept wrong digit count
- Address field should accept valid punctuation like commas and periods
- Back button should not allow form resubmission

## 2. UI / Visual Testing
- All text is readable — no truncation or overflow
- No broken images on any page
- Layout does not break when browser is resized
- Page title in browser tab is correct on every page
- Placeholder text is present and correctly worded 
- UI elements are properly aligned on all pages

## 3. Form Testing
- Submit with all required fields empty
- Submit with only some fields filled
- Enter special characters in text fields
- Enter script tag in any field
- Enter maximum character limit then one character over
- Enter spaces only in text fields
- Enter numbers in text-only fields
- Enter letters in number-only fields
- Test future dates in date fields
- Enter invalid date like 31/02/2000
- Mobile number field should not accept less or more than 10 digits

## 4. Navigation Testing
- Every menu/sidebar item opens the correct page
- Browser Back button works correctly after each action
- No 404 errors on any internal link
- Deep link URL in new tab opens the correct page
- Logo/home button returns to correct landing page
- Navigation links should be properly aligned and visible on all pages

## 5. Error Handling
- Invalid input shows a clear specific error message
- Error messages appear next to the relevant field
- Unknown URL shows a proper 404 page
- Error messages do not show stack traces or database errors
- Error messages should be in simple language — not technical jargon
- Error messages should be specific enough for the user to understand and fix the mistake

## 6. Cross-Browser Testing

- Core flows tested on Chrome
- Core flows tested on Firefox
- Core flows tested on Edge
- Any visual differences documented
- Any behavioural differences documented
- Core flows tested on Linux OS 
- to check platform compatibility

## 7. Security Basics

- Protected page URL accessed directly without login — should redirect to login
- After logout, Back button should not show protected content
- Password field should mask characters
- Sensitive data should not be visible in URL bar
- Script injection in text fields should not execute
- Account numbers should be masked in format XXXX1234 — never shown in full on screen
- Sensitive account details should require re-verification before displaying (e.g. biometric or password confirmation)

## 8. Usability

- Main action on each page is immediately obvious
- Confirmation messages shown after saves and deletes
- Tab key moves through form field in logical order
- New user can complete main task without a manual
- App should show a loading indicator when an action is being processed
- App should ask for confirmation before deleting any record
- All buttons and fields should have clear labels so user knows what to do next
## My Personal Additions (from real testing experience)

- Future dates should not be accepted in date of birth fields
- Address fields should accept valid punctuation like commas and periods
- Mobile number fields should not accept less or more than 10 digits
- Back button should not allow form resubmission

