# CSC309 APRIL 2015 EXAM SOLUTION
#### Question 1
##### (a) What it means that the HTTP protocol is stateless?
##### (b) Mention three different ways to maintain state in HTTP sessions?
##### (c) The HTTP protocol allows to send a GET or a POST request to the server, for example when submitting an html form. Give 2 reasons for using POST (instead of GET) in a bulleted format:
A POST request is more appropriate than a GET because:
1.
2.
#### Question 2
```html
<html>
<body>
<form action="process.php  " method="POST">
<h1>Complaint Form</h1>
<table border="0">
	<tr><td>Your name*:</td><td><input type="text" name="name"></td></tr>
	<tr><td>E-mail*:</td><td><input type="text" name="email"></td></tr>
	<tr><td>Phone number*:</td><td><input type="text" name="phone"></td></tr>
	<tr><td>Website:</td><td><input type="text" name="url" value="http://"></td></tr>
	<tr>
		<td>Sex:<input type="radio" name="sex" value="male">Male</td>
		<td><input type="radio" name="sex" value="female" checked>Female</td>
	</tr>
	<tr>
		<td>Contact Request:</td>
		<td>
			<input type="checkbox" name="contact" value="phone" checked>By Phone
			<input type="checkbox" name="contact" value="email" checked>By Email
		</td>
	</tr>
</table>
<p>Comments*:<br>
<input type="hidden" name="product_id" value="23">
<input type="hidden" name="form_id" value="form1">
<input type="hidden" name="language" value="English">
<textarea name="comment:" rows="3" col="30"></textarea><br>
<input type="submit" value="Submit form">
</form>
</body>
</html>
```
##### (a) Draw how the above HTML code will appear on a contemporary browser.
![alt text](https://github.com/OrangePass/csc309review/blob/master/src/img/april2015q2.png "别瞅了，这就是答案")
##### (b) What is the name of the destination URL (the webpage that will handle the submitted information)?
Destination URL:
##### (c) How many variables become available to the destination URL (after submitting the form)?
Number of Variables:
##### (d) List the variable name and variable value of all the variables that become availabe in the destination URL if a user submits the above form as-is (without filling-in any extra fields). If a variable is empty or null just indicate its value as "N/A" (Not Available).
| Variable Name | Variable Value|
| ------------- |:-------------:|
|               |               |
|               |               |
|               |               |
|               |               |
|               |               |
|               |               |
#### Question 3
You are given a web page with any arbitrary number of images, videos, and information about them. Write a Javascript function "change()" that will remove or hide all the information in the page and display only the images. A snippet of the webpage's html is provided below. Your code should work for any arbitrary numbe of img or any other elements. Partial marks will be granted for providing adequate pseudocode as an answer.
```html
<body>
	<div>
		<a href="http://www.utoronto.ca">
		<img id="logo" src="https://github.com/OrangePass/csc309review/blob/master/src/img/uoftlogo.png" width="100px"></a>
		<h1>Question 1</h1>
		<div>
			<img id="header" src="header.jpg" width="150px" />
			<video width="320" height="240" controls>
				<source src="movie.mp4" type="video/mp4">
				<source src="movie.ogg" type="" media="video/ogg">
				Your browser does not support the video tag.
			</video>
		</div>
		......
		<!--Any arbitrary number of img or other elements -->
		......
		<a onclick="change()" href="#">Show Images</a>
	</div>	
</body>
```
Write your code below:
```html
<script type="text/javascript">
function change() {
	// go over each tags, hides every tags except html/body
	var objs = document.all;
	for (var j=0; j<objs.length; j++) {
		if (objs[j].nodeName.toLowerCase()=='html' || objs[j].nodeName.toLowerCase()=='body') {
			continue;
		}
		objs[j].style.display = 'none';
	}
	
	// get each img tag
	var img = document.getElementsByTagName('img');
	for (var i=0; i<img.length; i++) {
		
		// "display" img tags
		img[i].style.display = 'block';
		
		// set the parent of each img tags
		var tempObj = img[i];
		while (tempObj.parentNode.nodeName.toLowerCase() != 'body') {
			tempObj = tempObj.parentNode;
			tempObj.style.display = 'block';
		}
	}
}
</script>
```
#### Question 4
##### (a) Write HTML code that represents the following HTML form. Your form should send the submitted request using the GET method to a new webpage with the name "form_submitted.php". You do not need to make any validation on the client side.
![alt text](https://github.com/OrangePass/csc309review/blob/master/src/img/april2015q4.png "别瞅了，我自己做的")
```html
<html>
<body>
    <h1>Login Form</h1>
    <form method="get" action="form_submitted.php">
        <table>
            <tr>
                <td>Login:</td>
                <td>
                    <input type="text" name="login">
                </td>
            </tr>
            <tr>
                <td>Password:</td>
                <td>
                    <input type="password" name="password">
                </td>
            </tr>
            <tr>
                <td>
                    <button type="submit">Log in</button>
                </td>
            </tr>
        </table>
    </form>
</body>
</html>

```
##### (b) How does the URL request that is sent to the server look like when a user fills the above form with the following information and clicks the submit button(login: admin, password:csc309)?
```
URL = http://localhost/form_submitted.php?login=admin&password=csc309
```
##### (c)
```php
<?php

if ($_GET['login'] == $_GET['password']) {
    echo 'Error, Login Failed';
} else {
    echo 'Login Successful';
}
?>
```
#### Question 5
##### (a) Given the XML document below, write a JSON document that carries the same information.
### XML
```xml
<book category="web">
    <title lang="english">XQuery Kick Start</title>
    <author>James McGovern</author>
    <author>Per Bothner</author>
    <author>Kurt Cagle</author>
    <year>2003</year>
    <price>49.99</price>
    <store address='24 Bay St', city='Toronto', province='On' code='M5T3A1' />
</book>
```
### JSON
```json
{
  "book": {
    "category": "web",
    "content": {
      "title": {
        "lang": "english",
        "content": "XQuery kick Start"
      },
      "author": [
        "James McGovern",
        "Per Bothner",
        "Kurt Cagle"
      ],
      "year": "2003",
      "Price": "49.99",
      "store": {
        "address": "24 Bay st",
        "city": "Toronto",
        "province": "ON",
        "code": "MSY3A1"
      }
    }
  }
}
```
##### (b) Given the JSON data you produced and the following expression that gives you access to it:
```javascript
var data = JSON.parse(ajax.responseText);
```
write a Javascript expression that would produce:
- The language in which the book is written?
```javascript
var booklanguage = data.book.content.title.lang;
```
- The name of the 3rd author of the book?
```javascript
var author3 = data.book.content.author[2];
```
- The address of the store where the book is available?
```javascript
var storeAddress = data.book.content.store.address;
```
#### Question 6
##### (a)
##### (b)
###### Model 1 All parts of the program are written in Javascript
###### Model 2 A classical server-side program (without use of Ajax)
###### Model 3 A web application using Ajax
#### Question 7
I don't think this question is worth to be done.
Instead, NOSQL will appear in the EXAM.
#### Question 8
##### (a) Which architectural design pattern have you used in your project?
###### Our projects' web architechtural design is:
##### (b) Describe two differences between 3-tier Architecture and MVC Architecture. Draw diagrams for each architecture.
1.
2.
###### Simple diagram for 3-tier architecture:
###### Simple diagram for MVC architecture:
##### (c) What is CSS Image Sprites? Describe the concept with some code demonstration.
##### (d) Describe four tactics (just the terminology of it) to improve the performance of your web based application. Two of them should be related to the client side and two of them should be related to server side.
###### Related to server performance:
1.
2.
###### Related to client performance:
1.
2.
#### Question 9
##### (a) SQL Injection: Give a brief description and a simple SQL example that clearly demonstrates your understanding of the threat.
SQL Injection:
SQL Injection Example:
##### (b) Click Fraud: Give a brief description and an example that clearly demonstrates your understanding of the threat.
Click Fraud:
Clikc Fraud Example (in words):
##### (c) What is IP Spoofing and how it can be used to orchestrate a Denial of Service(Dos) attack to a legitimate website?
##### (d) Give a one-sentence definition of the following four terms:
DNS Cache Poisoning:
HoneyPot:
Salting:
Same-origin Policy:
#### Question 10
##### (a) Mention two ways of making money on a website:
1.
2.
##### (b) Mention two ways to make your website rank higher in search engines:
```markdown
1.Publish relevant content

Quality content is the number one driver of your search engine rankings and there is no substitute for great content. Quality content created specifically for your intended user increases site traffic, which improves your site’s authority and relevance.

Identify a keyword phrase for each page. Think about how your reader might search for that specific page (with phrases like “mechanical engineering in Michigan,” “best applied physics program,” or “Michigan Tech degrees”). Then, repeat this phrase several times throughout the page—once or twice in the opening and closing paragraphs, and two to four more times throughout the remaining content.

Don’t forget to use bold, italics, heading tags, and other emphasis tags to highlight keyword phrases, but don’t overdo it.

Never sacrifice good writing for SEO. The best pages are written for the user, not for the search engine.

2.Update your content regularly

You’ve probably noticed that we feel pretty strongly about content. Search engines do, too. Regularly updated content is viewed as one of the best indicators of a site’s relevancy, so be sure to keep it fresh.

3.Metadata
When designing your website, each page contains a space between the <head> tags to insert metadata, or information about the contents of your page. If you have a CMS site, the UMC web team will have pre-populated this data for you:

Title Metadata
Title metadata is responsible for the page titles displayed at the top of a browser window. It is the most important metadata on your page. For those with a CMS website, the web team has developed an automated system for creating the meta title for each webpage.

Description Metadata
Description metadata is the textual description that a browser will use in your page search return. Think of it as your site’s window display—a concise and appealing description of what is contained within, with the goal of encouraging people to enter.

Keyword Metadata
Keyword metadata are the search phrases that people type when they want to find your page. You’ll want to include a variety of phrases. However, don’t get greedy: if your list becomes excessive, the browser may completely ignore the data. As a general rule, try to keep it to about 6-8 phrases with each phrase consisting of 1-4 words. A great example would be "computer science degree."

4.Have a link-worthy site
Focus on creating relevant links within the text. Instead of having “click here” links, try writing out the name of the destination. “Click here” has no search engine value beyond the attached URL, whereas “Michigan Tech Enterprise Program” is rich with keywords and will improve your search engine rankings as well as the ranking of the page you are linking to.

5.Use alt tags
Always describe your visual and video media using alt tags, or alternative text descriptions. They allow search engines to locate your page, which is crucial—especially for those who use text-only browsers.
```
##### (c) What is PageRank and how it works (give the main idea)? https://en.wikipedia.org/wiki/PageRank
PageRank is an algorithm used by Google Search to rank websites in their search engine results. PageRank was named after Larry Page, one of the founders of Google. PageRank is a way of measuring the importance of website pages. According to Google:

PageRank works by counting the number and quality of links to a page to determine a rough estimate of how important the website is. The underlying assumption is that more important websites are likely to receive more links from other websites.
#### Question 11
- [T] UDP is less reliable than TCP.
      The reason that UDP is less reliable than TCP as a transport protocol is that UDP provides neither error checking nor sequence
numbering.
- [F] Form validation should only be done in client side. Validation can be done both in client and sever side. http://stackoverflow.com/questions/15855770/why-do-we-need-both-client-side-and-server-side-validation
- [T] Cookies are only data, not program code. lecture27.5-cookies_sessions.pdf
- [F] Cookies cannot be used by third-party websites to track user browsing habits.
- [ ] The "Remember Me" feature, where the user's login info is remembered and reused when the user comes back is implemented requries the use of persistent cookies.
- [ ] In asynchronous communication, a user cannot interact with a webpage while new data is loaded from the server.
- [ ] In a 3-tier architecture unconnected tiers should not communicate.
- [ ] Using the universal selector (*) in a Javascript function to do DOM manipulation will increase the performance of your script.
- [ ] XML representation is less verbose thant JSON(i.e., XML is using fewer words to describe a model than JSON), hence XML is the preferred data interchange format in online applications.
- [F] POST method can submit data without encoding. ???
