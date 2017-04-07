#JMeter 

Please make sure to have the latest version of "Firefox" downloaded.

---
##Charles (Blackbox Testing)

If prefferred, locally download [Charles](http://www.charlesproxy.com/download/). This tool, alongside JMeter, is an equally powerful tool that tells you what exactly is going on. It can even be used to sniff iOS and Android http/https requests, let alone API's.  

As soon as you open Charles and play around outside the app, you'll notice data being collected in the left-tab. Every HTTP/HTTPS request being made is monitored. So if you're confused about a call and how it should look in JMeter, when a similar tool is running, you can use this to parse all data collected. 

##Remote Server or Local

Go to [Apache](http://jmeter.apache.org/download_jmeter.cgi) and download the latest **binaries**. Install and unzip.

Then go to: /bin/ApacheJMeter.jar and open the file. You'll need Java.

Or for remote in terminal run: 

* sudo apt-get install jmeter jmeter-http

You should see a bunch of files downloading. Go through the above steps and start ApacheJMeter.

JMeter, locally, should look like:  
![Smaller icon](http://4.bp.blogspot.com/-yMoHp5V2BsE/T-oewRnXeII/AAAAAAAABrA/XXb44Y7jLcg/s1600/jmeter.png)

###JMeter Tests
[Apache's JMeter Documentation](http://jmeter.apache.org/usermanual/build-web-test-plan.html)  
[Step-by-Step Configuration and Execution](http://jmeter.apache.org/usermanual/jmeter_proxy_step_by_step.pdf)  
[JMeter for Mac](http://www.anujgakhar.com/2010/06/23/stress-testing-your-website-with-apache-jmeter/)  
####Sniffing HTTP Requests
1. **Right-click** on "Test Plan""
2. Add > Logic Controller > Recorder Controller
1. **Right-click** on "WorkBench"
2. Add > Non-test Elements > HTTP Proxy Server
3. Open "Firefox"
	3. Go through restart/install procedure, post-Charles installation
	3. Go to FireFox > Preferences > Advanced
		1. While in Network tab, select "Settings" for Connection section
		2. Change HTTP Proxy: to "localhost" Port: "8080" or something not used, note the port being used.
		3. Check "Use this proxy for all protocols"
		3. Save, all websites should fail until Proxy is started
3. Select HTTP Proxy Server
	4. In the Right, you should see "Global Settings" "Port: 8080" (by default)
	5. Set Port to "8080" or port selected from earlier
	6. On HTTP Proxy Server, click the “Add” button in “URL Patterns to Include”. This will create a blank entry. Enter “.*\.html”.
	7. . Click the “Add” button in “URL Patterns to Exclude” 3 times. This will create 3 blank entries. After that enter “.*\.png” pattern, “.*\.gif” pattern and “.*\.ico” pattern.
4. In the HTTP Proxy Server, you should see a "Start" button on bottom, press start
5. In FireFox, go to "http://cs.qa1.poc.ae1.currdc.net:8080/wg-curriculum/api/%7Bversion%7D/data/skill" or any website of your choice.
	6. Notice the left-pane, similar to Charles.app, JMeter now records all HTTP Requests and all assets being requested. Alongside with paths, JMeter is also recording Headers sent from your machine.
	
####Load Tests
#####Google.com
In this example we will run load tests against Google, lets hope they don't get mad :)  

While having JMeter open:

1. **Right-click** on "Test Plan"
2. Add > Threads > Thread Group
3. Rename the "Thread Group" to "Google.com Users"
	3. Set Number of Threads to 10
	4. Set Loop count to 2 
4. **Right-click** on “Thread Group”, Add > Listener > Summary Report
4. **Right-click** on "Google.com Users"
5. Add > Sampler > HTTP Request
6. Add Server Name, "www.google.com", Add Path, "/", leave everything else empty
8. Press Play and viola, you've ran you're first Load Test using JMeter


#####Our Rest API's

In this example we will test the below API's:

* http://cs.qa1.poc.ae1.currdc.net:8080/wg-curriculum/api/%7Bversion%7D/data/skill  
* http://cs.qa1.poc.ae1.currdc.net:8080/wg-curriculum/api/rest/rosters  
* http://cs.qa1.poc.ae1.currdc.net:8080/wg-curriculum/api/rest/sections
* http://cs.qa1.poc.ae1.currdc.net:8080/wg-curriculum/api/rest/organizations

For now, they will all be using GET protocol. It is completely possible to use POST, DEL, PUT as well, though because I am not familiar with this environment or the calls themselves, **I will write a scenario that delivers JSON responses for GET "Skills", "Rosters", "Sections" and "Organizations".**

While the HTTP Sniffing steps are completed for all API's you want to test (listed above).

2. **Right-click** on "Test Plan"
2. Add > Threads > Thread Group
	3. Change "Name" to "API Users", name doesn't matter but for the sake of clarity
	4. Change "Number of Threads" to "5", this means there will be 5 users per request sent from JMeter
	5. Change "Loop Count" to "2" with "Forever" checked-off, which means that JMeter will Loop the request twice, so in total 10 requests, 5 per session
3. **Right-click** on "Thread Group"
4. Add > Config. Elements > HTTP Request Defaults
	5. For the sake of testing something Amplify related in Server Name or IP, enter: "http://cs.qa1.poc.ae1.currdc.net"
	5. In port, enter "8080"
	5. In Protocol [http], enter "GET"
5. **Right-click** on "Thread Group", Add > Config Element > HTTP Header Manager
5. **Right-click** on "Thread Group", Add > Sampler > HTTP Request
	6. In Path for HTTP Requests, enter: "/wg-curriculum/api/{version}/data/skill"
	7. Change "Name" to "Skill"
	8. Add "cs.qa1.poc.ae1.currdc.net" as the Server Name
6.  **Right-click** on "Thread Group", Add > Sampler > HTTP Request
	7.  In Path for HTTP Requests, enter: "/wg-curriculum/api/rest/rosters"
	7. Change "Name" to "Rosters"
	8. Add "cs.qa1.poc.ae1.currdc.net" as the Server Name
6.  **Right-click** on "Thread Group", Add > Sampler > HTTP Request
	7.  In Path for HTTP Requests, enter: "/wg-curriculum/api/rest/sections"
	7. Change "Name" to "Sections"	
	8. Add "cs.qa1.poc.ae1.currdc.net" as the Server Name
6.  **Right-click** on "Thread Group", Add > Sampler > HTTP Request
	7.  In Path for HTTP Requests, enter: "/wg-curriculum/api/rest/organizations"
	7. Change "Name" to "Organizations"
	8. Add "cs.qa1.poc.ae1.currdc.net" as the Server Name
6. **Right-click** on "Thread Group", Add > Listener > Graph Results
8. **Right-click** on “Thread Group”, Add > Listener > View Results Tree
9. **Right-click** on “Thread Group”, Add > Listener > Summary Report
10. For each "HTTP Sampler", **Right-click**, Add > Config Element > HTTP Authorization Manager
	11. For each "HTTP Authorization Manager" (there should be 4), the "base url"" should be "http://cs.qa1.poc.ae1.currdc.net:8080/wg-curriculum/api/"
	14. Add username and password for HTaccess, in this case its admin, admin
	14. Leave Domain and Realm empty
	

####CSV Config Element

In API’s we need to give inputs, there is a way in JMeter to provide inputs from csv file. You can create csv file of your inputs and provide this file to JMeter. JMeter will read your csv file line by line and provide this data to your http request. So how to provide inputs from csv file, it’s pretty simple. Create your csv file, I have created logindetails.csv file (Attached below). Now right click on thread group and go to Add –> Config Element –> CSV data set Config.