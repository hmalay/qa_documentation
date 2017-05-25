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

### Scope

The scope of this test plan only extends extends itself to Performance Testing for Environment Promotion. If these tests fail, then there are major, critical bugs to resolve for performance and system requirements to meet expectations.

### Abstract

Level Bookroom Accelerator (LBA) is a digital tool to help educators keep bookrooms organized and have access to instructional planning. 

The Leveled Bookroom Accelerator is an instructional tool and will be integrated into Scholastic’s core delivery platform, SDM (Scholastic Digital Manager).  While Scholastic will be working with vendors to develop features of the LBA, it will need to be developed via the specifications of Scholastic’s Internal Product Development Teams.

Project Process & tools will need to be agreed to across three core areas: 

* **New Content Production**: New instructional content for the program will be developed for both print and digital usage.  Workflows will need to be carefully coordinated across channels to maximize efficiency.
* **Digital Content Conversion**: We will want to build an enhanced experience for the teacher materials that leverages existing XML content & metadata as well as enhancements to existing print only materials.  
* **Application Development**: Features and experiences meant to enhance the content or experience of using the leveled bookroom accelerator.  
* Site will be a responsive Angular App that supports select content down to a Phone Aspect Ratio
* Initial launch is limited to Educator roles, not students or parents, although we may display class information
* User Profile, Registration, and License details would all be managed via Scholastic Digital Manager
* Rostering would be managed via Clever
* Content and data served in LBA could be integrated with Scholastic’s ecosystem and tools; including but not limited to:
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
* BUILD
* DEV
* QA
* PRODUCTION

#### Personnel

| Name | Email |
| --- | --- |
| Megan Artin	| <martin-consultant@scholastic.com> |
| Deanna Rullan | <drullan-consultant@scholastic.com> |
| Adam Young	| <ayoung-consultant@scholastic.com> |
| Alex (Oleksiy) Deverishchev | <AlDeverishchev-consultant@scholastic.com> |
| Jessie Dib | <JeDib-consultant@Scholastic.com> |
| Caitlin Endyke	| <caitlin@sosbrooklyn.com> | 
| Miriam Kasell | <mkasell-consultant@scholastic.com> |
| Sean Oakes | <soakes-consultant@scholastic.com> |
| David Langendoen | <DLangendoen-consultant@Scholastic.com> |


#### Tools

