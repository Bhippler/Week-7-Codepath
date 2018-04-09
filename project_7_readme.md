# Project 7 - WordPress Pentesting

Time spent: **X** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) User Enumeration
  - [ ] Summary: User Enumeration is the ability to programmatically determine whether a given account is valid on a system.
    - Vulnerability types: User account enumeration with a password brute-force
    - Tested in version: 4.2
    - Fixed in version: N/A
  - [ ] GIF Walkthrough: https://drive.google.com/open?id=14PIhdXwJKWg3ir7KbdG7Y89e2P8S4o-E
  - [ ] Steps to recreate: 1. Open wpscan and point it to scan for users on the WordPress website with the --enumerate u parameter
						   2. After user enumeration scan, import a list of common passwords in a .txt file into the wpscan directory
						   3. Enable wpscan to brute-force the discovered accounts with the --wordlist parameter followed by the .txt file name
						   4. Once the password has been found, use it to log into the WordPress admin page through your browser
  - [ ] Affected source code: N/A
    - [Link 1]
1. (Required) WordPress Cross-site Scripting (XSS)
  - [ ] Summary: Cross-Site Scripting (XSS) attacks are a type of injection, in which malicious scripts are injected into otherwise benign and trusted web sites.
    - Vulnerability types: XSS: executing benign code within the post or comment after it has been published
    - Tested in version: 4.2
    - Fixed in version: 4.2.3
  - [ ] GIF Walkthrough: https://drive.google.com/open?id=1IP1o3AbaiTWGSECqF9K7lqLSrjrHyHF4
  - [ ] Steps to recreate: 1. Create a new post or make a comment on a post
						   2. In the text box enter in some type of malicious code, for example: "<a href="[caption code=">]</a><a title=" onmouseover=alert('XSS!') ">Don't click on this link</a>"
						   3. Publish the post or comment and depending on the browser it will automatically run the code or will run when somebody clicks on the link.
  - [ ] Affected source code: src/wp-includes/class-wp-embed.php; src/wp-includes/formatting.php; src/wp-includes/kses.php; src/wp-includes/shortcodes.php; tests/phpunit/tests/kses.php; tests/phpunit/tests/shortcode.php
    - [Link 1] https://core.trac.wordpress.org/changeset/33359
1. (Required) WordPress Cross-site Scripting (XSS)
  - [ ] Summary: Cross-Site Scripting (XSS) attacks are a type of injection, in which malicious scripts are injected into otherwise benign and trusted web sites.
    - Vulnerability types: XSS: executing benign code through Javascript within the post or comment after it has been published
    - Tested in version: 4.2
    - Fixed in version: 4.3.1
  - [ ] GIF Walkthrough: https://drive.google.com/open?id=13Y7OLzE3Nypuwyiygkif_uVLm_0kJZWP
  - [ ] Steps to recreate: 1. Create a new post or make a comment on a post
						   2. In the text box enter in some type of malicious code, for example: "[caption width="1" caption='<a href="' ">]</a><a href=" onmouseover='alert("Why would you click on this link?")' ">I bet you won't click on this</a>"
						   3. Publish the post or comment and depending on the browser it will automatically run the code or will run when somebody clicks on the link.
  - [ ] Affected source code: src/wp-includes/class-wp-embed.php; src/wp-includes/formatting.php; src/wp-includes/kses.php; src/wp-includes/shortcodes.php; tests/phpunit/tests/kses.php; tests/phpunit/tests/shortcode.php
    - [Link 1] https://core.trac.wordpress.org/changeset/33359
1. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
1. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php) 

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

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
