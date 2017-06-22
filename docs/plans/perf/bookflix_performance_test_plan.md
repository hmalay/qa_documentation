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
| 06/12/17 | 1.0 |
| 06/22/17 | 1.1 |

### Scope

The scope of this test plan only extends extends itself to Performance Testing for Environment Promotion. If these tests fail, then there are major, critical bugs to resolve for performance and system requirements to meet expectations.

### Abstract

BookFlix is an online literacy resource that pairs classic video storybooks from Weston Woods with related nonfiction eBooks from Scholastic to build a love of reading and learning. An engaging way to link fact and fiction, BookFlix reinforces early reading skills and introduces children to a world of knowledge and exploration.


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
| Bruce Grogan	| <bgrogan@scholastic.com> |
| Deanna Rullan | <drullan-consultant@scholastic.com> |

#### Tools


* [MySQL](https://dev.mysql.com/downloads/mysql/)
* [BitBucket](https://bitbucket.org)
* [PHP 8](http://php.net/manual/en/intro-whatis.php)

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
|  |  |

### Risks

1. Known defects are not identified


### Load Model

| Application | User | Scenario | User Agent | Page Visits |
| --- | --- | --- | --- | --- |
| BookFlix | Teacher | I want to see the Watch the Story Page | Browser | 6500 |
| "" | "" | I want to see the Read the Book Page | "" | "" |
| "" | "" | I want to see the Puzzlers Page | "" | "" |
| "" | "" | I want to play the Word Match puzzle game  | "" | "" |
| "" | "" | I want to play the Fact or Fiction puzzle game  | "" | "" |
| "" | "" | I want to play the Which Came First puzzle game  | "" | "" |
| "" | "" | I want to see Meet the Author Page  | "" | "" |
| "" | "" | I want to see Explore the Web Page  | "" | "" |
| "" | "" | I want to see the Help Page  | "" | "" |
| "" | "" | I want to see the Resources Page  | "" | "" |


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
Given I am on Bookflix
And I am a ${userType}
Then I should be on Scholastic Digital Manager
And I should see the log in form
When I fill in the log in form with ${credentials}
And I submit the log in form
Then I should see the Bookflix icon
When I launch Bookflix
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

1. I want to see the Watch the Story Page
2. I want to see the Read the Book Page
3. I want to see the Puzzlers Page
4. I want to play the Word Match puzzle game
5. I want to play the Fact or Fiction puzzle game 
6. I want to play the Which Came First puzzle game 
7. I want to see Meet the Author Page
8. I want to see Explore the Web Page
9. I want to see the Help Page 
10. I want to see the Resources Page 


#### Stories

##### I want to see the Watch the Story Page 

```gherkin
${preconditions}
And I click the feature pair logo on the home page 
Then I click the Watch the Story link on the left nav 
And I should see a video playing 
Then I can confirm the Watch The Story page is functioning correctly 

Examples:
| userType  | credentials| 
| Teacher   | { username, password } |
```

##### I want to see the Read the Book page

```gherkin
${preconditions}
And I click the feature pair logo on the home page
Then I click the Read the Book link on the left nav 
And I click through the book preseneted on the page 
Then I can confirm the Read The Book page is functioning correctly 

Examples:
| userType  | credentials|
| Teacher   | { username, password } |
```

##### I want to see the Puzzlers page 

```gherkin
${preconditions}
And I click the feature pair logo on the home page 
Then I click the Puzzlers link on the left nav 
And I should be on the Puzzlers page 
And I should see three links named Word Match, Fact or Fiction or Which Came First
And I click each one 
And determine if they took me to the correct puzzle page
Then I can confirm the Puzzlers page is functioning correctly 

Examples:
| userType  | credentials| 
| Teacher   | { username, password } |
```

##### I want to play the Word Match puzzle game

```gherkin
${preconditions}
And I click the feature pair logo on the home page 
Then I click the Puzzlers link on the left nav 
When I click the Word Match link 
Then I should be on the Word Match puzzle page 
And I start playing the Word Match puzzle game 
Then I can confirm the Word Match puzzle game is functioning correctly

Examples:
| userType  | credentials|
| Teacher   | { username, password } | 
```

##### I want to play the Fact or Fiction puzzle game

```gherkin
${preconditions}
And I click the feature pair logo on the home page 
Then I click the Puzzlers link on the left nav 
When I click the Fact or Fiction link 
Then I should be on the Fact or Ficition puzzle page 
And I start playing the Fact or Fiction puzzle game 
Then I can confirm the Fact or Fiction puzzle game is functioning correctly

Examples:
| userType  | credentials| 
| Teacher   | { username, password } |
```

##### I want to play the Which Came First puzzle game

```gherkin
${preconditions}
And I click the feature pair logo on the home page 
Then I click the Puzzlers link on the left nav 
When I click the Which Came First link 
Then I should be on the Which Came First puzzle page 
And I start playing the Which Came First puzzle game 
Then I can confirm the Which Came First puzzle game is functioning correctly

Examples:
| userType  | credentials| 
| Teacher   | { username, password } | 
```


##### I want to see the Meet the Author Page 

```gherkin
${preconditions}
And I click the feature pair logo on the home page 
Then I click the Meet the Author link on the left nav 
And I should see text about the author for the specific book 
Then I can confirm the Meet the Author page is functioning correctly 

Examples:
| userType | credentials|
| Teacher	 | { username, password } |
```

##### I want to see the Explore the Web Page 

```gherkin
${preconditions}
And I click the feature pair logo on the home page 
Then I click the Explore the Web link on the left nav 
And I should see certain urls/text on the Explore the Web page 
Then I can confirm the Explore the Web page is functioning correctly 

Examples:
| userType | credentials|
| Teacher  | { username, password } |
```

##### I want to see the Help Page 

```gherkin
${preconditions}
And I click the Help link on the header 
And I should be on the Help page
And I should see certain urls/text related to help on Bookflix 
Then I can confirm I've seen the Help page 

Examples:
| userType | credentials|
| Teacher  | { username, password } |
```

##### I want to see the Resources Page 

```gherkin
${preconditions}
And I click the Resources link on the header 
And I should be on the Resources page
And I click on the different tabs on the Resources page 
And I should see certain text for that particular tab I click
Then I can confirm I've seen the Resources page 

Examples:
| userType | credentials|
| Teacher  | { username, password } |
```