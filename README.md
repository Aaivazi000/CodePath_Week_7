# Project 7 - WordPress Pentesting

Time spent: *3* hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types: Cross Site Scripting (XSS)  - Input Sanitization
    - Tested in version: Version 4.2
    - Fixed in version: 4.2.3
  - [ ] GIF Walkthrough: https://imgur.com/a/Au4om
  - [ ] Steps to recreate: On Admin Page make a new post and text shown into the Post Title field. Publish the post and go to the home page (wpdistillery.dev). Search for your post and when you hover over the title of the post the alert(‘xss’) will be engaged.
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/4.2/src/wp-includes/default-widgets.php)


1. (Required) Authenticated Stored Cross-site Scripting 
  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2.0
    - Fixed in version: 4.2.3
  - [ ] GIF Walkthrough: https://imgur.com/a/V9MGV
  - [ ] Steps to recreate: 
		1. Log in as a regular user or just visit the site without being logged in as an admin.
		2. Post a comment to the page with the following HTML in the body of the comment: <a href="[caption code=">]</a><a title = " onmouseover=alert('testalert')  ">link</a>
		3. Post the comment. And hover over the link.
  - [ ] Affected source code: 
    - [Link 1](https://klikki.fi/adv/wordpress3.html)

1. (Required) Nav Menu stored XSS attack: CVE 2015-5733

  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.4
  - [ ] GIF Walkthrough: https://imgur.com/a/pnOar
  - [ ] Steps to recreate: 
		1. Log in as Admin
		2. GO to Appearance > Menus > and make a new mene. Name the menu anything. Go to current link, enter any test as the url and enter the following in the url text: <script>alert(1) </script>
		3. This will execute anytime the menu is saved or displayed.
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/4.2/src/wp-admin/js/nav-menu.js)


## Assets

None used.

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [2017] [Andriana Aivazians]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
