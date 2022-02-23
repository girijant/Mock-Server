While working on End-to-End 4G/5G Network Slicing Service-Orchestration integration/testing activities, we often use several API calls on various Network Domain (Core, Transport...etc) Controller Elements like: NSMF, NSSMF, CNSSMF, RNSSMF...etc. These API calls work as an important bridge between the client and the Network Domain Controllers, perform various operations on Network Elements through GET/POST/DELETE...etc methods.

But what happens when you do not have a Real Network Domain Controller or Not readily available for some reason during your testing or customer Demo/PoCs?
* Here comes to your aid the magical feature of Mock-Server/Simulator - A Mocking Framework, that mimics the RESTful and SOAP based requests and responses for the desired APIs like: EDENNET, NFMP, VPRN and PGW...etc, which allows you to perform the essential operations on Network Elements for your testing/Demo/PoCs.

This guide includes step-by-step instructions, so that you have a comfortable experience in the RESTful and SOAP based Simulator. Without further ado, let’s get started by discussing all the what(s), why(s) & how(s) about REST & SOAP Simulators!

# Mock-Server
A java based light-weight server for mocking your RESTful and SOAP based APIs over HTTP or HTTPS With having a browser-based Dashboard Console - for live monitoring of logs, requests, and responses to help on easy tracking or quick debugging. 

# What a Mock-Server?
A Mock-Server is a java based mocking framework that can support for mocking your RESTful and SOAP based service/APIs over HTTP or HTTPS.
The Concept: The concept is very simple:
* You or any external system send a Request to Mock-Server, the Mock-Server matches the incoming request with a configured Expectation (method, header, end-point, body) and an Action (response) is taken accordingly for matched/unmatched Request.
* In addition, it provides a GUI based Dashboard-Console for live-monitoring, Filtering and Tracing the detailed Requests, Responses and logs in a pretty Rich format - helps for easy tracking and quick debugging.

# Mock-Server Design Principles
* A light-weight server (jetty) must be always up and running in the backened - i.e. readily available for mocking any REST or SOAP based APIs.
* An Expectation needs to be configured - contains a Request Matcher (method, header, end-point, body).
* An Action needs to be configured - for the success or error response.
* Capable to Receive any Request payload of any type (JOSN,XML..etc).
* Must be Verified and Matched the Request against the configured Expectations
* Return the desired Response if a request matches an expectation else error respone(404).
* Allows to Configure the Request & Expectations.
* Allows to mimic the EDENNET, NFMP, VPRN as RESTful based and PGW as SOAP based APIs.
* Allows easy tweaking for any new API integration.
* Must have a GUI based Dashboard Console: For live monitoring of logs, requests and responses to help on easy tracking and quick debugging.
* Easily launched from CLI or integrated with Kubernates pod.

# REST-Mock:
A generic Mocking Framework, that mimics the RESTful based any service requests and responses for the APIs: EDENNET, NFMP, VPRN over HTTP(S) to perform an essential operation.

# REST-Mock Configuration:
Download & unzip the required REST-Simulator package i.e. RestSimulator_100.zip into it. From 'config' directory of unzipped REST-Simulator package, Edit/Update the 'restmock.properties',
Configure Host and Port, save as below:
![image](https://user-images.githubusercontent.com/17194046/155332898-58efca2e-d3c4-473e-bab7-cc634a5a6274.png)
Run 'startRestSimulator.sh' or 'startRestSimulator.bat' script
![image](https://user-images.githubusercontent.com/17194046/155331678-164ad052-0baf-40c7-8031-d2b2e4df58ff.png)

# REST-Mock Console:
* Make sure REST-Mock is successfully installed, up and running on your linux-vm or windows box.
* The Dashboard Console can be launched in any browser using the URL: http(s)://<host>:<port>/restmock/dashboard
* For example if REST-Simulator is running on localhost on port 8081 use: http://localhost:8081/restmock/dashboard
![image](https://user-images.githubusercontent.com/17194046/155333721-2a4c323e-5ac8-4493-ab42-2d9210712b2f.png)
   
# SOAP-Mock:
A Mocking Framework, that mimics the SOAP based service requests and responses for the PGW APIs over HTTP(S) to perform an essential operation.

# SOAP-Mock Configuration:
Download & unzip the simulator package: SOAPSimulator_100.zip. Edit/Update the 'soapmock.properties'
   ![image](https://user-images.githubusercontent.com/17194046/155336315-00ccb538-62cf-44c2-a6a6-5625e2a71207.png)
Run 'startSoapSimulator.sh' script:
![image](https://user-images.githubusercontent.com/17194046/155334797-1d9c98e2-5aa6-476b-afb7-cf5bcb7f5452.png)

# SOAP-Mock Console:
![image](https://user-images.githubusercontent.com/17194046/155334711-e904cb3c-95f3-4df5-8622-e99cc50b03f2.png)



  
  
  
  
  