* [Eclipse](http://www.eclipse.org/downloads/packages/eclipse-ide-java-ee-developers/neon2)
* [Java 8](http://www.oracle.com/technetwork/pt/java/javase/downloads/jdk8-downloads-2133151.html)
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
| [EXAMPLE-88]() | Example: User's without admin assessments cannot sign in |

### Risks

1. Known defects are not listed
2. Schedule is not finalized
3. Stories tested under UAT do not include functional tests

### Schedule

| Task Name | Duration (days) | Start | Finish |
| --- | --- | --- | --- |
| Review and Finalize Plan | 3 | 05/23/2017 | 05/25/2017 |
| Dress Rehearsal | 1 | 05/23/2017 | 05/25/2017 |
| Test Scripting | 3 | 05/25/2017 | MM/DD/YYYY |
| Delta Testing | 1 | MM/DD/YYYY | MM/DD/YYYY |
| Theta Testing | 1 | MM/DD/YYYY | MM/DD/YYYY |
| Beta Testing | 1 | MM/DD/YYYY | MM/DD/YYYY |
| Alpha Testing | 1 | MM/DD/YYYY | MM/DD/YYYY |

### Tests

| Test Name | Description |
| --- | --- |
| Dress Rehearsal | This will test the JMeter installation and make sure that requests sent from JMeter is properly recieved by the system under test |
| Delta Testing | These tests will be executed as a baseline for up to an hour. |
| Theta Testing | Similar to the theta tests, these tests will use the same scrips but repeat for a longer duration and if needed with higher concurrency. |
| Beta Testing | Again, similar to theta and beta testing, these tests will stress test the system with 150% - 300% of our Peak Load. |
| Alpha Testing Round 1 | Again, similar to theta and beta testing, these tests will stress test the system with 150% - 300% of our Peak Load. |
| Alpha Testing Round 2 | Re-run Alpha Tests |

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
Given I am on Leveled Bookroom Accelerator
And I am a ${userType}
Then I should be on Scholastic Digital Manager
And I should see the log in form
When I fill in the log in form with ${credentials}
And I submit the log in form
Then I should see the Leveled Bookroom Accelerator icon
When I launch Leveled Bookroom Accelerator
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

1. I want to see Reserved Titles
2. I want to see Bookmarked Titles
3. I want to see Similar Titles
4. I want to see a Teaching Card for my title
5. I want to see Resources
6. I want to see a new book added to My Set
7. I want to go Back To The Search after logging out
8. I want to log in as an Admin and go to Bookroom Manager

#### Stories

##### I want to see Reserved Titles

```gherkin
${preconditions}
And I fill in the search input with ${bookTitle}
And I submit my search query
Then I should be on search results page
And I should see my search results
When I follow ${bookTitle}
Then I should see teaching card pop-up
And I should see reserve button
When I reserve ${bookTitle}
And I close the teaching card pop-up
And I follow My Sets
And I follow Reserved Titles
Then I should see My Reserved Titles

Examples:
	| userType  | credentials 		     | bookTitle    |
	| Teacher   | { username, password } | Harry Potter |
```

##### I want to see Bookmarked Titles

```gherkin
${preconditions}
And I fill in the search input with ${bookTitle}
And I submit my search query
Then I should be on search results page
And I should see my search results
When I follow ${bookTitle}
Then I should see teaching card pop-up
And I should see bookmark button
When I bookmark ${bookTitle}
And I close the teaching card pop-up
And I follow My Sets
And I follow Bookmarked Titles
Then I should see My Bookmarked Titles

Examples:
	| userType  | credentials 		     | bookTitle    |
	| Teacher   | { username, password } | Harry Potter |
```

##### I want to see Similar Titles

```gherkin
${preconditions}
And I fill in the search input with ${bookTitle}
And I submit my search query
Then I should be on search results page
And I should see my search results
When I follow ${bookTitle}
Then I should see teaching card pop-up
And I should see search for similar button
When I search for books similar to ${bookTitle}
And I follow ${similarBookTitle}

Examples:
	| userType  | credentials 		     | bookTitle    | similarBookTitle |
	| Teacher   | { username, password } | Harry Potter | Lemony Snicket   |
```

##### I want to see a Teaching Card for my title

```gherkin
${preconditions}
And I fill in the search input with ${bookTitle}
And I submit my search query
Then I should be on search results page
And I should see my search results
When I follow ${bookTitle}
Then I should see teaching card pop-up
And I should see teaching card pop-up elements

Examples:
	| userType  | credentials 		     | bookTitle    |
	| Teacher   | { username, password } | Harry Potter |
```

##### I want to see a new book added to My Set

```gherkin
${preconditions}
And I fill in the search input with ${bookTitle}
And I submit my search query
Then I should be on search results page
And I should see my search results
When I follow ${bookTitle}
Then I should see teaching card pop-up
And I should see add to set button
When I press add to set button
And I select my set from the dropdown
And I close the teaching card pop-up
And I follow My Sets
And I follow Bookmarked Titles
Then I should see ${bookTitle} in My Set

Examples:
	| userType  | credentials 		     | bookTitle    |
	| Teacher   | { username, password } | Harry Potter |
```

##### I want to go Back To The Search after logging out

```gherkin
${preconditions}
And I fill in the search input with ${bookTitle}
And I submit my search query
Then I should be on search results page
And I should see my search results
When I follow ${bookTitle}
Then I should see teaching card pop-up
When I log out via the header
Then I should be on Scholastic Digital Manager
And I should see the log in form
When I fill in the log in form with ${credentials}
And I submit the log in form
Then I should be on the home page
And I should see jump back in button
When I press jump back in button
Then I should be returned to my previous search

Examples:
	| userType  | credentials 		     | bookTitle    |
	| Teacher   | { username, password } | Harry Potter |
```

##### I want to log in as an Admin and go to Bookroom Manager

```gherkin
${preconditions}
Then I should be on Bookroom Manager

Examples:
	| userType | credentials 		    |
	| Admin	   | { username, password } |
```

