 # Testing Guidelines
The information in this document is derived from multiple sources. They include but are not limited to:

* [Adcade Bootcamp Presentation](https://docs.google.com/a/adcade.com/presentation/d/1inL2kMgyjANwt600MzqkeVQEECtLtTfPJ3v8iYhQEtI/edit#slide=id.gf4f0645e_0409)
* [IAB Display Guidelines](http://www.iab.net/guidelines/508676/508767/displayguidelines)
* [Adcade Ad Matrix](https://docs.google.com/a/adcade.com/spreadsheet/ccc?key=0AiABAzEQmBMGdEFMYVdmVmFCcW9GSWxoRm9XdnFaTVE&usp=sharing_eid#gid=0)
* [Adcade Metrics Guidelines](https://docs.google.com/a/adcade.com/document/d/1ziWCL8DSSwjJ_Rqisjv3qlMfXQ7onIpNMHOrn4BbggQ/edit)

## Types of Ads
This is an ongoing collection of the infinite ad types, skins and functionality introduced via `AdStack`, `IDE`, `AdScript`, etc.

Please update this as regularly as possible, even if you are not the original author. Take the liberty to create, update or delete any data in this document.



| Type | Preview | Description |
| --- | --- | --- |
| In-Page | [URL](http://adcade.com/demo/capitalone/index.html) | A creative that is within a fixed position on a page. In-Page creatives typically include video assets and polite download technology. |
| Film Strip | [URL](http://adcade.com/demo/gshock/index.html) | A 300x3000 canvas, viewable through a 300x600 window and fully controlled by viewer. User can scroll through each of the 300x600 panels. This unit is also available for mobile where it is a scrollable, multipanel, horizontal or vertical ad unit, much like “The Filmstrip” Display Standard Ad Unit. |
| Fullscreen Expandable | [URL](http://adcade.com/demo/epicurious_live_mocks/320x50_expandable/index.html) | A creative that expands beyond its initial pixel dimensions. Expansion can take place upon user interaction (for example, by click or mouse-over) or automatically when the page loads (Auto-Expand). A creative can be customized to expand in any direction, shape, or effect and to collapse on user interaction or automatically on mouse-out or based on a timer. Expanding creatives expand over page content by default, but you can also enable them to push content down on a page. This is called a pushdown ad. |
| Pushdown Expandable | [URL](http://adcade.com/demo/epicurious_live_mocks/728x90_expandable/index.html) | A creative can be customized to expand in any direction, shape, or effect and to collapse on user interaction or automatically on mouse-out or based on a timer. Expanding creatives expand over page content by default, but you can also enable them to push content down on a page. This is called a pushdown ad. |
| Leftside Expandable | [URL](http://adcade.com/demo/phrma/468x648_expand/) | See `Fullscreen Expandable` and  `Pushdown Expandable`. Description applies to right side expandables. |
| Floating | [URL](#) | A creative that floats on top of a page's content. A Floating creative can move with content or maintain a locked position on a page as a user scrolls. It can be loaded in any position on the page (centered, top left, bottom center, or any relative pixel position) <br \> Full page floating units that appear on site load are often referred to as full page interstitials, welcome mats, and homepage takeovers, among others. Generally these will also include a full page background that appears behind the creative to cover the site content completely.|
| Slider | [URL](http://adcade.com/demo/epicurious_live_mocks/728x90_expandable/index.html) | A floating creative that sits at the bottom of a site, extending 100% of the site's width. These creatives can be fully closed out on user interaction or based on a timer.<br \>Catfish can also be set up to expand or sidekick/slide on user interaction. The slide functionality is an IAB Rising Star: The Slider. |
| Sidekick | [URL](http://adcade.com/demo/jeep/suv/300x600_sidekick/) | Expandable format that launches from IAB standard ad, pushing page content leftward, revealing large, functional canvas |
| Portrait | [URL](http://adcade.com/demo/business_insider/portrait_feed/) | 300x1050 canvas format with state-of-the-art plug and play functionality via the multiple modules included in the unit. Certain modules have ability to expand on user interaction. |
| Mobile Pull | [URL](http://adcade.com/demo/montblancsite/index.html) | A mobile bottom or top banner that expands to full screen, not unlike “The Pushdown” Display Standard Ad Unit. |
| Wallpaper Skin | [URL](http://adcade.com/demo/lg/hunit/) | Animated or static unit that loads into the gutters of a site, monetizing space outside of a standard ad slot. |
| Full Screen Flex | [URL](http://adcade.com/demo/olay_gamechangers_320x50/) | Full screen mobile experience that accommodates both portrait and landscape orientation |
| Adhesion | [URL](http://adcade.com/demo/sally_hansen/728x90/) | Standard mobile banner that “adheres” to its start position when device is rotated or when content is manipulated (e.g., with a tap to magnify) |
| Billboard | Not found in [matrix](https://docs.google.com/a/adcade.com/spreadsheet/ccc?key=0AiABAzEQmBMGdEFMYVdmVmFCcW9GSWxoRm9XdnFaTVE&usp=sharing_eid#gid=0) | Large billboard running the full width of the page with full close-ability. This is based off of the large masthead that runs on the YouTube homepage. |
| Float |  Not found in [matrix](https://docs.google.com/a/adcade.com/spreadsheet/ccc?key=0AiABAzEQmBMGdEFMYVdmVmFCcW9GSWxoRm9XdnFaTVE&usp=sharing_eid#gid=0) | A creative that floats on top of a page's content. A Floating creative can move with content or maintain a locked position on a page as a user scrolls. It can be loaded in any position on the page (centered, top left, bottom center, or any relative pixel position) <br \>Full page floating units that appear on site load are often referred to as full page interstitials, welcome mats, and homepage takeovers, among others. Generally these will also include a full page background that appears behind the creative to cover the site content completely. |



## Clickthrough Verification
### Operating System Requirements
* `Mac OS X 10.4.x` and up
* `Windows 2000` and up
* `iOS 6.x` and up
* `Android 4.1.x`  and up

### Web Kit Requirements
* `Internet Explorer 8` and up
* `Firefox 34.0.x` and up
* `Chrome 39.0.x` and up
* `Safari 6.x` and up

### Software Requirements
* `Charles` Debugging Software [(link)](http://www.charlesproxy.com/)

### Click-Through
The measurement of a user clicking on a link that re-directs the user’s web-enabled device to another Web destination. [*](http://www.iab.net/wiki/print/)

#### Click
A "click" can denote several different things. It can be a metric that measures the reaction of a user to an Internet ad. In this context, there are 3 types of click: `click-throughs`, `in-unit clicks` & `mouseovers`. It can be the opportunity for a user to download another file by clicking on an advertisement, as recorded by the server. It can be the result of a measurable interaction with an advertisement or key word that links to the advertiser's intended Web site or another page or frame within the Web site. *It can be a metric that measures the reaction of a user to linked editorial content. More information is available at the IAB Ad Campaign Measurement Guidelines. See also, clickthrough, in-unit click and mouseover. [*](http://www.iab.net/wiki/print/)


### Example
For this example we will use a relatively simple marquee ad. This Refinery 29 - Tiffany & Co. Advertisement is a H-Unit ad with a background and video push-down.

#### Scenario(s)
Go through the scenario(s) below one step at a time to understand the steps for this one "click-through" test. For this specific ad there are multiple touch points that will redirect the user to the click-through URL.

Link to [Appliction Under Test (AUT)](http://adcade.com/demo/refinery29/tiffany/marquee_flight1/)  

	As a tester  
	I want to click the ad  
	So that I can verify the click-through URL  

		Scenario Outline: I want to verify the click-through URL  
		Given I am on the AUT
		And I am using Charles Debugger to view all network requests
		Then I should see "c_wallpaper.jpg"
		And I should see "poster.jpg"
		And I should see "Adcade"
		When I follow or press "<clickThroughPoint>"
		Then I should be on "<redirectURL>"
		And I should be redirected to "<finalExitURL>"

Examples:

| clickThroughPoint | redirectURL | finalExitURL |
| --- | --- | --- |
| ![](../img/Header.png) | http://bs.serving-sys.com/BurstingPipe/adServer.bs?cn=tf&c=20&mc=click&pli=11676068&PluID=0&ord=[timestamp] | http://www.tiffany.com |
| ![](../img/BackGround.png) | http://bs.serving-sys.com/BurstingPipe/adServer.bs?cn=tf&c=20&mc=click&pli=11676068&PluID=0&ord=[timestamp] | http://www.tiffany.com |
| ![](../img/VideoPlaying.png) | http://bs.serving-sys.com/BurstingPipe/adServer.bs?cn=tf&c=20&mc=click&pli=11676068&PluID=0&ord=[timestamp] | http://www.tiffany.com |
| ![](../img/VideoThumb.png) | http://bs.serving-sys.com/BurstingPipe/adServer.bs?cn=tf&c=20&mc=click&pli=11676068&PluID=0&ord=[timestamp] | http://www.tiffany.com |

### Charles Debugging Tool
| Step | Description | Screenshot |
| --- | --- | --- |
| 1 | Open the AUT URL in your browser of choice. For this example, lets use Chrome on Mac OS X. | ![](../img/FullScreenChrome.png) |
| 2 | Open Charles. Your default view should appear similar to the screen shot. | ![](../img/CharlesMain.png ) |
| 3 | From the toolbar, select Settings. | ![](../img/CharlesSettings.png) |
| 4 | In the "Include" section, limit the recorder to sniff only requests made from Adcade servers. This is called whitelisting. | ![](../img/SingleInclude.png) |
| 5 | Your recording settings should reflect as follows. Be sure to include the server of the click-through. | ![](../img/RecordingSettings.png) |
| 6 | Refresh the AUT. Until now your requests log should've been either empty or full of other requests from your computer. If you'd like you can select and delete all requests not relevant to this test. After refreshing the view, you should see requests being populated from Adcade servers. | ![](../img/AllRequests.png) |
| 6 | On the left-hand-side of the work station, you can select a request to view more details, which will open up on the right-hand-side of your work station. Select the call to the click through server, and double click "Host".  | ![](../img/RedirectEvent.png) |
| 7 | Use this data to validate that the click-through is pointing to the right endpoint. | n/a |



## Metrics
### Guidelines
See [Metrics Guidelines Documentation](https://docs.google.com/a/adcade.com/document/d/1ziWCL8DSSwjJ_Rqisjv3qlMfXQ7onIpNMHOrn4BbggQ/edit)

Metrics are used in our application to track user retention, impressions and more. It is a feature and proper testing needs to be done to ensure the function is behaving as expected. Other than a few `GET` requests to initialize tracking, most of our metrics requests are sent as `POST` through `FORM DATA`. Typical FORM DATA looks like:

	{"adId":"XXXX-XXXX-XXXX-XXXX","pId":"YYYY-YYYY-YYYY-YYYY","startTime":12345678910,"events":[{"type":"<eventHandle>","time":123456,"key":"<eventName>"}]}:

The metrics tracked in uur example, `eventHandle` & `eventName`, are listed below.

### Example
For this example we will use a relatively simple marquee ad. This Refinery 29 - Tiffany & Co. Advertisement is a H-Unit ad with a background and video push-down.

#### Scenario(s)
Go through the scenario(s) below one step at a time to understand the steps for this one "click-through" test. For this specific ad there are multiple touch points that will redirect the user to the click-through URL.

	As an admin  
	I want to track a users interaction  
	So that I can gather metrics  

	As an admin  
	I want to create, read, update & delete metrics via API  
	So that I can capture impressions and retention  

		Scenario Outline: I want to verify the metrics firing from triggers and actions  
		Given I am on the AUT
		And I am using Chrome
		And I have Developer Tools open
		And I am on the XHR Network Tab
		Then I should see "c_wallpaper.jpg"
		And I should see "poster.jpg"
		And I should see "Adcade"
		When I do "<eventTrigger>"
		Then the response should contain "<eventName>"
		And I should be redirected to "<finalExitURL>"


**Examples:**

| eventTrigger | eventHandle | eventName | eventType |
| --- | --- | --- | --- |
| Requesting `/` | Impression | imp | GET |
| Interacting with Ad | Touchdown | tdn | POST |
| Expanding Ad | Interact | std.interact.expansion | POST |
| Dragging Logo | Interact | std.interact.logo_drag | POST |
| Dropping Logo | Touchup | tup | POST |
| Collapse | Interact | std.interact.collapse | POST |
| Clickthrough | Exit | std.exit.clickthrough | POST |
| Exit Main | Exit | std.exit.exit_main | POST |
| Video Play | Auto | std.auto.video.play | POST |
| Video Quartile | Auto | std.auto.video.1st_quartile.main_video | POST |
| Video Quartile | Auto | std.auto.video.2nd_quartile.main_video | POST |
| Video Quartile | Auto | std.auto.video.3rd_quartile.main_video | POST |
| Video Quartile | Auto | std.auto.video.4th_quartile.main_video | POST |
| Video Collapse | Auto | std.auto.collapse | POST |
| Video End | Auto | std.auto.video.complete.main_video | POST |
| Close | Auto | std.auto.close | POST |


### Viewing Metrics
| Step | Description | Screenshot |
| --- | --- | --- |
| 1 | Open the AUT in your browser of choice. For this example, lets use Chrome on Mac OS X. | ![](../img/FullScreenChrome.png =500x) |
| 2 | Right Click and select "Inspect Element" or press `Command` + `Option` + `I`. | ![](../img/ChromeMenu.png =200x) |
| 3 | Depending on your default settings, the "Inspector Window", may appear different. Your experience should however should reflect the screen shot. | ![](../img/InspectorChrome.png =500x) |
| 4 | From this window, select the "Network" tab, which should be in the top bar. Your console may show that there is "no network data" to display. Refresh the ad if that is the case.| ![](../img/SelectNetwork.png =500x)|
| 5 | From this tab, select the "XHR" filter, which should also be in the top bar. By default the "All" filter should be applied. | ![](../img/XHR.png =500x) |
| 6 | Unless you need to refresh again, your Inspector should show the default Impression. Any other tracked metric interaction will be available through this tab. | ![](../img/SelectingARequest.png =500x) |

## MRAID (Mobile Rich Media Ad Interface Definitions)
Link to [MRAID Webtester](http://webtester.mraid.org/) environment.

Most of our ads come with test tags. For example, this [ad](https://adstack.adcade.com/preview/preview.html?adId=7c277904-7fc9-4791-bfdc-eef959b65ab8&plId=2b1528e5-7478-493c-bde9-d4f0be1e3ff8) there are "tags" in the [campaign brief](https://docs.google.com/a/adcade.com/spreadsheet/ccc?key=0AvdVSRELa_3XdGg1YmZaUjN3LWRycVltVlV3UldobEE#gid=0). Go to the "Tag Sheet" sheet, in the section titled "TAGS" there are multiple HTML snippets you can copy & paste.

### Testing in MRAID
For the purposes of this example lets use this html "tag", below:

    <div>
    	<script>
    		(function()
    		{
				// get query string params
				var getParameterByName = function(name)
				{
				    name = name.replace(/[\[]/, "\\\[").replace(/[\]]/, "\\\]");
				    var regex = new RegExp('[\\?&]' + name + '=([^&#]*)'),
				        results = regex.exec(location.search);
				    return results == null ? '' : decodeURIComponent(results[1].replace(/\+/g, ' '));
				};

				var adId = getParameterByName('adId');

	    		var img = document.createElement('img');
	    		img.style.borderStyle = 'none';
	    		img.setAttribute('src', 'http://ad-prod.adcade.com/1/backup/imp/' + adId);

	    		var anchor = document.createElement('a');
	    		anchor.setAttribute('target', '_blank');
	    		anchor.setAttribute('href', 'http://ad-prod.adcade.com/1/backup/ext/' + adId);
	    		anchor.appendChild(img);

	    		document.body.appendChild(anchor);

    		})();
    	</script>
    </div><a target="_blank" href="http://ad-prod.adcade.com/1/backup/ext/SHBRIDEDEC13SPBU30050"><img src="http://ad-prod.adcade.com/1/backup/imp/SHBRIDEDEC13SPBU30050" style="border-style: none;"></a>

| Step | Consideration | Screenshot |
| --- | --- | --- |
| 1 | Navigate to [MRAID Webtester](http://webtester.mraid.org/) | ![](../img/MRAID.png =500x) |
| 2 | Keep all details at default for this example, then go to the "Flight" tab. | ![](../img/MRAID.png =500x) |
| 3 | Paste the HTML code snippet in the text box area. | ![](../img/MRAID2.png =500x) |
| 4 | Press "Render". Viola! Now the tester should be on the "Test" tab and a new window in the selected viewport should open (For this test the window size was 320 X 480). All interactions in this environment should reflect the MRAID standards for ads in browser/webpage environments.| ![](../img/MRAID3.png =500x) |

___
