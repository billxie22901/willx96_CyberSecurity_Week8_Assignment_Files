# Project 8 - Pentesting Live Targets

Time spent: **X** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue

Vulnerability #1: SQL Injection (SQLi)
- Description: URL unsanatized. Puting %27%20OR%20SLEEP(5)=0--%27 into the Salesperson ID will execute the SQL Injection. In this case, waiting 5 seconds before moving going to the default salesperson.
GIF Walkthrough: 
<a href="https://imgur.com/V1UdOGG"><img src="https://i.imgur.com/V1UdOGG.gif" title="Video Walkthrough" /></a>

Vulnerability #2: Session Hijacking/Fixation
- Description: Session not secure and login info was forwarded to another site. I logged in to blue site and that also gave me access to red site.
GIF Walkthrough
<a href="https://imgur.com/BN4a19z"><img src="https://i.imgur.com/BN4a19z.gif" title="source: imgur.com" /></a>


## Green

Vulnerability #1: Username Emumeration
- Description: If a known username is entered and login fails, the error message is bolded, whereas if the username is unknow, the error message would be unbolded.
GIF Walkthrough: 
<a href="https://imgur.com/ktEWR6N"><img src="https://i.imgur.com/ktEWR6N.gif" title="Video Walkthrough" /></a>

Vulnerability #2: Cross-Site Scripting (XSS)
- Description: Though no actual exploit found regarding XSS on any site, I believe the most likely candidate would be the green site. I tried to contact all three sit with the script "<script>alert(’xss exploit found by willx96');</script>" and only the green site does not show the comment.
GIF Walkthrough
<a href="https://imgur.com/QQwLJqV"><img src="https://i.imgur.com/QQwLJqV.gif" title="source: imgur.com" /></a>


## Red

Vulnerability #1: Insecure Direct Object Reference (IDOR)
- Description: When viewing a sales person you found under the "Find a Salesperson" page, you can change their ID in the URL, you will get to a different salesperson.
GIF Walkthrough
<a href="https://imgur.com/XnVgluY"><img src="https://i.imgur.com/XnVgluY.gif" title="Video Walkthrough" /></a>

Vulnerability #2: Cross-Site Request Forgery (CSRF)
- Description: Malicious HTML file can hijack valid user's session to do malicious things. In this case, changing the salesperson name and contact info.
GIF Walkthrough
<a href="https://imgur.com/6scB1PK"><img src="https://i.imgur.com/6scB1PK.gif" title="source: imgur.com" /></a>

## Notes

## License

Copyright [2017] [William Xie]

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.