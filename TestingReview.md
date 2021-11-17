# Testing
- Testing is to make sure something works as expected
[Review Guide](https://github.com/adamranieri/2105PythonBatch/blob/main/Reviews/InterviewQuestions.md)

- **Functional**
    - Something gives the correct outputs given the correct inputs
    - Unconcerned with efficiency
    - **Positive**
        - Happy path 
        - Expected inputs
        - Correct username correct password *should* log you in
    - **Negative**
        - Testing for when things do not go smoothly
        - Incorrect username or incorrect password *should not* let you log in
    - Positve and negative tests should pass
    - Tools
        - JUnit
        - Postman
- **Performance**
    - The **efficiency** of you program/software
        - Time 
        - Memory usage
        - Processing power
        - Bandwidth
    - **Load**
        - You emulate a high amount of *normal* usage on an application
    - **Stress**
        - Abnornaml usage of the application
        - Trying to break the applications using weird situations
            - 10,000 users decide to login at the exact same time
    - Tools
        - SoapUI
        - JMeter
- **Acceptance Testing/ User Acceptance Testing**
    - The human factor.
    - Has to almost always be done manually.
    - Ultimately most software is designed to be used by humans.
    - **Alpha**
        - Internal developers/team members use the application 
        - Spot probelms that affect usability like black text on a black background
    - **Beta**
        - External *end-users* use the application 
        - You should have ACUTAL accountants try to use your accounting software
            - Point out features that are really unintuitive for the field
    - Tools
        - Excel sheets describing user stories
        - What not be something that requires programming

# How we Test
- **White Box**
    - You know what the code looks like
    - You are writing tests that address specific snippets of code
        - You are calling a method and seeing that the return is what is expected
- **Gray box**
    - Code that you might have some exposure to
- **Black Box**
    - Testing software when you do not know what the code looks like
    - Am I getting what I want?
- **Testing Pyramid**
![Testing Pyramid](https://reflect.run/images/articles/automated-tools-pyramid.png)
- **Unit Tests**
    - Small 
    - Atomic
        - They check for one specific thing.
        - A unit test will check a *single* method
    - The bulk of the tests you write should be unit tests.
- **Integration Tests**
    - little bit larger than unit
    - They check to see if multiple parts of the software are working together as expected
    - You usually see this a lot in the service layer.
- **E2E (End to End)**
    - Testing the entire application
    - Does this application give me the correct final result and work as it should
    - Does pressing buy actually work and create an order that is process fulfilled.

# Automation Testing
- Offloading the running and checking of test cases to a computer versus a human being.
- This can be done at any level of testing
    - For unit testing (Very easy to automate)
    - For Integration tests
    - For E2E Tests (Can be difficult. Think of all of the different UIs out there)
- Pros
    - Tests are a lot faster run by a machine rather than a human
        - The faster you can see test results the faster you can fix your application
    - Machines don't make mistakes
    - Machine don't take days off, can be run at any time
    - Will be cheaper than humans in the long run.
- Cons
    - It does require skill and technical programming to write automated tests
    - It does take time to set up automated tests (usually worth it in the long run)

## TDD
- Test Driven Development
- Test first then Implement
- Why is it important to write the tests first?
    - Until you prove something works it does not work
        - Writing the tests will you save you time. 
        - Fixing bugs is not the time sink. It is finding where the bugs come from.
    - When you test first you come up with all the different ways that piece of software will work.
    - The process of designing test cases guides how the the code is written

## BDD
- Behavior driven development
- A really common problem in applications is feature sprawl.
    - You write code for features/ that no one requested
- The process
1. You create **user stories**
    - As a Employee I want to view orders so that I can reach out to customers
2. You create the **Acceptance Criteria** for that user stories
    - A actual steps that must be undertaken to fulfil that user stories
    - Often writtin in something like gherkin
    - A Human should be able to read this feature file and manually see if it works
```Gherkin  
    Scenario: Employee Responds To an Order
        Given The Employee is on the Order Review Page
        When The Employee clicks on The Order Details button
        Then A popup with the Cusomter's information should appear
```
3. Run That Acceptance Criteria and see if it passes
    - A Human could do this
    - If it can be **automated** that would be preferred
        - Selenium and Cucumber
    - You should be checking the results of these as if you are an end user

## Selenium
- IT NOT A TESTING FRAMEWORK
- It is for automating browser, *that't it*

## Cucumber
- Original a Ruby testing framework
- It is a *Testing Framework*
- The big selling point to Cucumber was that test cases were written in Gherkin which is like English

### Cucmumber(Testing Framework) + Selenium(Automation) Testing Automation 
- Cucubmer and Selenium go together like Peanut Butter and Chocolate
    - 0 relation to each other but go together great

### STLC/SDLC/Defect Life Cycle
- Software Development Lifecycle
![SDLC and STLC](https://www.sealights.io/wp-content/uploads/2020/03/figure1.png)
- Testing is an ***ESSENTIAL*** part of development
- Having untested code is a recipe for disaster
- Web Applications are NEVER finished. There is always a new feature
- There is no perfect definition of either
- SDLC
    1. Analysis/requiremnts (look at the current app and what needs to be done)
    2. Design 
    3. Implment
    4. Deploy
    5. Maitnence
- STLC (For the most part the same but think of the tests as the application)
    1. Analysis/requirements (Current state of testing and what needs to be done)
    2. Test Case design
    3. Test Case implemention (Evironment setup)
    4. Excuecute the tests
    5. Report the results

- Defect Life Cycle
![Defect Life Cycle](https://www.softwaretestinghelp.com/wp-content/qa/uploads/2018/01/Defect-Life-cycle-In-HPM.jpg)
1. Bug is reported
    - Can be rejected
        - Not a bug
        - Not worth the time
2. Bug is open/worked on
    - Hopefully fixed
    - Might get reassigned to someone who can fix it
3. Bug is closed

- **Bug/Defect** is ANYTHING in the creates unexpected behavior
    - NOT intrisically bad.
- **Priority**
    - How urgently something needs to be fixed
- **Severity**
    - How much it breaks a feature