# Project 7 - WordPress Pentesting

Time spent: **14** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Version Enumeration
  - [ ] Summary: A readme file with the version was available at the link http://wpdistillery.vm/readme.html
    - Vulnerability types: enumeration, mapping, fingerprinting
    - Tested in version: 4.2
    - Fixed in version: 4.8.1
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate:go to http://wpdistillery.vm/readme.htm
  - [ ] Affected source code: none
2. (Required) Login Enumeraton
  - [ ] Summary: The loggin menu notifies when a user has entered an incorrect password for an existing user.
    - Vulnerability types: enumeration
    - Tested in version: 4.2
    - Fixed in version: unknown 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: Loggin to the admin account using a wring password. A response will return that a wrong password was entered for the admin account. 
  - [ ] Affected source code: none
3. (Required) Authenticated Stored XSS via Imange Filename
  - [ ] Summary: It was possible to execute a XSS attack when uploading an image with XSS scrip in the filename.
    - Vulnerability types: XXS
    - Tested in version: 4.2
    - Fixed in version: 4.2.10
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: Change the image name to include the 'cengizhansahinsumofpwn<img src=a onerror=alert(document.cookie)>.jpg' script. Then, upload the image as an attachment in a comment. In order for the exploit work, that admin has to approve the comment. After the admin approves the comment, it becomes visible to rest of the users. When the image is clicked on, the XSS script executes. 
  - [ ] Affected source code: none
4. (Optional) Host Header Injection in Password Reset
  - [ ] Summary: An attacker can send a password reset link to a different email.
    - Vulnerability types: CSRF
    - Tested in version: 4.2
    - Fixed in version: 4.8.3
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 1) Click "Lost your password?" 2) In the username or email feild, enter "admin" 3) Using Burp Suite, find the password reset POST request and send it to the repeater. 4) In the repeater, change the "HOST:" form wpdistiller.vm to an alternative email. 5) Resend the POST request.
  - [ ] Affected source code: none
    
## Assets
BURP Suite

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes



## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
