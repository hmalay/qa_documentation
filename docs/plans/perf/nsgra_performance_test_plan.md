# Performance Tests

## Overview

### Authors

| Name | Email |
| --- | --- |
| Navraj Nat 	   | <NNat@Scholastic.com>     |
| Sajjad Hossain | <shossain@scholastic.com> |

### Vesions
| Date | Version |
| --- | --- |
| 05/25/17 | 1.0 |
| 06/22/17 | 1.1 |

### Scope

The scope of this test plan only extends extends itself to Performance Testing for Environment Promotion. If these tests fail, then there are major, critical bugs to resolve for performance and system requirements to meet expectations.


### Abstract

Next Step Guided Reading Assessment provides teachers with an easy-to-use online resource designed to compile valuable student reading assessment data—the information teachers need to group students, select texts, and plan and teach guided reading lessons, and interpret and organize it into printable reports for teachers.

NSGRA Features include:

* Assessment Tools
* Reporting
* Lesson Plans
* PDF Resources
* Product Usage Videos


**Application Development**: Features and experiences meant to enhance the content or experience of using NSGRA.  

* Initial launch is limited to Educator roles, not students or parents.
* User Profile, Registration, and License details would all be managed via Scholastic Digital Manager
* Content and data served in NSGRA could be integrated with Scholastic’s ecosystem and tools; including but not limited to:
	* SDM
	* Woodwing
	* Adobe Suite (Primarily IDD & IC)
	* PRM (Scholastic’s Digital Delivery Content Management System)
	* AEM
	* Clever
	* GIT
	* eReader
	* Analytics


### Requirements

#### Compatibility

| Operating System | OS Version | Webkit(s) | Supported Version(s) |
| --- | --- | --- | --- |
| Mac OS X |  10.9.x + | Safari | Latest 3 versions |
||| Chrome | Latest 3 versions |
| iOS | 7.x.x + | Safari | Latest 3 versions |
||| Chrome | Latest 3 versions |
| Windows | 7.x.x + | Chrome | Latest 3 versions |
||| Firefox | Latest 3 versions |
||| Internet Explorer | Version 11.x.x + |
||| Edge | Version 12.x.x + |

#### Environments

* LOCAL (DEV)
* DEV
* QA
* PERF
* PRODUCTION

#### Personnel

| Name | Email |
| --- | --- |
| Bruce Grogan	| <bgrogan@scholastic.com> |
| Deanna Rullan | <drullan-consultant@scholastic.com> |
| Grace Clifford	| <gclifford-temp@scholastic.com> |


#### Tools

