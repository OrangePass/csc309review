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
#### Question 4
##### (a)
##### (b)
##### (c)
#### Question 5
##### (a)
##### (b)
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
1.
2.
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
