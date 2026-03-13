# DemoQA_Exploratory_Session_01

Charter: Explore DemoQA Elements + Forms for validation and UI bugs
Tester: Janhavi Morajkar
Date: 13th March 2026
App: [https://demoqa.com/](https://demoqa.com/)
Start Time: [write current time]
Time Box: 60 minutes

### Text Box ([demoqa.com/text-box](http://demoqa.com/text-box))

| Time | Action | Expected | Actual | Bug? |
| --- | --- | --- | --- | --- |
| 18:30 | Paste full paragraph in Full Name | Accepted or truncated | Accepted — no character limit | N |
| 18:33 | Enter only spaces in all fields → Submit | Error shown | Spaces accepted in all fields. Only email validation fires | Y |
| 18:37 | Enter test@@test.com in Email → Submit | Error — invalid email | Email field turns red — validation works | N |
| 18:40 | Enter emoji 🎉 in Full Name → Submit | Error or accepted | Emoji accepted — no character restriction | Y |
| 18:42 | Resize browser to half width | Layout stays intact | Layout breaks — form not responsive | Y |

### Student Registration Form ([demoqa.com/automation-practice-form](http://demoqa.com/automation-practice-form))

| Time | Action | Expected | Actual | Bug? |
| --- | --- | --- | --- | --- |
| 18:45 | Submit without touching anything | All required errors shown | First Name, Last Name, Mobile show errors. Gender, Email, Picture show green tick even when empty | Y |
| 18:47 | Select gender → try to deselect | Cannot deselect radio button | Cannot deselect — can only switch between options | N |
| 18:49 | Type xyzabc in Subjects field | No autocomplete match shown | Only predefined subjects accepted — free text not allowed | N |
| 18:50 | Upload .pdf as picture | Error — only images allowed | PDF accepted — no file type validation | Y |
| 18:52 | Select State → City → change State | City resets | City does not reset — data inconsistency | Y |
| 18:54 | Tab through every field | Logical tab order | Tab order is logical | N |

### Buttons ([demoqa.com/buttons](http://demoqa.com/buttons))

| Time | Action | Expected | Actual | Bug? |
| --- | --- | --- | --- | --- |
| 18:55 | Double click "Double Click Me" | Success message appears | "You have done a double click" message appears | N |
| 18:56 | Right click "Right Click Me" | Success message appears | "You have done a right click" message appears | N |
| 18:59 | Single click "Click Me" button | Success message appears | "You have done a dynamic click" message appears | N |
| 19:00 | Single click where double click expected | Error or no response | No response — button does not react to wrong click type | N |

## 📋 Session Summary

**Total Time:** 60 minutes
**Areas Explored:** Text Box, Student Registration Form, Buttons
**Bugs Found:** 5

- BUG-EX-001 — Spaces accepted in all fields except email (Text Box)
- BUG-EX-002 — Emoji accepted in Full Name (Text Box)
- BUG-EX-003 — Layout breaks on browser resize (Text Box)
- BUG-EX-004 — Email and Picture show green tick when empty (Registration Form)
- BUG-EX-005 — PDF accepted in picture upload (Registration Form)

**Most Interesting Finding:**
Email and Picture fields show green tick (✅) even when empty misleading UI gives false confidence that fields are valid

**One thing DemoQA tests that guru99 didn't:**
Button interaction types  double click, right click, single click all handled differently. guru99 had no such interaction testing.
