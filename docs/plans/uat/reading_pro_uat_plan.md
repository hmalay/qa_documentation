# User Acceptance Tests

For `Reading Pro`

## Overview

### Authors

| Name | Email |
| --- | --- |
| Grace Clifford | gclifford@scholastic.com |
| Sajjad Hossain | shossain@scholastic.com |

### Vesions
| Date | Version |
| --- | --- |
| 03/26/17 | 1.0 |
| 04/09/17 | 1.1 |

### Scope

The scope of this test plan only extends extends itself to User Acceptance Testing for Production Promotion. If these tests fail, then there are major, critical bugs to resolve for Reading Pro.

### Abstract

Scholastic Reading Pro Library is a browser-based eBook reader for students. Reading Pro Libraryallows students to select eBooks from the online library collection and read them in an eBook Viewer. Students keep their eBooks in their own custom bookshelf area. Studentsalso havean online profile showing their Lexile measure, books read, and other important reading data.

### Requirements

#### Software

##### Operating Systems

* Mac OS
* Linux OS
* or Windows OS

##### Browsers/Webkits

| Browser/Webkit | Minimum Version |
| --- | --- |
| | |


#### Environments

* LOCAL (DEV)
* DEV
* QA
* PRODUCTION

#### Personnel

* Grace Clifford
* Chanda Chaudhary
* Srisha Vuppu
* Sajjad Hossain

#### Tools

* [Eclipse](http://www.eclipse.org/downloads/packages/eclipse-ide-java-ee-developers/neon2)
* [Java 8](http://www.oracle.com/technetwork/pt/java/javase/downloads/jdk8-downloads-2133151.html)
* [Widefly](http://wildfly.org/downloads/)
* [MySQL](https://dev.mysql.com/downloads/mysql/)
* [MySQL Workbench](https://downloads.mysql.com/archives/workbench/)
* [SourceTree](https://www.sourcetreeapp.com/)
* [BitBucket](https://bitbucket.org)

### Acceptance Criteria

The acceptance criteria for this test plan extends itself to only surface-level interaction with the application and its main views.

The below epics and stories should pass in the all browsers and webkits defined.

## Students

### Epic(s)

1. I want to use the home page
2. I want to use the home page with Recommended Reading List

### Stories

1. I want to see Scholastic Branding and Logo
2. I want to see the SDM widget
3. I want to see the Navigation Bar
4. I want to see the Welcome Message
5. I want to see My Guided Reading Level
6. I want to see Reading Interests messages
7. I want to see Reading Interests icons
8. I want to see Create My Reading List button

## Scenarios

### I want to use the home page

```gherkin
As a student
I want to use the home page
So that I can access tools and applications
```

#### I want to see Scholastic Branding and Logo

```gherkin
Given I am on '/'
And I have my permissions
And I go to my school
And I have my products
Then I should see the Scholastic Logo
And it should be in the upper left corner
```

	
#### I want to see the SDM widget

```gherkin
Given I am on '/'
And I have my permissions
And I go to my school
And I have my products
Then I should see the SMD widget
When I mouse over my name
Then I should see the log out link
When I mouse over the widget grid
Then I should see:
	The name of the school
	Scholastic Digital Manager Logo
	Other Products
When I click Scholastic Digital Manager Logo
Then I should be on SDM Portal Page
When I click on another product
Then the other application should open
```
	
#### I want to see the Navigation Bar

```gherkin
Given I am on '/'
And I have my permissions
And I go to my school
And I have my products
Then I should see Home
And I should see Search
And I should see My Results
And if class has been set by teacher
And I should see Reading Pro Test
```

#### I want to see the Welcome Message

```gherkin
Given I am on '/'
And I have my permissions
And I go to my school
And I have my products
Then I should see 'Hi, ${studentFirstName}!'
```

#### I want to see My Guided Reading Level

```gherkin
Given I am on '/'
And I have my permissions
And I go to my school
And I have my products
Then I should see My Guided Reading Level
And if this is my first time in this view
Then My Guided Reading Level should be blank
```

#### I want to see Reading Interests messages

```gherkin
Given I am on '/'
And I have my permissions
And I go to my school
And I have my products
And if this is my first time in this view
Then I should see ${message}
And it should be below student welcome message
```

#### I want to see Reading Interests icons

```gherkin
Given I am on '/'
And I have my permissions
And I go to my school
And I have my products
Then I should see upto 20 Reading Interest icons
When I click on an icon
Then the icon should be checked
When I click a checked icon
Then the icon should be un-cheecked
If I clicked an icon more than 3 times
Then I should not see any checks
```

#### I want to see Create My Reading List button

```gherkin
Given I am on '/'
And I have my permissions
And I go to my school
And I have my products
Then I should see Create My Reading List button
And it should be below Reading Icons
```

#### I want to use the home page with Recommended Reading List

```gherkin
As a student
I want to use the Recommended Reading List
So that I can access recommended content
```

## Schedule

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