### Test Types 
1. Functional Testing -  Does it do what it is supposed to do? 
    - this type of testing verifies that every feature of the application works according to its requirement.
    - ex: "forgot password function" - valid email --> allows to reset the password, else shows error message for invalid email 
  - there are two main types of functional testing: 
  1. black-box testing - tester acts as a real user and sends inputs, checks outputs without having knowladge for internal system 
  2. white-box testing - done by developers to check the internal logic and functions performing correctly as they are expected 

2. Non-functional testing - How well does it work?
    - Non-functional testing evaluates the characteristics of a system, it doesn't only check a feature works but checks how well it performs under certain conditions(Quality)
  - two of the most critical non-functional testing types: 
  1. Performance Testing - this checks the application's performance under certain conditions, how its behaving in terms of speed, responsiveness, stability. 
  2. Usability Testing -  focuses on how easy, intuitive, and user-friendly the software is. done by reviweing real user's attempts to complete a certain task. 

3. Maintenance Testing - Does it still work after a change? 
    - Maintenance Testing is performed in order to verify that application still works after a modification. 
    - Regression Testing:  
 - process of re-testing existing features to ensure that a recent code change or bug fix has not unintentionally broken other parts of the application


### STLC - Software Testing Lifecycle 
- A repeatable process to test the software before it reaches to the customer 
- there are 6 pahses of STLC and current phase depends on the previous one
1. `Requirement Analysis` - read, understand the documentation to realize what needs to be tested, or how the application should behave. (Recipe)
2. `Test Planning` - Defining the testing strategy, the scope, tools, budget, all the resources to schedule before testing. 
3. `Test Design` - Instruction for the tester to perform each action with clear goal and questions to clarify the target. 
4. `Test  Environment` -  Control space, the combination of hardware, software, and network settings where all the data and system is ready to perform testing 
    - this step must be very important because a test case passing in a wrong environment but failing in the real one is not a passing test case, it must be retested! 
5. `Test Execution` - in this phase, everything is documented for future review and bug fixes, detailed report about what was tested, expected, and exectly what went wrong in case if test is negative.
6. `Test Closure` - a pahase where the team steps back and review every detail from beginning to the end to review what needs to be improved,  learned, or  the application is ready to ship. 

### Practice for STLC. 
- testing a search bar in the shopping website across three stages. 
1. Requirememt analysis - search bar is supposed to help users to find products, to type what they wanted, to autocorrect mispronounced words and show relevant products according to the catagory. 
2. Test Planning: 
### Objective
Ensure the search bar returns accurate, relevant results quickly and handles edge cases gracefully.

### Scope
Test functionality, usability, performance, and error handling of the search bar.

### Test Items
* Search input field
* Search button/icon
* Search results page
* Autocomplete/suggestions (if applicable)
* Handling of special characters and empty inputs

### Test Strategy
* **Manual Testing:** Focus on UI and usability end-to-end flows.
* **Automated Testing:** Selenium WebDriver for UI regression; JMeter for performance and API endpoints.
* **Compatibility:** Cross-browser (Chrome, Firefox, Safari, Edge) and responsive device testing (Desktop & Mobile).

### Resources & Tools
**Team Allocations:** Testers assigned to UI, backend, and performance testing.
**Tools Stack:**
  Automation: Selenium WebDriver
Performance: Apache JMeter
3. Test Design:
*    Enter a valid product name and verify correct results appear.
*    Enter a partial product name and check autocomplete suggestions.
*    Enter special characters and verify system handles them without crashing.
*    Submit an empty search and verify appropriate message is shown.
*    Test search response time under normal and peak loads.


### Executing functional and non-functional testing in mindBridge lab 
# SC2 Test Log — Functional vs. Non-Functional

Record one row per check as you run the lab. Fill the shaded example row first, then your own results.

## Test Results

| # | Check                           | Type (Functional / Non-functional) | Input / Condition                    | Expected result                            | Actual result                                                              | Pass / Fail |
|:--|:--------------------------------|:-----------------------------------|:-------------------------------------|:-------------------------------------------|:---------------------------------------------------------------------------|:------------|
| 0 | Example: search returns matches | Functional                         | Search term: `Testing`               | Only courses matching "Testing" are listed | 3 matching cards shown                                                     | Pass        |
| 1 | Search returns matching courses | Functional                         | Search term: `Siftware Testing`      | Matching Results should appear             | Multiple courses shown with the title Software Testing                     | Pass        |
| 2 | `/api/courses` response time    | Non-functional                     | Same search re-run, Network tab open | Under ~1000 ms for a responsive product    | Measured: 3.03 s                                                           | Fail        |
| 3 | Layout below ~768 px width      | Non-functional                     | Window width: 600px                  | Cards stack cleanly, nothing overflows     | Cards still stacking but texts are invisible grids are also half invisible | Fail        |
| 4 | Layout at 768 px or wider       | Non-functional                     | Window width: 800 px                 | Grid displays correctly                    | Working perfectly, showing 2 grids and everything is visible               | Pass        |

## STLC Mapping

One sentence per check: which STLC phase produced the observation, and why.

| Check | STLC Phase                  | Why                                                |
|:------|:----------------------------|:---------------------------------------------------|
| 1     | Test Planning / Test Design | You defined the scope and the pass/fail criteria   |
| 2     | Test Environment Setup      | You prepared the environment before executing      |
| 3     | Test Cycle Closure          | You evaluate outcomes and report release readiness |

## Wrap-Up Answers

* **Which check was functional, and why?**  
  Check 1 was functional because it evaluated the core business logic and expected feature output (returning matching courses based on the search query).

* **Which two checks were non-functional, and why?**  
  Checks 2 and 3 were non-functional because they evaluated system performance (response time) and UI responsiveness/layout under specific width constraints rather than core feature logic.

* **Can a feature pass functional testing and still have problems? Use your measured response time or the broken narrow layout as evidence.**  
  Yes. For example, Check 1 passed functionally, but Check 2 failed because the search response took 3.03 seconds, proving that a feature can work correctly in logic while failing non-functional performance standards.












