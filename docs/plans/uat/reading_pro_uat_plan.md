# User Acceptance Tests

## Overview

### Authors

| Name | Email |
| --- | --- |
| Grace Clifford | <gclifford@scholastic.com> |
| Sajjad Hossain | <shossain@scholastic.com> |

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
| Lytton, Alison  | <ALytton@Scholastic.com> |
| Chaudhary, Chanda | <CChaudhary-consultant@Scholastic.com> |
| Mane, Dattaram | <DMane-consultant@Scholastic.com> |
| Nadgar, DJ | <DNadgar-consultant@Scholastic.com> |
| Stoltze, Emma | <EStoltze@Scholastic.com> |
| Krangel, Eric | <EKrangel@Scholastic.com> |
| Clifford, Grace | <gclifford@scholastic.com> |
| Vaidya, Jeanny | <JVaidya-temp@Scholastic.com> |
| Ying, Jiayi | <JYing@Scholastic.com> |
| Palmer, John | <JPalmer@Scholastic.com> |
| Caicedo, Linda | <LCaicedo-consultant@Scholastic.com> |
| Jain, Palak | <PJain-consultant@Scholastic.com> |
| Hossain, Sajjad | <shossain@scholastic.com> |
| Vuppu, Sirisha | <SVuppu-consultant@Scholastic.com> |
| Morgan, Tucker | <TMorgan@Scholastic.com> |
| Lolla, Vamsidhar | <vLolla-consultant@Scholastic.com> |
| Efremovski, Velimir | <VEfremovski@Scholastic.com> |
| Reddy, Rajender | <RReddy-consultant@Scholastic.com> |
| Palmer, Diane | <DPalmer@Scholastic.com> |
| Chen, Jenhau | <JChen@Scholastic.com> |
| Artin, Megan | <MArtin-consultant@Scholastic.com> |
| Narala, Sivarami | <SNarala-consultant@Scholastic.com> |
| Kumar, Udesh | <UKumar-consultant@Scholastic.com> |
| Athrey, Vinod | <VAthrey-consultant@Scholastic.com> |
| Nagaraju, Bhagirathi | <BNagaraju-consultant@Scholastic.com> |
| Cherrington, Janelle | <JCherrington@Scholastic.com> |
| Schoss, Josepha | <JSchoss@Scholastic.com> |
| Rajendran, Kausthubh | <KRajendran-consultant@Scholastic.com> |
| Claiborne, Mike | <MClaiborne@Scholastic.com> |
| Krants, Paul | <PKrants-consultant@Scholastic.com> |


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

### Known Defects

| JIRA | Notes |
| --- | --- |
| [EXAMPLE-88]() | User's without admin assessments cannot sign in |

### Risks

1. Known defects are not listed
2. Schedule is not finalized
3. Stories tested under UAT do not include functional tests

### Schedule

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

### Epics

1. I want to use the home page
2. I want to use the Recommended Reading List
3. I want to use Search and Search Results
4. I want to use My Results
5. I want to take a Reading Pro test
6. I want to take a Book Quiz

## Test Cases

## `${preconditions}` 

```
Given I am on Reading Pro
And I am a Student
And I have my assessments
And I go to my school
And I have my products
```

### I want to use the home page

```gherkin
As a student
I want to use the home page
So that I can access tools and applications
```

#### Scenarios

1. I want to see Scholastic Branding and Logo
2. I want to see the SDM widget
3. I want to see the Navigation Bar
4. I want to see the Welcome Message
5. I want to see My Guided Reading Level
6. I want to see Reading Interests messages
7. I want to see Reading Interests icons
8. I want to see Create My Reading List button

#### Stories

##### I want to see Scholastic Branding and Logo

```gherkin
${preconditions}
Then I should see the Scholastic Logo
And it should be in the upper left corner
And I should see the 
```

	
##### I want to see the SDM widget

