#Regression Test Plan
##Introduction
Please see [Testing Tutorial and Guidelines](http://testweb.pw/adcadeTesting/testing/Testing_Tutorial_And_Guidelines/).

##Acceptance Criteria 
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


##Test Scope
These regression tests can apply to all/most ads. There may be scenarios that apply uniquely to the feature/ad, those are expected to be tracked in a partnering document, preferably a test plan of its own. All ads need to be tested in an S3 environment that mirrors the production environment. All interactions need to be accounted for, documented and tested throughout all stages of development. For example, the [Prism ad](http://testweb.pw/adcadeTesting/testing/Prism_Ad_Test_Plan/) unit is a new type of ad unit; stories and scenarios need to be documented that relay both functionality and expectations of the said feature. 

##Preconditions

* Latest code is checked in to stage, production or test environment(s)
* The latest `AdStack`, `IDE`, `AdScript` versions are used
* Code being tested, has been approved for the master branch and are trackable to a version
* Campaign Brief and Test Results are created and updated for duration of development, QA and deployment

##HTTP Statuses
Use [this document](http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html) to establish what a Status Code refers to. A status code is given by each request to a web app or service. Lets use [adcade.com](http://adcade.com) as an example. When I go to Adcade, I'm requesting a bunch of files from a location. 

One request to [adcade.com](http://adcade.com), includes but is not limited to calls to the below assets and files: 

	http://adcade.com
		vendor/
		fastclick/
		jquery-ui/
		jquery-mobile/
		jquery/
		angular/
		angular-bootstrap/
		placeholders/
		angular-ui-router/
		angular-ui-utils/
		angular-mocks/
		bootstrap/
		bootstrap-tree/
		bootstrap-datetimepicker/
		assets/
		img/
		demos/
		ng-boilerplate.css
		intro-background.jpg
		src/
		app/
		assets/
		common/
		templates-common.js
		templates-app.js
	https://resource.adcade.com

So to ensure Adcade is up and running, we can run an HTTP 200 OK Status Check for all the above requests as standard regression suite. We can check this using browser-side [Debugging](http://testweb.pw/adcadeTesting/testing/Testing_Tutorial_And_Guidelines/#metrics) or [Charles](http://testweb.pw/adcadeTesting/testing/Testing_Tutorial_And_Guidelines/#clickthrough-verification) to get set up and running, then ensure there are no console errors or failed requests.

Similarly, the ad should have a `HTTP 200 OK Status Check` for all calls requests apart of its' standard regression suite.

##Story Coverage
| Step | P/F | Description | Examples | Story |
| --- | --- | --- | --- | --- |
| 1 |  | Requests and demo assets load with no console errors, in/from expected-compatibility environments (i.e. main-built.js from S3). | If an ad unit is targeted **only** for native mobile browsers, then functional and regression should be focused on said environments. This scenario  ensures that the legacy required JS file is requested and rendered with no errors. |  As a tester, I want to evaluate end-points, So that regression tests pass |
| 2 |  |  All images, video, CSS, JS, and data assets are available from S3 environment and are rendered with no errors. Expected behaviors, interactions, gestures and metrics are available and usable via said host. | If an ad unit is a video interstitial, than this step ensures that not only is the video loaded, but it is rendered properly with CSS and JS restrictions applied. It also ensures that metrics are triggered and captured from a high-level. Ensures functional capability with said asset, i.e. Play Back, Volume, Full Screen, etc. |As a tester, I want to evaluate assets, So that regression tests pass |
| 3	|  |  Ad unit, [metrics](http://testweb.pw/adcadeTesting/testing/Testing_Tutorial_And_Guidelines/#metrics), and [click throughs](http://testweb.pw/adcadeTesting/testing/Testing_Tutorial_And_Guidelines/#clickthrough-verification) are using the right AdID. | All ad's have an AdID; they are available via the [campaign brief](https://docs.google.com/a/adcade.com/spreadsheet/ccc?key=0AunIV2knptx1dGdmaVJiUkRzZzZFMzJENFBZVklLb3c#gid=5). If an unit has the 'ID: 918b487b-78e7-4ff6-b097-dd3f3ddecfd8' then all resources required by the ad unit, should be requested with the AdID as a parameter. In this example, the resource request for ad-tiny is: https://ad-adstack.adcade.com/2/tiny/918b487b-78e7-4ff6-b097-dd3f3ddecfd8/pl/241266f6-9f4c-4f10-8a48-2dcf0de31844. | As a tester, I want to evaluate all requests using AdID, So that regression tests pass |
| 4 |  |  [Metrics](http://testweb.pw/adcadeTesting/testing/Testing_Tutorial_And_Guidelines/#metrics) are working as expected. | Although they may not all be mentioned and/or documented, there are metric calls pertaining to each and every ad. Whether it is an impression or a quartile. Using this [ad](http://adcade.com/demo/the_atlantic/allstate/) as an example, when we [debug](http://testweb.pw/adcadeTesting/testing/Testing_Tutorial_And_Guidelines/#metrics) for metrics, we expect metrics tracking for each unique user click on gender, age, race, education level, income, marital status. The tracking details are/should be available via the [campaign brief](https://docs.google.com/a/adcade.com/spreadsheet/ccc?key=0AunIV2knptx1dGdmaVJiUkRzZzZFMzJENFBZVklLb3c#gid=1). | As a tester, I want to evaluate Metrics & API, So that regression tests pass |
| 5 |  |  [Metrics Functionality](#) meets tracking, clickthrough, interaction and API requirements | This includes but is not limited to: Every click is counted as an individual interaction, Auto-expands/auto-collapses are tracked as "auto", User-initiated expands/collapses are tracked as interactions, clickthroughs stop the video; stop is tracked as "auto," video metrics are captured as "auto" where necessary, video metrics are captured as "interact" where necessary.| As a tester, I want to evaluate network requests, So that regression tests pass |
| 6	|  |  Backup assets and url are set up properly and match AdID | This obtained similarly via the above steps. However the conditions need to consider Windows Native IE browser, and browser web kits from that environment. Browser can contain header, however this test is not valid until the conditions are met.  | As a tester, I want to evaluate back up assets on IE 7 & 8, So that regression tests pass |
| 7	|   | Ad works correctly on desktop, tablet and mobile devices. | This only includes tests where hardware and device conditions are met. If the campaign brief mentions target platforms or devices, the ad must work in those environments | As a tester, I want to evaluate the ad on targeted platforms,  So that regression tests pass |
| 8 |   | Functionality matches expectations set forth in campaign brief. | In addition to the [campaign brief](https://docs.google.com/a/adcade.com/spreadsheet/ccc?key=0AunIV2knptx1dGdmaVJiUkRzZzZFMzJENFBZVklLb3c#gid=1) any other traceable document should be included and mentioned in the `Acceptance Criteria` during test execution. | As a tester, I want to evaluate UI, UX and functionality,  So that regression tests pass |

