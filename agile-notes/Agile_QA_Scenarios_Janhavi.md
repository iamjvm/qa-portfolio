Scenario 1:
You are 3 days into a sprint. You're testing the Login feature. It crashes every time you enter a valid username and password. What do you do?
> I found a Critical bug the Login feature crashes on valid credentials, blocking all users from accessing the app. 
> I immediately log it in JIRA with Critical severity and High priority, attach screenshots and steps to reproduce, and notify the developer directly on chat. 
> My standup update tomorrow: "Yesterday I tested the Login feature and found a Critical bug the app crashes on valid login. I've logged it as DEV-XX in JIRA and flagged it to Deb Kashyap. Today I'll continue testing remaining scenarios once the fix is available."

Scenario 2:
It's the LAST DAY of the sprint. Sprint Review is in 3 hours. You're still testing and you found 2 bugs one Major, one Minor. You WON'T finish retesting before the review. What do you do?
> With Sprint Review in 3 hours and 2 bugs still open, I immediately inform my QA Lead or Project Manager about the situation not after the review, but right now.
> For the Major bug I recommend blocking the story from the Sprint Review. Shipping a Major bug to stakeholder’s damages team credibility.
> For the Minor bug I flag it but agree it can move to the next sprint backlog without blocking the review.
> My message to the lead: "I have a Major bug still open on the Login story I recommend we don't demo it today and move it to next sprint for a proper fix."

Scenario 3:
In Sprint Planning the Product Owner adds a new User Story to the sprint. You read it and the Acceptance Criteria are MISSING no definition of what success looks like. What do you do?
> No  I cannot write proper test cases without acceptance criteria. Testing without clear success criteria means I don't know what PASS or FAIL looks like.
> During Sprint Planning itself I raise my hand and politely ask the Product 
Owner: "Before we commit to this story, could we define the acceptance criteria? Without them I won't know what to test or when it's done."
> I do not wait until after planning unclear requirements caught early save the whole team from rework later.
> If the PO needs time to define them, I request the story be moved to the next sprint until it's ready.





Scenario 4:
You're in Daily Standup. Yesterday you tested Login and found 3 bugs. Today you'll test Search Employee. The developer whose code has bugs is also on the call.Write your ACTUAL standup script word for word.
Remember:
* Professional tone
* Not blame-heavy
* Clear and specific
My Standup Script:
"Yesterday I completed testing the Login module and found 3 bugs.
I've logged all 3 in JIRA:
- DEV-11: App crashes on valid login Critical
- DEV-12: Password field shows plain text Major
- DEV-13: Login button active when fields are empty Minor
All bugs have steps to reproduce and screenshots attached in JIRA.
Today I'll be testing the Search Employee module.
No blockers for now but I'd appreciate if the Login bugs could be picked up soon so I can retest 
before sprint ends."

Scenario 5:
Sprint ends TOMORROW. A developer says: "We don't have time to fix the Minor bugs — let's ship and fix next sprint."
There are 2 Minor bugs and 1 Major bug.
What is your response?
* What do you agree to?
* What do you push back on?
* How do you phrase it without creating conflict?

> I agree to ship the 2 Minor bugs they can be logged in JIRA and fixed in the next sprint without affecting the user experience significantly. 
> However, I push back on shipping the Major bug. My response to the developer: 
"I completely understand the time pressure and I agree we can carry the Minor bugs to next sprint. But I'd recommend we don't ship with the Major bug open  it could directly impact users and create bigger issues in production that take more time to fix later than fixing it now. Can we get just this one resolved before we ship?" 
> This way I'm not being aggressive I’m protecting the team and the user at the same time.
