Burp Suite Lab Documentation

Name: Masumi Jain
Lab Topic: HTTP Traffic Interception and Parameter Manipulation using Burp Suite
Date: 01/02/2026

Objective

Understand how Burp Suite intercepts web traffic

Analyze HTTP requests and responses

Modify GET parameters using Repeater

Observe server behavior after parameter tampering

Learn how input manipulation affects backend responses

Lab Environment

Tool Used: Burp Suite Community Edition
Platform: Kali Linux (VM Environment)
Browser: Burp Built-in Browser
Network Type: Controlled Lab Environment
Target: Authorized testing website inside lab

Step-by-Step Lab Procedure
1. Launching Burp Suite

Started Burp Suite in Kali Linux:

burpsuite


Selected Temporary Project

Used Burp Defaults

Started Burp Suite

2. Configuring Browser

Used Burp’s built-in browser to automatically route traffic through proxy

Enabled interception:

Proxy → Intercept → Intercept is ON

3. Capturing HTTP Request

Visited test URL using Burp browser

Captured GET request in Proxy

Example captured request:

GET /success?ipv4 HTTP/1.1
Host: target-site.com


Observed request headers and structure.

4. Sending Request to Repeater

Right-clicked captured request

Selected Send to Repeater

Navigated to Repeater tab

5. Parameter Manipulation

Original request:

GET /success?ipv4 HTTP/1.1


Modified request:

GET /success?ipv4=1 HTTP/1.1


Tested multiple values:

ipv4=127.0.0.1
ipv4=8.8.8.8
ipv4=999.999.999.999
ipv4=' OR 1=1 --


Clicked Send after each modification and observed server response.

Commands / Features Used

Proxy Interception

Repeater Tool

GET Parameter Editing

Response Analysis

Key Observations

Parameter initially had no value

Adding value changed server behavior

Response body and content length varied based on input

Invalid input tested server validation behavior

Demonstrated how user-controlled input influences backend processing

Key Takeaways

Burp Suite is essential for web application testing

GET parameters can be manually modified to test application behavior

Repeater allows controlled testing without resending from browser

Input validation is critical to prevent vulnerabilities

Even small parameters may affect backend logic

Challenges Faced

Understanding where to modify parameters

Differentiating headers from parameters

Identifying which part of request controls response

Lessons Learned

Understanding HTTP request structure is crucial

Parameter manipulation is foundational in web security testing

Response comparison helps identify potential weaknesses

Testing must always be performed in authorized environments

Ethical Statement

All testing was conducted in a controlled lab environment.
No unauthorized systems were targeted.
This activity was performed strictly for educational and cybersecurity learning purposes.

Conclusion

Successfully captured and modified HTTP requests using Burp Suite.
Gained practical experience in parameter tampering and response analysis.
Strengthened foundational skills in web application security testing.
