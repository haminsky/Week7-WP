# Week7-WP
This a repository to pentest WordPress for CodePath assignment.
Vulnerability Name:WordPress 2.5-4.6 - Authenticated Stored Cross-Site Scripting via Image Filename

Summary: this is a cross site scripting vulnerability that allows the attacker to create a malicious java script code and 
insert it as the name of an image file, if the image is uploaded the inserted filename(jscode) will be injected in WordPress
       
       Vulnerability types:XSS Cross-Site Scripting
       
       Tested in version:4.2.2
       
       Fixed in version: 4.2.10
       
       GIF Walkthrough:
![xssviamimage](https://user-images.githubusercontent.com/30760006/37509403-7841c352-28b4-11e8-85b1-cc93d7584dbc.gif)
Steps to recreate: rename an image with a js code like (angryTuk"><img src=x onerror=prompt(document.domain)>) as a filename, the code will be injected as soon as the admin/user upload it through page attachement.

Affected source code: media.php.

## Pentesting Report

1. (Required) Vulnerability Name:WordPress  4.0-4.7.2 - Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds

  - [ ] Summary: allows users with posting priveleges to insert specially formatted HTML containing JavaScript for viewers' browsers to run.
    
    - Vulnerability types:(xss)CrossSite Scripting
    
    - Tested in version:
    
    - Fixed in version: 4.2.13
  
  - [ ] GIF Walkthrough: 
  
  
  - [ ] Steps to recreate: 
  
  - [ ] Affected source code:embed.php
