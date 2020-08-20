# Challenge 01 - A little something to get you started
## Flags: 4
<br />

## **Flag#1**
We begin by testing the functionality of the site. At first glance, nothing seemes wrong with `http://35.227.24.107/0274df1725/page/2` (Markdown Test page). Home and edit work as expected as well.

![markdown test](/screenshots/02_1.JPG "info given")

Next, I tried creating a new page. Noting that  ` "Markdown is supported, but scripts are not"`, I tested the forms for XSS using two simple alert calls for the title and textbox. Initially, nothing notable occured, but clicking on the Home button (and also just navigating between pages) will bring up an alert box with our first flag and our alert messages.

![xss](/screenshots/02_3.JPG "flag") 
![xss](/screenshots/02_4.JPG "flag") 
![flag found](/screenshots/02_2.JPG "flag") 

It seems that this is a case of Stored XSS, as the flag and alart messages keep getting triggered when navigating the site. The newly created page did not execute the script initially, but it was successfully stored in the web application and persists even if the titles are changed. 

**Flag:** ^FLAG^fe5b737958c8f8c9f2a276d887d07c6ff5b1bc9243fea234830de00ed85c40cd$FLAG$

<br /> 

## **Flag#2**
When I was fiddling with the pages, I noticed that the page numbers do not match up. Creating a new page, I noticed it was listed as **10**, `http://35.227.24.107/0274df1725/page/10`, but there was only 7 pages, including 2 blank pages.

![web page](/screenshots/02_5.JPG "flag") 

Manually checking each url, 
- page 3: Not Found
- page 4: Forbidden 
- page 5: Not Found

Since page 4 is Forbidden, I tried a round about method to enter it, using the page editor. First, I went to any editable page, and edited the url to `http://35.227.24.107/0274df1725/page/edit/4`. The flag was within the textbox.

**Flag:** ^FLAG^1cde064dc80d32e00ee77c4a4b96a44f7e9d8bf120a2800771fa72834bc908bc$FLAG$

<br /> 

## **Flag#3**
This flag was slightly more difficult for me to find, requiring two hints. 

Hints received:
- Make sure you tamper with every input
- Have you tested for the usual culprits? XSS, SQL injection, path injection

Since XSS was found before, I decided to try with a test for SQL injection
^FLAG^7a4cddbacdf450a66d550bf975812973de848991895767447ae53ca1180052c6$FLAG$