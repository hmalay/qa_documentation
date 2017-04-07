# QA Methodology
## Planning
To begin the planning stage, QA's have to meet with developers and/or product owners and/or clients to discuss the documentation and project scope prior to implementation to begin the planning stage. Documentation comes in various forms, from paper to electronic, but no matter what kind, these product/project documents have to be analyzed. The time reading it should also be time dedicated to looking for any discrepancies and issues, meanwhile also building and spec'ing test dependancies, frameworks and cases. The product document is examined thoroughly for complexity, UI features, functionality, issues and most importantly `requirements`; some aspects may need to be changed to work. Analysis as a QA is feedback for the developers.
## Implementation
Feedback to developers signals the beginning of the implementation stage. The product is placed into the warm and loving hands of development. During this stage QA's begin to build test cases for the upcoming product. These cases are built with the concepts in Test Plans parenting Test Cases/Scenarios. Each test is designed to examine the product as per the Scope Document(s). After further documentation is processed, the QA's begin building test cases again to examine the code that has been provided. The testing goes on until all elements of the product have been tested thoroughly. 

Software testing is the process of validating and verifying that a software program/application/product:

1. Meets the requirements that guided its design and development;
2. Works as expected; and
3. Can be implemented with the same characteristics in other environments

## Delivery & Maintenance
This is the bulk of the QA work. Regression tests are executed during this phase, Manual or Automation. After more tests have been built to meet the needs of client based functionalities, a UAT has to be drafted and handed out to the client(s), internal and/or external. 

This UAT (User Acceptance Test) tests all up-to-date functions of the software. During this phase it is also key to build test plans, tests that check the code in a regimented fashion. These tests also have to be executed, heeding to the Test Schedule. All test results have to be delivered, in a Test Execution Report. `Everything has to be reproducible.`

## Test Types
During the planning stage, QA Testers build test cases. Test cases and test plans require a full assessment of the documentation. 

There are many kinds of testing and they include but are not limited to:

| Type | Description |
| --- | --- |
| Black-Box | Internal system design is not considered in this type of testing. Tests are based on requirements and functionality. |
| White -Box | This testing is based on knowledge of the internal logic of an application's code. Also known as Glass box Testing. Internal software and code working should be known for this type of testing. Tests are based on coverage of code statements, branches, paths, conditions. |
| Unit | Testing of individual software components. Typically done by the programmer and not by testers, as it requires detailed knowledge of the internal program design and code. May require developing test driver modules or test harnesses. |
| Incremental Integration | Bottom up approach for testing i.e. continuous testing of an application as new functionality is added; Application functionality and modules should be independent enough to test separately. Done by programmers or by testers. |
| Integration | Testing of integrated modules to verify functionality after integration. Modules are typically code modules, individual applications, client and server applications on a network, etc. This type of testing is especially relevant to client/server and distributed systems. |
| Functional | This type of testing ignores the internal parts and focus on the output is as per requirement or not. Black-box type testing geared to functional requirements of an application. |
| System | Entire system is tested as per the requirements. Black-box type testing that is based on overall requirements/specifications. Covers all combined parts of a system. |
| End-to-End | Similar to system testing, involves testing of a complete application environment in a situation that mimics real-world use, such as interacting with a database, using network communications, or interacting with other hardware, applications, or systems if appropriate. |
| Sanity | Testing to determine if a new software version is performing well enough to accept it for a major testing effort. If application is crashing for initial use then system is not stable enough for further testing and build or application is assigned to fix. |
| Regression | Testing the application as a whole for the modification in any module or functionality. Difficult to cover all the system in regression testing so typically automation tools are used for these testing types. |
| Acceptance, UAT | Normally this type of testing is done to verify if system meets the customer specified requirements. Users or customers use this testing to determine whether to accept application. |
| Load | It's a performance testing to check system behavior under load. Testing an application under heavy loads, such as testing of a web site under a range of loads to determine at what point the system response time degrades or fails. |
| Stress | System is stressed beyond its specifications to check how and when it fails. Performed under heavy load like putting large number beyond storage capacity, complex database queries, continuous input to system or database load. |
| Performance | Term often used interchangeably with stress and load testing. To check whether system meets performance requirements. Used different performance and load tools to do this. |
| Usability | User-friendliness check. Application flow is tested, Can new user understand the application easily, Proper help documented whenever user stuck at any point. Basically system navigation is checked in this testing. |
| Installation | Tested for full, partial, or upgrade install/uninstall processes on different operating systems under different hardware, software environment. |
| Recovery | Testing how well a system recovers from crashes, hardware failures, or other catastrophic problems.
| Security | Can system be penetrated by any hacking way. Testing how well the system protects against unauthorized internal or external access. Checked if system, database is safe from external attacks. |
| Compatibility | Testing how well software performs in a particular hardware/software/operating system/network environment and different combinations of above.
| Comparison | Comparison of product strengths and weaknesses with previous versions or other similar products.
| Alpha | In house virtual user environment can be created for this type of testing. Testing is done at the end of development. Still minor design changes may be made as a result of such testing. |
| Beta | Testing typically done by end-users or others. Final testing before releasing application for commercial purpose. |


