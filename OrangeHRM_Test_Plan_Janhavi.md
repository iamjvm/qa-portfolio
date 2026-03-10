**Test Plan : OrangeHRM Demo Web Application**

Document Version: 1.0  
Prepared By: Janhavi Morajkar  
Date: 10th March 2026  
Project: Manual QA Testing — OrangeHRM Demo  
Application URL: https://opensource-demo.orangehrmlive.com

# Section 1: Scope

1.1 In Scope — Modules to be tested:  
\- Login and Authentication  
  \- Valid login, invalid credentials, empty fields, session handling  
      
\- Employee Management — Search  
  \- Search by first name, last name,employee ID, empty search  
      
\- Employee Management — Add Employee  
  \- Adding with all required fields, missing required fields, duplicate entries

1.2 Out of Scope — Will NOT be tested:  
\- Performance and load testing  
\- Mobile device testing (Android/iOS)  
\- Leave Management module  
\- Recruitment module  
\- Third-party integrations  
\- Automation testing

1.3 Reason for Exclusions:  
This cycle focuses on core authentication and employee management as these are the highest-risk features for end users. Excluded modules will be covered in a future test cycle.

# Section 2: Test Approach

2.1 Testing Type:  
Manual Functional Testing

2.2 Testing Techniques:  
\- Equivalence Partitioning dividing inputs into valid/invalid groups  
\- Boundary Value Analysis testing at the edges of input limits  
\- Negative Testing  invalid inputs, unexpected user behaviour  
\- Exploratory Testing unscripted sessions to find edge cases

2.3 Testing Levels:  
\- Functional testing does it work as expected?  
\- UI testing  are all elements visible, clickable, correctly labelled?  
\- Usability testing  is it intuitive for the end user?

2.4 Bug Tracking:  
JIRA — all bugs logged with severity, priority, steps to reproduce, expected result, actual result, and screenshots.

2.5 Test Management:  
Test cases maintained in Google Sheets.Execution status updated daily during testing.

# Section 3: Test Environment

|  Parameter | Details |
| :---: | :---: |
| Application | OrangeHRM Demo |
| URL | https://opensource-demo.orangehrmlive.com |
| Browser |  Google Chrome (latest stable version) |
| Operating System | Windows 11 |
| Screen Resolution | 1920 x 1080 |
| Valid Login Credentials | Username: Admin / Password: admin123 |
| Invalid Login Test data | Username: wronguser / Password: wrongpass |
| Network | Standard broadband connection |
| Test execution | Manual — no automation tools used |

Note: If the demo site resets credentials or data, testing will resume the next day after re-entering required test data.

# Section 4: Entry Criteria

Testing begins ONLY when ALL of the following are confirmed:

\- OrangeHRM demo site is accessible and loading correctly  
\- Valid credentials confirmed working (Admin / admin123)  
\- All test cases for in-scope modules are written and reviewed  
\- JIRA project is set up with correct components and issue types  
\- This Test Plan has been reviewed

# Section 5: Exit Criteria

Testing is complete ONLY when ALL of the following are true:

\- 100% of in-scope test cases have  been executed  
\- All Critical and High severity bugs are reported in JIRA  
\- Zero open Critical severity bugs remain  
\- All Major bugs are assigned to a developer or marked Won't Fix  
\- Test Summary Report is completed and shared with the team

# Section 6: Test Deliverables

| Deliverable | Status | Location |
| :---: | :---: | :---: |
| Test Plan | ✅ Complete | GitHub /test-plans/ |
| Test Cases — Login | ✅ Complete | GitHub /test-cases/ |
| Test Cases — Employee | ✅ Complete | GitHub /test-cases/ |
| Bug Report BR\_001 | ✅ Complete | GitHub \+ JIRA |
| Bug Report BR\_002 | ✅ Complete | GitHub \+ JIRA |
| Bug Report BR\_003 | ✅ Complete | GitHub \+ JIRA |
| JIRA Sprint Board | ✅ Complete | JIRA Sprint 1 |
| Test Summary Report | 🔲 Pending | To be created |

# Section 7: Risks and Mitigations

| Risk | Likelihood | Impact | Mitigation |
| :---: | :---: | :---: | :---: |
| Demo site slow or unavailable | Medium | High | Screenshot evidence, retest next day |
| Demo site resets test data | High | Medium | Re-enter data at start of each session |
| Requirements unclear mid-cycle | Medium | High | Raise queries with team before writing test cases |
| Tester availability reduced | Medium | Medium | Prioritise Critical/High test cases first |
| New features added without notice | Low | Medium | Re-review scope with team before execution |

# Section 8: Test Schedule

| Activity | Target Date | Status |
| :---: | :---: | :---: |
| Test Plan written | 10th March 2026 | ✅ Done |
| JIRA project setup | 5th March 2026 | ✅ Done |
| Test cases — Login module | 4th March 2026 | ✅ Done |
| Test cases — Employee module | 4th March 2026 | ✅ Done |
| Test execution — Login | 11th March 2026 | 🔲 Pending |
| Test execution — Employee | 12th March 2026 | 🔲 Pending |
| Bug reporting | 11–13th March 2026 | 🔲 Pending |
| Retest of fixed bugs | 14th March 2026 | 🔲 Pending |
| Test Summary Report | 15th March 2026 | 🔲 Pending |
| Test cycle closure | 15th March 2026 | 🔲 Pending |

# Section 9: Approvals

| Role: QA Tester  | Name: Janhavi Morajkar | Date: 10th March 2026 |
| :---: | :---: | :---: |
| Role: Reviewer  | Name: —               | Date: — |

