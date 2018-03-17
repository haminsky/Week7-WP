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
  
  ![youtubexss](https://user-images.githubusercontent.com/30760006/37540430-1d14a07a-2914-11e8-8a3a-371cb2e1c98b.gif)

  
  - [ ] Steps to recreate: a user with posting abitlity 
  
  - [ ] Affected source code:embed.php




1. (Required) Vulnerability Name:  WordPress <= 4.9.4 - Application Denial of Service (DoS) (unpatched)

- [ ] Summary: using the linux command line to launch a denial of service against the WordPress application.
    
    - Vulnerability types:DoS Denial of Service
    
    - Tested in version:
   
   - Fixed in version: 
  
  - [ ] GIF Walkthrough:
  ![dos](https://user-images.githubusercontent.com/30760006/37552263-bd059a30-296e-11e8-8f7e-2eae5ab23678.gif)
   [ ] GIF Walkthrough:(continued)
  
  - [ ] Steps to recreate: Download the python script doser.py point the script to wpdistillery.vm and then use linux command line to satrt the script 
 
 - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
