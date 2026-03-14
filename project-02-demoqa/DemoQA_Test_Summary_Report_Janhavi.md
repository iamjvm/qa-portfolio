# DemoQA_Test_Summary_Report_Janhavi

# Test Summary Report — DemoQA Practice Application

**Version:** 1.0
**Author:** Janhavi Morajkar
**Date:** 14th March 2026
**Application:** [https://demoqa.com/](https://demoqa.com/)

## 1. Executive Summary

DemoQA practice application was tested on 13th and 14th March 2026 as part of Project 2 of the QA Engineer portfolio. Three modules were covered Text Box, Student Registration Form, and Buttons testing all core user flows, validation behaviour, and edge cases as a real user would interact with the application.

A total of 20 test cases were executed across two modules. 13 test cases passed and 7 failed, giving an overall pass rate of 65%. In addition, 5 bugs were discovered during exploratory testing, bringing
the total bugs found to 13 across both scripted and exploratory sessions.

The application is functional and the UI is clean, but several minor validation gaps reduce the overall quality. Key issues include missing validation on empty form submission, special characters and numbers accepted in name fields, and a PDF file accepted in a picture upload field. None of the bugs found are Critical severity, however they collectively indicate that input validation needs improvement.

Overall verdict: DemoQA is medium quality. The core flows work correctly but the lack of proper input validation across multiple fields brings the quality assessment down. The application is not
ready for a production environment without fixing the identified bugs.

## 2. Test Scope

### Modules Tested:

- Text Box (Elements module)
- Student Registration Form (Forms module)
- Buttons (Elements module)

### Testing Types Applied:

- Functional Testing
- Negative Testing
- Boundary Value Analysis
- Exploratory Testing

### Out of Scope:

- Interactions, Widgets, Book Store modules
- Performance and load testing
- Mobile testing
- Automation

## 3. Test Execution Results

| Metric | Count |
| --- | --- |
| Total Planned | 20 |
| Executed | 20 |
| PASS | 13 |
| FAIL | 7 |
| BLOCKED | 0 |
| Pass Rate | 65% |

### By Module:

| Module | Total | Pass | Fail | Blocked |
| --- | --- | --- | --- | --- |
| Text Box | 8 | 4 | 4 | 0 |
| Student Registration Form | 12 | 9 | 3 | 0 |

## 4. Bug Summary

### From Test Cases:

| Bug ID | Title | Module | Severity | Status |
| --- | --- | --- | --- | --- |
| BUG-TB-001 | Typo in output label — Permananet instead of Permanent Address | Text Box | Trivial | Open |
| BUG-TB-002 | Numbers accepted in Full Name field | Text Box | Minor | Open |
| BUG-TB-003 | No validation on empty form submission | Text Box | Major | Open |
| BUG-TB-004 | Whitespace accepted as valid input | Text Box | Minor | Open |
| BUG-TB-005 | Special characters accepted in Full Name | Text Box | Minor | Open |
| BUG-REG-001 | Future date accepted in Date of Birth field | Registration Form | Major | Open |
| BUG-REG-002 | PDF file accepted in picture upload field | Registration Form | Minor | Open |
| BUG-REG-003 | City dropdown not reset when State is changed | Registration Form | Minor | Open |

### From Exploratory Session:

| Bug ID | Title | Module | Severity | Status |
| --- | --- | --- | --- | --- |
| BUG-EX-001 | Whitespace accepted in Name and Address fields | Text Box | Minor | Open |
| BUG-EX-002 | Emoji accepted in Full Name field | Text Box | Minor | Open |
| BUG-EX-003 | Layout breaks on browser resize | Text Box | Minor | Open |
| BUG-EX-004 | Email and Picture show green tick when empty | Registration Form | Minor | Open |
| BUG-EX-005 | PDF accepted in picture upload field | Registration Form | Minor | Open |

### Bug Count by Severity:

| Severity | Count |
| --- | --- |
| Critical | 0 |
| Major | 2 |
| Minor | 10 |
| Trivial | 1 |
| Total | 13 |

## 5. Test Environment

| Parameter | Details |
| --- | --- |
| Browser | Chrome (latest) |
| OS | Windows 11 |
| Application URL | [https://demoqa.com/](https://demoqa.com/) |
| Test Dates | 13th and 14th March 2026 |
| Test Data | Manually created per test case |
| Bug Tracking Tool | JIRA — component: DemoQA-Project2 |

## 6. Quality Assessment

Overall the DemoQA application performed well across its core functionality. The Buttons module worked exactly as expected with all three click types single, double, and right click responding
correctly with appropriate messages.

The Student Registration Form was the strongest module tested. Compared to guru99 Bank Demo, the Registration Form showed noticeably better validation mobile number length is enforced, letters are rejected in the mobile field, and required fields are clearly marked. This level of validation was missing in guru99.

The Text Box module was the weakest area. It lacks basic input validation numbers, special characters, emoji, and whitespace are all accepted in the Full Name field without any error. Empty form submission also passes silently with no error message shown to the user.

The recurring theme across both modules is inconsistent validation. Specific gaps include future dates accepted in Date of Birth, PDF files accepted in a picture upload field, City dropdown not resetting when State is changed, and only 4 states available in the State dropdown which is unrealistic for a real application.

Despite these issues, no Critical bugs were found. All identified bugs are Minor or Major severity, which means the core application flows are working but input handling needs significant improvement before this application could be considered production ready.

## 7. Outstanding Issues

All 13 bugs found during this testing cycle are currently Open in JIRA under component DemoQA-Project2. No bugs have been fixed or closed at the time of this report.

### High Priority Items to Fix First:

1. BUG-TB-003 — Empty form submission passes silently with no validation message. This is the most impactful bug as it affects basic usability for all users.
2. BUG-REG-001 — Future date accepted in Date of Birth field. This creates invalid data records and is a data integrity risk.
3. BUG-EX-003 — Layout breaks on browser resize. In a real application this would affect all mobile and tablet users.

### Items That Can Be Deferred:

BUG-TB-001 — Typo in output label is Trivial severity and does not affect functionality. Can be fixed in a future release.

BUG-EX-002 — Emoji accepted in Full Name is Minor severity and low risk for most use cases.

## 8. Release Recommendation

RECOMMENDATION: DO NOT RELEASE

DemoQA in its current state is not recommended for release. While the core functionality works and no Critical bugs were found, 2 Major bugs remain open that directly impact the user experience and data integrity of the application.

BUG-TB-003 — empty form submission passing silently — means users receive no feedback when they forget to fill required fields. This creates confusion and a poor user experience that would lead to user dissatisfaction.

BUG-REG-001 — future date accepted in Date of Birth — means invalid data can be saved into the system. This is a data integrity risk that could cause problems in any real application that uses this data for age verification or record keeping.

Major bugs cannot be deferred to the next release. They must be fixed, retested, and confirmed as resolved before the application goes live. Once both Major bugs are fixed and
verified, a regression test should be run on the affected modules before release approval is given.

Minor and Trivial bugs can be scheduled for a follow up release after the Major issues are resolved.