## Test Plans
Early in the deployment planning phase, the testing team creates a test plan. The test plan defines the objectives and scope of the testing effort, and identifies the methodology that your team will use to conduct tests. It also identifies the hardware, software, and tools required for testing and the features and functions that will be tested. A well-rounded test plan notes any risk factors that jeopardize testing and includes a testing schedule.

If your testing team is divided into technology sub-teams, each sub-team should develop a test plan for that team's specific technology area. For example, the networking team would write a test plan for testing networking features. All members of each sub-team should review and approve its team's test plan before it is integrated into the general test plan.


## Defining Test Scope
In the scope and objectives section of the test plan, the testing team describes specifically what you want your testing to accomplish. 

Also, you need to define the scope of your testing by identifying what you will test and what you will not. For example, you might limit your testing of client computer hardware to the minimum supported configurations or to the standard configurations.

## Identify Requirements
| Requirement | Description |
| --- | --- |
| Hardware |  List the hardware that you need to conduct tests. Include components such as video cards, modems, routers and external drives. |
| Software |  List the software that you need to test the compatibility of your applications within defined environments. |
| Environments | Include databases or environments that you need to prepare for testing applications. Also include a description of the resources that you need to populate the databases, such as personal and business data. |
| Personnel | Identify the number of testers you need and the skill level required. Include consultants and other support personnel, as necessary. |
| Training | For example, any additional learning or training that your testers need to complete prior to testing their assigned applications or technologies. |
| Tools | Include all tools or scripts that you need to automate testing and to track results. |

## List Features
List all the features or aspects of features that need to be tested. This part of the test plan describes what to test, not how to test. For example:

1. Contact Form
2. Checkout/Shopping Cart
3. Registration & Log In
4. Account Management
5. RMA Return Management

##Define Acceptance Criteria
Acceptance criteria is to be determined by the User Stories that make up the MVP. The user stories will follow but the test coverage has to ensure:

* The functionality of each feature and service that implemented
* Interoperability with existing components and systems in the production environment, both during the phase-in period and after the environment has been rolled out
* Hardware and driver compatibility for every type of client computer
* Application compatibility for every application
* Application compatibility for every server application
* Optimization of configurations, such as those for standardized desktops on client computers
* Baselines (a range of measurements derived from performance monitoring that represents acceptable performance under typical conditions) for performance monitoring
* Baselines and stress tests for capacity planning
* Procedures for deployment and post-deployment administration, such as procedures for upgrading a client computer and for backing out of a faulty rollout process.
* Uses the required tools and utilities
* Describes the risk factors that could prevent the successful completion of all required tests.


##Create a Test Schedule
Draft a preliminary schedule that includes each test listed in the test plan. The schedule can help you coordinate test lab use among sub-teams. Assign a team member, ideally the test lab manager, if your team has one, to maintain and update the lab schedule. Having an up-to-date schedule is critical when unscheduled lab requests are submitted. 

Testing occurs through all phases of development. The dates below denote stress, forced-error, UAT, End to End and System testing prior to client review. Testing will continue to occur during development and integration. Automation and unit tests to be completed in parallel to manual testing, if feasible and necessary. For example:

| Task Name | Duration (days) | Start | Finish |
| --- | --- | --- | --- |
| Application Name | 36 | MM/DD/YYYY | MM/DD/YYYY |
| Development | 22 | MM/DD/YYYY | MM/DD/YYYY |
| QA Review #1 - Theta Testing | 2 | MM/DD/YYYY | MM/DD/YYYY |
| Development (Revisions) | 2 | MM/DD/YYYY | MM/DD/YYYY |
| Deployment to QA Environment | 2 | MM/DD/YYYY | MM/DD/YYYY |
| QA Review #2 - Beta Testing | 1 | MM/DD/YYYY | MM/DD/YYYY |
| Deployment to Stage or Alpha Environment | 2 | MM/DD/YYYY | MM/DD/YYYY |
| Final QA - Alpha Testing | 5 | MM/DD/YYYY | MM/DD/YYYY |


##Define Epic User Stories
List all the features or aspects of features that need to be tested. This part of the test plan describes what to test, not how to test. The terminology and format are not limited to any type. However, user stories are business-readable and proficient.

###User Stories [*](http://en.wikipedia.org/wiki/User_story)

