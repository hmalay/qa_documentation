#Prism Ad - Test Plan


##Project Scope
This is the first ad type of its kind, so a description doesn't exist. However, the team created a minimalist [UX Guideline](https://docs.google.com/a/adcade.com/document/d/1GQHTJfRLYxP09BIxQrRU3Ft7HvyhUxUbIBKTNfX_rB4/edit).

The prism is a 6-sided cube. Currently the functionality is limited to left/right. Development is being done on making the prism up/down functional. When the user swipes, drags or taps & drags the frame in a direction, the animation will reveal the next side/frame. If the users stops swiping mid-transition, the side most revealed will be active in the iframe. 

The tickets below cover the basic building blocks and framework necessary to make this prism render and functional (limited to left/right and 4-sides):

* [ADSCR-534](https://adcade.atlassian.net/browse/ADSCR-534)
* [ADSCR-524](https://adcade.atlassian.net/browse/ADSCR-524)

##Test Scope
This feature is still in beta. The functionality below, from the [UX Guideline](https://docs.google.com/a/adcade.com/document/d/1GQHTJfRLYxP09BIxQrRU3Ft7HvyhUxUbIBKTNfX_rB4/edit) are not included in this preview. The below functionality are scenarios unique to a client or campaign. For instance, if an organization want an ad with a menu, then and only then will the menu be active.

These functionality will **NOT** be previewed currently:

1. Unit will play an intro animation highlighting the various screens, order customizable
2. After intro animation, unit will use ambient motion to aid in attracting eyes to the unit. 
3. Included in UI of all prism units - Menu button that bring up overlay listing the sections of the unit for quick navigation.
4. Using gyroscope/accelerometer user will be encouraged to rotate device to navigate to facets.


This test plan is limited to testing:

* Ensuring elements are rendered
* On mobile devices, swiping left takes user to the right frame. 
* On mobile devices, swiping right takes the user to the left frame. 
* On mobile devices, users are only allowed to view one frame at a time.
* On desktop, tapping, & dragging left, keeps the prism rotating to the right.
* On desktop, tapping, & dragging right, keeps the prism rotating to the left.
* Tapping and dragging in any direction is limited to the width of the browser.
* On desktop, swiping left takes the user to the right frame.
* On desktop, swiping right takes the user to the left frame.

###Test Environment
This test will be executed `locally`.

###Test Requirements
This document assumes that you've read & installed [front-end requirements](https://adcade.atlassian.net/wiki/display/FD/Front+End+Onboarding).
####Operating System Requirements
* `Mac OS X 10.4.x` and up
* `Windows 2000` and up
* `iOS 6.x` and up
* `Android 4.1.x`  and up

####Browser Requirements
* `Internet Explorer 8` and up 
* `Firefox 34.0.x` and up
* `Chrome 39.0.x` and up
* `Safari 6.x` and up

####Software Requirements
* `Charles` Debugging Software [(link)](http://www.charlesproxy.com/)

###Repository Requirements
* `fe_sandbox`; branch `3.8.0-rc.2`
* `product2`; branch `3.8.0-rc.2`


###Test Types
Includes both [Agnostic](#agnostic) and [Specific](#specific) test types. For Example, to test that an end point is available, they undergo a set of standard expectation criteria. Similarly, these ad's may have their own unique functionality and conditions.

| Type | Description |
| --- | --- |
| Black-Box | Internal system design is not considered in this type of testing. Tests are based on requirements and functionality. |
| White -Box | This testing is based on knowledge of the internal logic of an application’s code. Also known as Glass box Testing. Internal software and code working should be known for this type of testing. Tests are based on coverage of code statements, branches, paths, conditions. |
| Functional | This type of testing ignores the internal parts and focus on the output is as per requirement or not. Black-box type testing geared to functional requirements of an application. |
| Regression | Testing the application as a whole for the modification in any module or functionality. Difficult to cover all the system in regression testing so typically automation tools are used for these testing types. |
| Usability | User-friendliness check. Application flow is tested, Can new user understand the application easily, Proper help documented whenever user stuck at any point. Basically system navigation is checked in this testing. |
| Security | Can system be penetrated by any hacking way. Testing how well the system protects against unauthorized internal or external access. Checked if system, database is safe from external attacks. |
| Compatibility | Testing how well software performs in a particular hardware/software/operating system/network environment and different combinations of above. |

####Holistic (Standard) Tests
#####HTTP Status
Use [this document](http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html) to establish what a Status Code refers to.

	AUT = "http://adcade.dev/fe-sandbox/staging/internal/brand/2014/features/prism/"
	
	As a tester  
	I want to check the status and response code of my requests  
	So that I can ensure holistic functionality of the ad  
	
		Scenario Outline: I want to check the status and response code of my requests
		Given I am on AUT
		Then I should see "AWESOME SITE BRO"  
		And my response code for <"request"> should be 304 or 200
	
For Examples used in the above scenario, see: [Prism Requests](#)

#####Console
In your `Chrome, Firefox, Safari, Internet Explorer` open `Inspect Element` or `Debugging`. Ensure page loads all assets, especially main-built.js, from `S3` with no console errors.

	AUT = "http://adcade.dev/fe-sandbox/staging/internal/brand/2014/features/prism/"
	
	As a tester  
	I want to check the browser console for errors
	So that I can ensure holistic functionality of the ad  
	
		Scenario: I want to check the browser console for errors
		Given I am on AUT
		Then I should see "AWESOME SITE BRO"  
		When I right click on the page
		And I select "Inspect Element"
		Then I should see "Inspector"
		When I press "Console"
		Then I should see "Using require-adscript.js."
		And I should see "[AdS] No background set." 
		When I click on the ad
		Then I should see a "td" element fire in console with a count
		

####Reductionist (Unique) Tests
#####Functional

	AUT = "http://adcade.dev/fe-sandbox/staging/internal/brand/2014/features/prism/"
	Frame 1 = "unique identifier for frame"
	Frame 2 = "unique identifier for frame"
	Frame 3 = "unique identifier for frame"	
	Frame 4 = "unique identifier for frame"
	All Frames = "Frame 1, Frame 2, Frame 3, Frame 4"
		
	As a tester  
	I want to check the prism functionality 
	So that I can ensure unique functionality of the ad  
	
		@mobile @prism
		Scenario: I want to check the prism functionality on mobile
		Given I am on AUT
		And I am on a mobile device
		Then I should see "AWESOME SITE BRO"  
		And I should see Frame 1
		When I right swipe left in the ad
		Then I should see Frame 2
		When I right swipe right in the ad
		Then I should see Frame 1
		When I right swipe right in the ad
		Then I should see Frame 4
		When I right swipe right in the ad
		Then I should see Frame 3	
		When I right swipe right in the ad
		Then I should see Frame 2
		When I right swipe left in the ad
		Then I should see Frame 3

		@desktop @prism	
		Scenario: I want to check the prism functionality on desktop
		Given I am on AUT
		And I am on desktop
		Then I should see "AWESOME SITE BRO"  
		And I should see Frame 1
		When I right swipe left in the ad
		Then I should see Frame 2
		When I right swipe right in the ad
		Then I should see Frame 1
		When I right swipe right in the ad
		Then I should see Frame 4
		When I right swipe right in the ad
		Then I should see Frame 3	
		When I right swipe right in the ad
		Then I should see Frame 2
		When I right swipe left in the ad
		Then I should see Frame 3
		When I drag & hold right
		Then I should see all frames
		And I should be scrolling left
		When I drag & drag left
		Then I should see all frames
		And I should be scrolling right

#####Compatibility

	AUT = "http://adcade.dev/fe-sandbox/staging/internal/brand/2014/features/prism/"
	Frame 1 = "unique identifier for frame"
	Frame 2 = "unique identifier for frame"
	Frame 3 = "unique identifier for frame"	
	Frame 4 = "unique identifier for frame"
	All Frames = "Frame 1, Frame 2, Frame 3, Frame 4"
		
	As a tester  
	I want to check the prism functionality on all major browsers
	So that I can ensure compatibility of the ad  
	
		@compatibility @prism	
		Scenario Outline: I want to check the prism functionality on all major browsers
		Given I am on AUT
		And I am on <"browser">
		Then I should see "AWESOME SITE BRO"  
		And I should see Frame 1
		When I right swipe left in the ad
		Then I should see Frame 2

Examples:

| browser |
| --- |
| OS X Safari |
| OS X Chrome |
| OS X Firefox |
| Windows Internet Explorer |
| Windows Chrome | 
| Windows Firefox |
| Windows Mobile Internet Explorer |
| iOS Safari | 
| iOS Chrome |
| Android Native Browser |
| Android Chrome |
| Android Firefox |

<div id="results"></div>
#Test Results

| Type | Test | Story | Result | Notes |
| --- | --- | --- |
| Regression | Response Code | I want to check the status and response code of my requests | Pass | n/a |
| Regression | Console | I want to check the browser console for errors | Pass | n/a |
| Functional | Prism | I want to check the prism functionality on mobile | Pass | n/a |
| Functional | Prism | I want to check the prism functionality on desktop | Pass | n/a |
| Compatibility | Browser | I want to check the prism functionality on all major browsers | Pass | n/a |