* [Eclipse](http://www.eclipse.org/downloads/packages/eclipse-ide-java-ee-developers/neon2)
* [PHP 8](http://php.net/manual/en/intro-whatis.php)
* [Widefly](http://wildfly.org/downloads/)
* [MySQL](https://dev.mysql.com/downloads/mysql/)
* [MySQL Workbench](https://downloads.mysql.com/archives/workbench/)
* [SourceTree](https://www.sourcetreeapp.com/)
* [BitBucket](https://bitbucket.org)


### Acceptance Criteria

The acceptance criteria for this test plan extends itself to only performance-level interaction with the application and its' endpoints and requests made under-the-hood.

1. The systems' performance during the performance & stress tests should be greater or equal to server conditions during baseline system performance test.
2. Application should have a reasonable response time:
	* User Interface requests should resolve under 6 seconds with no delays presented to the user
	* Background requests should timeout or resolve in 30 seconds with no impacts presented to the user
3. Server resource allocation should handle redirects and loadbalancing to serve performance and stress conditions
	* Load balancers should be identified and tested
	* CDNs, and other content delivery systems should be identified and tested

The tests do not meet pass criteria if:

* System crashes during test
* System becomes momentarily unresponsive
* System performance during tests is worse than baseline test conditions


### Known Defects

| JIRA | Notes |
| --- | --- |
| | |

### Risks

1. Known defects are not identified

### Load Model

| Application | User | Scenario | User Agent | Page Visits |
| --- | --- | --- | --- | --- |
| NSGRA | Teacher | I want to assess Development Word Knowledge | Browser | 5000 |
| "" | "" | I want to assess Reading Interest Survey | "" | "" |
| "" | "" | I want to assess Listening Comprehension | "" | "" |
| "" | "" | I want to assess Reading Assessment Conference  | "" | "" |
| "" | "" | I want to see Resources  | "" | "" |
| "" | "" | I want to see Admin Report Page  | "" | "" |
| "" | "" | I want to see the Admin Summary Progress Report Page  | "" | "" |
| "" | "" | I want to see the Admin Reading Benchmark Report Page  | "" | "" |

### Schedule

| Task Name | Duration (days) | Start | Finish |
| --- | --- | --- | --- |
| Review and Finalize Plan | 2 | 15.1 | 15.4 |
| Dress Rehearsal | 1 | 15.1 | 15.4 |
| Test Scripting | 3 | 15.1 | 15.4 |
| 1x Testing | 1 | 15.1 | 15.4 |
| 2x Testing | 1 | 15.1 | 15.4 |
| Endurance Testing | 1.5 | 15.1 | 15.4 |
| Alpha Testing | 1 | 15.1 | 15.4 |

### Tests

| Test Name | Description |
| --- | --- |
| Dress Rehearsal | This will test the JMeter installation and make sure that requests sent from JMeter is properly received by the system under test |
| 1x Testing | These tests will be executed as a baseline for up to an hour.  |
| 2x Testing | These tests will stress test the system with 150% - 300% of our Peak Load. |
| Endurance Testing | These tests will stress test the system for about 36 hours with a moderate size load. |
| Alpha Testing | Re-run any tests that need to be ran again |

### Epics

1. I want to benchmark the system under the highest load possible
2. I want to make sure scholastic resources are resolved within 2 seconds
3. I want to make sure server requests are load balanced
4. I want to make sure content is delivered from a content delivery network
5. I want to test the system under the highest expected load conditions
6. I want to stress test the system under high concurrent usage conditions
7. I want to test the views with the most unique page views from Google Analytics

## Test Cases

## `${preconditions}`

```
Given I am on NSGRA
And I am a ${userType}
Then I should be on Scholastic Digital Manager
And I should see the log in form
When I fill in the log in form with ${credentials}
And I submit the log in form
Then I should see the NSGRA(K-2 or 3-6) icon
When I launch NSGRA(K-2 or 3-6) icon
```

### I want to benchmark the system under the highest load possible

```gherkin
As a quality engineer
I want to benchmark the system under the highest load possible
So that I can benchmark the systems maximum load
```

### I want to test the system under the highest expected load conditions

```gherkin
As a quality engineer
I want to test the system under the highest expected load conditions
So that I can performance test our system according to benchmarks
```

### I want to stress test the system under high concurrent usage conditions

```gherkin
As a quality engineer
I want to stress test the system under high concurrent usage conditions
So that I can stress test our system under unusually high traffic
```


#### Scenarios

1. I want to assess Development Word Knowledge
2. I want to assess Reading Interest Survey
3. I want to assess Listening Comprehension
4. I want to assess Reading Assessment Conference  
5. I want to see Resources
6. I want to see Admin Report Page
7. I want to see the Admin Summary Progress Report Page
8. I want to see the Admin Reading Benchmark Report Page


#### Stories

##### I want to assess Development Word Knowledge

```gherkin
${preconditions}
And I click the Assess Card
And I click the Development Word Knowledge Card
Then I should be on Developmental Word Knowledge page
And I select a ${class} from the class dropdown
And I select a ${time_period} from the time period dropdown
Then I click the view button
And I click on student ${student_name}
And a popup window for the student should display
Then I select a value for each of the dropdown
And click the save and close button
And should see the results I saved on the Developmental Word Knowledge page
Then I assessed Developmental Word Knowledge

Examples:
|userType|class|time_period| student_name|
|Teacher|English|Beginning of Year| John Smith |
```

##### I want to assess Reading Interest Survey

```gherkin
${preconditions}
And I click the Assess Card
And I click the Reading Interest Survey Card
Then I should be on Reading Interest Survey Card page
And I select a ${class} from the class dropdown
And I select a ${time_period} from the time period dropdown
Then I click the view button
And I click on student ${student_name}
And a popup window for the student should display
Then I check off certain check boxes
And click the save button
And should see the results I saved on the Reading Interest Survey page
Then I assessed the Reading Interest Survey  

Examples:
|userType|class|time_period|student_name|
|Teacher|English|Beginning of Year|John Smith|
```

##### I want to assess Listening Comprehension

```gherkin
${preconditions}
And I click the Assess Card
And I click the Listening Comprehension Card
Then I should be on Listening Comprehension Card page
And I select a ${class} from the class dropdown
Then I click the view button
And I click on student ${student_name}
And a popup window for the student should display
Then I mark the correct and incorrect answers(radio buttons)
And click the save and close button
And should see the results I saved on the Listening Comprehension page
Then I assessed the Listening Comprehension

Examples:
|userType|class|student_name|
|Teacher|English|John Smith|
```

##### I want to assess Reading Assessment Conference

```gherkin
${preconditions}
And I click the Assess Card
And I click the Reading Assessment Conference Card
Then I should be on Reading Assessment Conference Card page
And I select a ${class} from the class dropdown
And I select a ${time_period} from the time period dropdown
Then I click the view button
And I click on student ${student_name}
And a popup window for the student should display
Then I fill out the input requested
And select the dropdown values requested
And click the save button
And should see the results I saved on the Reading Assessment Conference page
Then I assessed the Reading Assessment Conference page

Examples:
|userType|class|time_period|student_name|
|Teacher|English|Beginning of Year|John Smith|
```

##### I want to see Resources

```gherkin
${preconditions}
And I click the Resources Card
Then I should be on Resources page
And click the title ${title_name} of a given resource
And confirm the title has been downloaded
Then I have been on the Resources page


Examples:
|userType|title_name|
|Teacher|Animal Homes Answer Key|
```

##### I want to see the Admin Report Page

```gherkin
${preconditions}
And I click the Admin Reports Card
Then I should be on Admin Reports page
And click the Reports link on header
Then I have been on the Report Page

Examples:
|userType|credentials|
|Admin|{ username, password } |
```

##### I want to see the Admin Summary Progress Report Page

```gherkin
${preconditions}
And I click the Admin Reports Card
Then I should be on Admin Reports page
And I click the Summary Progress Report Card
Then I should be on Summary Progress Report page
And select the year ${year_value} from the year dropdown
And select the school ${school_value} from the school dropdown
And select the teacher ${teacher_value} from the teacher dropdown
And select the class ${class_value} from the class dropdown
And click the view button
And can confirm the data I selected is displaying what I picked
Then I have been on the Admin Summary Progress Report Page


Examples:
|userType|credentials|year_value|school_value|teacher_value| class_value|
|Admin|{ username, password }|2016-2017|All Schools|All Teachers| All Classes|
```
##### I want to see the Admin Reading Benchmark Report Page

```gherkin
${preconditions}
And I click the Admin Reports Card
Then I should be on Admin Reports page
And I click the Reading Benchmark Report Card
Then I should be on Reading Benchmark Report page
And select the year ${year_value} from the year dropdown
And select the school ${school_value} from the school dropdown
And select the teacher ${teacher_value} from the teacher dropdown
And select the class ${class_value} from the class dropdown
And click the view button
And can confirm the data I selected is displaying what I picked
Then I have been on the Reading Benchmark Report Page


Examples:
|userType|credentials|year_value|school_value|teacher_value| class_value|
|Admin|{ username, password }|2016-2017|All Schools|All Teachers| All Classes|
```