####Traditional user-story template

	As a <role>, 
	I want <goal/desire>, 
	So that <benefit>

The "so that" clause as optional.

####Hunting the value

	In order to <receive benefit>, 
	As a <role>, 
	I want <goal/desire>
	
####Five W's specifies:

	As <who> <when> <where>, 
	I <what>, 
	Because <why>


##Define Scenarios
A test case or scenario is a detailed procedure that fully tests a feature or an aspect of a feature. Whereas the test plan describes what is to be tested, a test case describes how to perform a particular test. You need to develop a test case for each test listed in the test plan or test specification.

Test cases should be written by someone who understands the function or technology being tested and should go through a peer review.

Test cases include information such as the following:

* Purpose of the test
* Special hardware requirements, such as a modem
* Special software requirements, such as a tool
* Specific setup or configuration requirements
* Description of how to perform the test
* Expected results or success criteria for the test
* Designing test cases can be a time-consuming phase in your testing schedule. Although you might be tempted to take shortcuts, the time you spend will pay off in the long run. 

*You can conduct tests faster when they are carefully planned. Otherwise, testers spend time debugging and rerunning tests.*

Organizations take a variety of approaches to documenting test cases; these range from developing detailed, recipe-like steps to writing general descriptions. In detailed test cases, the steps describe exactly how to perform the test. In descriptive test cases, the tester decides at the time of the test how to perform the test and what data to use.

Some advantages of detailed test cases are that they are reproducible and they are easier to automate. This approach is particularly important if you plan to compare the results of tests over time, such as when you are optimizing configurations. A disadvantage of detailed test cases is that they are more time-consuming to develop and maintain. On the other hand, test cases that are open to interpretation are not repeatable and can lead to debugging time that pertains more to the test itself than to what is being tested.

It is recommended that you find a compromise between the two extremes, one that tends toward more detail. Balance thoroughness with practicality to reach your goal of test integrity and manageability.

##Advantages of Gherkin-based Tests
Scenarios can be written in a multitude of ways. However, when it comes to standardization, its hard to hit the nail on the head as uniquely as Gherkin does. Even if AUT uses a JavaScript or fully-Manual testing solution, business-readable scenarios go along way for 

###Gherkin scenarios

Once you've chosen a feature, it's time to write scenarios that describe each part of it. Each scenario follows a very specific pattern. Start by giving it a name.
The body of a scenario is made up of three different parts, let's use: `Given`, `When` and `Then`. 

The first is Given, which describes the initial state of the system for the scenario. This is the only place where you can describe things that the user can't do. In this case, the "site administrator" can't magically put 5 news entries in the database, but that's ok. To have more than one Given statement, start the next line with And.

The second part of each scenario is When, which describes the actual action that this user is taking. Finally, Then is used to describe what our user can see at the end of the scenario.

The exact language you use in your scenarios is up to you - just make sure to follow the Given, When, Then format. Each line in the scenario is called a "step", and should plainly describe what the user is doing and seeing.

If we didn't go any further, we would at least have a standard way of describing our features. Writing scenarios also makes you think through each feature in more detail. When you're finished, you've got a blueprint for exactly what you need to develop, written in language that your client can understand.

	Feature: Remote fence control API
	In order to control fence security from anywhere
	As an API user
	I need to be able to POST JSON instructions that turn fences on/off

	
	Feature: Delicious humans
	In order to be entertained
	As a dinosaur
	I need to be able to watch delicious humans pass by me all day

	Feature: Add a news entry
		Scenario: Add a new news entry
		Given I am on "/admin/news"
		When I click "New entry"
		And I fill in "Title" with "Alan Grant does not endorse the park!"
		And I press "Save"
		Then I should see "Your article has been saved"
		
You can also add test data for your scenario, which can also be referred to as examples:

	Feature: Add a news entry
		Scenario Outline: Add a new news entry
		Given I am on "<URL>"
		When I click "<button>"
		And I fill in "<form>" with "<text>"
		And I press "Save"
		Then I should see "<expectedResult>"
		
		Examples:
		| URL | button | form | text | expectedResult |
		| /admin/news | New entry | Title | Alan Grant does not endorse the park! | Your article has been saved |




##Execution & Results
Depending on test coverage, manual, unit and automation reports are handled separately. An example, below work in progress, would use the @TAGS to identify a test type, a feature & scenario.

| Tags | P/F | Description | Notes |
| --- | --- | --- | --- |
| @type1 @epic1 @scenario1 | P | Some abstract on the feature. | Tested on iOS and Android in addition to IE and Chrome on Windows. |
| @type2 @epic2 @scenario2 | F | Some abstract on the feature. | See more in TICKET-XXX |

___