```gherkin
${preconditions}
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
	
##### I want to see the Navigation Bar

```gherkin
${preconditions}
Then I should see Home
And I should see Search
And I should see My Results
And if class has been set by teacher
And I should see Reading Pro Test
```

##### I want to see the Welcome Message

```gherkin
${preconditions}
Then I should see 'Hi, ${studentFirstName}!'
```

##### I want to see My Guided Reading Level

```gherkin
${preconditions}
Then I should see My Guided Reading Level
And if this is my first time in this view
Then My Guided Reading Level should be blank
```

##### I want to see Reading Interests messages

```gherkin
${preconditions}
And if this is my first time in this view
Then I should see ${message}
And it should be below student welcome message
```

##### I want to see Reading Interests icons

```gherkin
${preconditions}
Then I should see upto 20 Reading Interest icons
When I click on an icon
Then the icon should be checked
When I click a checked icon
Then the icon should be un-cheecked
If I clicked an icon more than 3 times
Then I should not see any checks
```

##### I want to see Create My Reading List button

```gherkin
${preconditions}
Then I should see Create My Reading List button
And it should be below Reading Icons
```

### I want to use the Recommended Reading List

```gherkin
As a student
I want to use the Recommended Reading List
So that I can access recommended content
```

#### Scenarios

1. I want to see My Guided Reading Level
2. I want to see Certificate Level
3. I want to see Quizzes Passed
4. I want to see Words Read
5. I want to see Average Quiz Score
6. I want to see My Reading Interests
7. I want to edit My Reading Interests
8. I want to see My Reading List

#### Stories

##### I want to see My Guided Reading Level

```gherkin
${preconditions}
Then I should see My Lexile
And it should be empty by default
```

##### I want to see Certificate Level

```gherkin
${preconditions}
Then I should see My Lexile
And I should see Certificate Level
And it should display a hyphen by default
```

##### I want to see Quizzes Passed

```gherkin
${preconditions}
Then I should see My Lexile
And I should see Quizzes Passed
And it should be 0 by default
When I take a quiz
And I pass my quiz
Then I should see my grade
```

##### I want to see Words Read

```gherkin
${preconditions}
And I've read ${books}
Then I should see My Lexile
And I should see Words Read
And it should be 0 by default
When I read a book
Then I should see number of words read
```

##### I want to see Average Quiz Score

```gherkin
${preconditions}
Then I should see My Lexile
And I should see Average Quiz Score
And it should be 0% by default
When I take a quiz
Then I should the average of all my tests scored
```

##### I want to see My Reading Interests

```gherkin
${preconditions}
Then I should see My Lexile
And I should see My Reading Interests
And I should see up to 3 icons
```

##### I want to edit My Reading Interests

```gherkin
${preconditions}
And I chose my ${readingInterests}
Then I should see My Lexile
And I should see My Reading Interests
And I should see up to 3 icons
When I choose 3 new icons
And I press Update My Reading List
Then I should see my new Reading List
```

##### I want to see My Reading List

```gherkin
${preconditions}
And I chose my ${readingInterests}
Then I should see My Lexile
And I should see 'Here are some books you might like to read'
And I should see 'Recommended'
And I should see 'Fast Find'
And I should see 'What's New'
When I mouse over information buttion
Then the information modal apperars
When I click a tab
Then I should see ${books}
And I should see ${bookCovers}
And I should see ${bookTitles}
And I should see ${bookSummaries}
And I should see ${bookAuthors}
If there is a Guided Reading Level or Lexile for ${book}
Then I should see it below the authors name
And I should see ${wordCount} below Lexile
And I should see ${readingInterestCategories} below summary
And I should see Take Quiz button
When I click Take Quiz
Then I should see a modal with a quiz for that title
When I close the modal
And I click List View icon
Then I should see a table of books
And I should see ${columnHeaders}
When I click ${columnHeader}
Then the table should be sorted by the column values descending
When I click ${columnHeader}
Then the table should be sorted by the column values ascending
```

### I want to use Search and Search Results

```gherkin
As a student
I want to use Search
So that I can filter content by custom search criteria
```

#### Scenarios

1. I want to see the Search Bar
2. I want to see Search filter options
3. I want to use Search filter options
4. I want to use Search
5. I want to Search by Reading Interests

#### Stories

##### I want to see the Search Bar

```gherkin
${preconditions}
Then I should see the search bar
And I should see the search button
And I should see search filters
```

##### I want to see Search filter options

```gherkin
Given I am on '/'
And I have my assessments
And I go to my school
And I have my products
Then I should see the search bar
And I should see search filters
And I should see 'Books with Quizzes Only'
And I should see 'At My Reading Level'
And I should see 'In My School Library'
And I should see 'eBooks Only'
```

##### I want to use Search filter options

```gherkin
${preconditions}
Then I should see the search bar
And I should see search filters
When I click ${searchFilter}
Then I should see results filtered by ${filter}
```

##### I want to use Search

```gherkin
${preconditions}
Then I should see the search bar
And I should see search filters
When I fill in search with ${searchTerm}
Then I should see ${results}
And I should see ${books}
And I should see ${bookCovers}
And I should see ${bookTitles}
And I should see ${bookSummaries}
And I should see ${bookAuthors}
If there is a Guided Reading Level or Lexile for ${book}
Then I should see it to the right of the book title
And I should see ${wordCount} to the right of Lexile
And I should see Take Quiz button
When I click List View icon
Then I should see a table of books
And I should see ${columnHeaders}
When I click ${columnHeader}
Then the table should be sorted by the column values descending
When I click ${columnHeader}
Then the table should be sorted by the column values ascending
```

##### I want to Search by Reading Interests

```gherkin
${preconditions}
Then I should see the search bar
And I should see the Reading Interests link
When I follow Reading Interests
Then I should see upto 20 Reading Interest icons
And I should see Search button
When I click on an icon
Then the icon should be checked
When I click a checked icon
Then the icon should be un-cheecked
When I select my ${readingInterests}
And I press the Search Button 
Then I should be on the Search Results page
And I should see 'Selected reading interests'
And I should see my ${readingInterests} at the top of my results
And I should see search ordered ${byReadingInterests}
And I should see ${books}
And I should see ${bookCovers}
And I should see ${bookTitles}
And I should see ${bookSummaries}
And I should see ${bookAuthors}
If there is a Guided Reading Level or Lexile for ${book}
Then I should see it to the right of the book title
And I should see ${wordCount} to the right of Lexile
And I should see Take Quiz button
When I click List View icon
Then I should see a table of books
And I should see ${columnHeaders}
When I click ${columnHeader}
Then the table should be sorted by the column values descending
When I click ${columnHeader}
Then the table should be sorted by the column values ascending
```

### I want to use My Results

```gherkin
As a student
I want to use My Results
So that I can view results filtered by search criteria
```

#### Scenarios

1. I want to see my statistics
2. I want to view a list of books I've read

#### Stories

##### I want to see my statistics

```gherkin
${preconditions}
Then I should see my statistics
And I should see My Guided Reading
And I should see Certificate Level
And I should see Quizzes Passed
And I should see Words Read
And I should see Average Quiz Score
```

##### I want to view a list of books I've read

```gherkin
${preconditions}
Then I should see List of Books I've Read
And I should see ${books}
And I should see ${bookCovers}
And I should see ${bookTitles}
And I should see ${bookSummaries}
And I should see ${bookAuthors}
And I should see ${bookWordCount}
And I should see ${bookPoints}
And I should see ${bookDate}
```


### I want to take a Reading Pro test

```gherkin
As a student
I want to take a Reading Pro test
So that my reading level can be assessed and graded
```

#### Scenarios

1. I want to see a welcome message
2. I want to start and pause the test
3. I want to practice a test
4. I want to skip a question
5. I want to complete a test

#### Stories

##### I want to see a welcome message

```gherkin
${preconditions}
Then I should see Let's Get Started button
When I press Let's Get Started
Then I should see a modal
And I should see my first name
And I should see instructions
And I should see a close button
When I press close button
Then I should not see the modal
```

##### I want to start and pause the test

```gherkin
${preconditions}
Then I should see Let's Get Started button
When I press Let's Get Started
Then I should see a multiple choice question
And I should see a Next button 
And the Next button should be disabled
When I select an answer
Then the Next button should not be disabled
When I click Next
Then I should be on another question
When I press close
Then I should see a confirm dialog
And I should see 'Your test will be paused so you can resume later'
When I confirm the pop-up
Then I should not see the modal
```

##### I want to practice a test

```gherkin
${preconditions}
And the teacher required a practice test for the class
When I answer both questions
Then I should see 'You have completed the practice test. All questions you answer from now on will be counted toward your Lexile measure.'
When I press Go On
Then I should be on another question
```

##### I want to skip a question

```gherkin
${preconditions}
And I am on a Reading Pro Test
Then I should see Skip button
And I should see the maximum amount of skips allowed
When I press Skip
Then I should be on the next question
When I reachg the maximum amount of skips
Then the Skip button should be disabled
```

##### I want to complete a test

```gherkin
${preconditions}
And the teacher chose to share Lexile results
And I am on a Reading Pro Test
And I answered all the questions
Then I should see a completion message
And I should see an exit button
And I should see Create Reading List button
And I should see my Lexile updated with my score(s)
```

### I want to take a Book Quiz

```gherkin
As a student
I want to take a Book Quiz
So that my reading comprehension for that title can be assessed
```

#### Scenarios

1. I want to take a Book Quiz
2. I want to press Next
3. I want to Finish a Book Quiz
2. I want to view statistics based on my quiz results

#### Stories

##### I want to take a Book Quiz

```gherkin
${preconditions}
Then I should see Take Quiz button
And I should see ${quizzes}
And I should see 'Quizzes for ' + ${bookTitle}
And I should see close button
And I should see ${bookTitle}
When I press Take Quiz
Then I should see my first name
And I should see 'This is the quiz for ' + ${bookTitle}
And I should see multiple choice questions
And I should see short answer questions
And I should see Exit Quiz button
When I press Exit Quiz
Then I should see a warning dialog
And I should see 'Exiting a quiz will be counted as an attempt. Are you sure you want to exit?' 
When I confirm the dialog
Then I should see ${tryAgainLaterMessage}
And I should see ${bookTitle}
And I should see ${bookAuthor}
And I should see my grade
And I should see right:wrong ratio
And I should see View Incorrect Answers button
And I should see Done button
When I press Done
Then I should not see the modal
```

##### I want to press Next

```gherkin
Given I am on a book quiz
Then I should see my first name
And I should see 'This is the quiz for ' + ${bookTitle}
And I should see multiple choice questions
And I should see short answer questions
And I should see Exit Quiz button
And the Next button should be disabled
When I select an answer
Then the Next button should not be disabled
When I click Next
Then I should be on another question
```

##### I want to Finish a Book Quiz

```gherkin
Given I am on a book quiz
And I am on the second to last question
Then I should see the Next button
And the Next button should be disabled
When I select an answer
Then the Next button should not be disabled
When I click Next
Then I should see ${completionMessage}
And I should see ${tryAgainLaterMessage}
And I should see ${bookTitle}
And I should see ${bookAuthor}
And I should see my grade
And I should see right:wrong ratio
And I should see View Incorrect Answers button
And I should see the feedback section
And I should see 'Loved It!'
And I should see 'Liked It!'
And I should see 'Okay'
And I should see 'Not Great'
And I should see 'Leave It'
When I click ${feedbackOption}
Then the button should be green
And I should see a comment field
When I fill in comment with ${comment}
Then I should see ${comment}
And I should see Done button
When I press Done
Then I should not see the modal
```


##### I want to view statistics based on my quiz results

```gherkin
${preconditions}
And I finished ${bookQuiz}
When I close the modal
Then I should see my statistics and quiz results
And I should see my Lexile updated with my score(s)
```
