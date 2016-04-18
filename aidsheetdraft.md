### HTTP
1. **What is the internet?**
 * A collection of computer networks that use a protocol to exchange data.

2 **Internet Protocol (IP)**
 * Simple protocol for data exchange between computers
 * IP Addresses:
  * 32-bit for IPv5
  * 128-bit for IPv6

2 **Transmission Control Protocol (TCP)**
 * Adds multiplexing and reliable delivery on top of IP
  * Multiplexing: multiple programs using the same IP address
  * Reliability: guaranteed, ordered and error-checked delivery
 * Port: a number given to each program or service
  * port 80: web browser (port 443 for secure browsing)
  * port 25: email
  * port 22: ssh
 * Some programs (games, streaming media programs) use simpler UDP protocol instead of TCP

3 **Web Browser Vs Web Server**
 * Web Browser requests and parses documents from web servers
 * Web Server listens for web page requests

4 **Domain Name Server (DNS)**
 * Set of servers that map (translate) written names to IP addresses
  * Example: www.cs.toronto.edu → 128.100.3.40
 * Many systems maintain a local cache called a hosts file

5 **Uniform Resource Locator (URL)**
 * Identifies the path to a document on the web server
 * Upon entering this URL into the browser, it would:
  * ask the DNS server for the IP address of the URL
  * connect to that IP address at port 80
  * request the document from the server by sending
   * GET mashiyat/csc309/index.htm
  * parse and display the resulting page on the screen

6 **Hypertext Transport Protocol (HTTP)**
 * Set of commands understood by a web server and sent from a browser
 * Some HTTP commands (your browser sends these internally):
  * GET filename: download
  * POST filename: send a web form response
  * PUT filename: upload

7 **TCP/IP: Protocol Framework**

<table>
  <tr>
    <th>TCP/IP Layers</th>
    <th></th>
    <th colspan="4">TCP/IP Protocols</th>
  </tr>
  <tr>
    <td>Application Layer</td>
    <td></td>
    <td>HTTP</td>
    <td>FTP</td>
    <td>SMTP</td>
    <td>DNS</td>
  </tr>
  <tr>
    <td>Transport Layer</td>
    <td></td>
    <td>TCP</td>
    <td colspan="3">UDP</td>
  </tr>
  <tr>
    <td>Network Layer</td>
    <td></td>
    <td>IP</td>
    <td>ARP</td>
    <td>ICMP</td>
    <td>IGMP</td>
  </tr>
  <tr>
    <td>Network Interface Layer</td>
    <td></td>
    <td>Ethernet</td>
    <td>Token Ring</td>
    <td colspan="2">Other Link-Layer Protocols</td>
  </tr>
</table>

8 **TCP/IP**

9 **Types of Connection (TCP/UDP)**
* Connection oriented model
 * Like phone calls
 * Uses Transmission Control Protocol (TCP)
 * Defined ordering of messages and acks
* Connectionless model
 * Like sending letters via postal service
 * Uses User Datagram Protocol (UDP)
 * More efficient and good for sending broadcasts to many machines

### HTML
1. Hypertext Markup Language (HTML)
 * Describes the content and structure of information on a web page
 * Not the same as the presentation (appearance on screen)
 * Surrounds text content with opening and closing tags
 * Each tag's name is called an element

### LESS & SASS
CSS Pre-processor: converts code written in a preprocessec language to CSS
* DRY principle (don't repeat yourself)
 * Variables
 * Minxins
 * Functions
* Maintainability
* Readability
* Natural Extension
* You	can	change	the	extension	of	.CSS	files	to	.LESS	and	start	typing	LESS	
* You	can	define	namespaces	similar	to	C/C++	that	can	ignore	variables?	
* You	can	use	CSS	funcBons	by	escaping	them

### Document Object Model (DOM)
* web browser builds a model of the web page (the document) that includes all the objects in the page (tags, text, etc)
* All of the properties, methods, and events available to the web developer for manipulating and creating web pages are organized into objects
* Those objects are accessible via scripting languages in modern web browsers
* **Why is this useful?**
 * Because we can access the model too!
 * The model is made available to scripts running in the browser, not just the browser itself
 * A script can find things out about the state of the page
 * A script can change things in response to events, including user requests
 * We have already used this capability in A1

### Session & Cookies
* HTTP is Stateless
 *	it	simply	allows	a	browser	to	request	a	single	document	from	a	web	server	
 *	it	remembers	nothing	between	invoca9ons	
 *	Short	lived	
 *	**EVERY**	resource	that	is	accessed	via	HTTP	is	a	single	request	with	no	threaded	connection	between	them.

* Adding state to HTTP
 * Client Mechanisms:
  * Cookies
  * Hidden Variables
  * URL Rewriting
  * Local Storage
* Server Mechanisms:
 * sessions

* Cookies
 * A	small	amount	of	information	sent	by	a	server	to	a	browser,	and	then	sent	back	by	the	browser	on	future	page	requests.
 * Motivation:
  *	authen9ca9on	
  *	user	tracking	
  *	maintaining	user	preferences,	shopping	carts,	etc.	
 * Set by the server
 * Sent with the HTTP Response header
 * Returned by browser with HTTP Request
 
 * How long does a cookie exist?
 * **session	cookie**	:	the	default	type;	a	temporary	cookie	that	is	stored	only	in	the	browser's	memory	
  * when	the	browser	is	closed,	temporary	cookies	will	be	erased	
  * can	not	be	used	for	tracking	long-term	informa9on	
  * safer,	because	no	programs	other	than	the	browser	can	access	them
 * **persistent	cookie**	:	one	that	is	stored	in	a	file	on	the	browser's	computer	
  * can	track	long-term	informa9on	
  * potentially	less	secure,	because	users	(or	programs	they	run)	can	open	cookie	files,	see/change	the	cookie	values,	etc.
 
 * URL Rewriting： Store	state	in	the	URL:	Rewrite	URLs	so	that	they	include	state	variables		
  *	Each	URL	is	now	a	get	request		
  *	Supported	by	all	browsers		
  *	Requires	all	URLs	contain	all	state	information	(long	URLs)		
  *	Current	submiked	page	represents	current	state independent	of	what	was	done	previously.

* Session - Persistent State：Current	state	is	stored	at	the	server	(i.e.,	in	a	file,	database)	
 *	Each	request	includes	a	token	identifying	the		browsers	session	(tokens	can	be	passed	via	cookies,	hidden	variables,	URL rewriting).		
 *	At	each	request,	the	execu9ng	script	uses	the	token	to	fetch	session	state	
 * Session	hijacking!	Add	unique	value	+	signature

### Web Security
1. Security Goals (Chapter 1)
 * Seven Key Security Concepts:
  1. Authentication
  2. Authorization
  3. Confidentiality
  4. Data / Message Integrity
  5. Accountability
  6. Availability
  7. Non-Repudiation
 * System Example: Web Client-Server Interaction
2. Secure Systems Design (Chapter 2)
 * **Understanding Threats**
  1. Defacement
  * Online Vandalism, attackers replace legitimate pages with illegitimate ones
  * Targeted towards political web sites
  * Ex: White House website defaced by anti-NATO activists
  2. Infiltration
   * An attempt to sneak across a secure place
   * Unauthorized parties gain access to resources of computer system (e.g. CPUs, disk, network bandwidth)
   * Could gain read/write access to back-end DB
   * Ensure that attacker’s writes can be detected
   * Different goals for different organizations
    * Political site only needs integrity of data
    * Financial site needs integrity & confidentiality
  3. Phishing
   * Attacker sets up spoofed site that looks real
    * Lures users to enter login credentials and stores them
    * Usually sent through an e-mail with link to spoofed site asking users to “verify” their account info
     * The links might be disguised through the click texts
     * Wary users can see actual URL if they hover over link
  4. Pharming
   * Like phishing, attacker’s goal is to get user to enter sensitive data into spoofed website
   * Larger number of users is victimized
   * no conscious action is required by the victim
   * DNS Cache Poisoning – attacker is able to compromise DNS tables so as to redirect legitimate URL to their spoofed site
     * DNS translates URL to IP addresses
     * Attacker makes DNS translate legitimate URL to their IP address
     * the result gets cached, poisoning future accesses
  5. Insider Threats
   * Attacks carried out with cooperation of insiders
    * Insiders could have access to data and leak it
    * Ex: DB and Sys Admins usually get complete access
   * Separation of Privilege / Least Privilege Principle
    * Provide individuals with only enough privileges needed to complete their tasks
    * Don’t give unrestricted access to all data and resources 
  6. Click Fraud
   * Targeted against pay-per-click ads
   * Attacker could click on competitor’s ads
    * Uses up competitor’s ad budgets
    * Gains exclusive attention of legitimate users
   * Site publishers could click on ads to get revenue
   * Automated through malware such as botnets
  7. Denial of Service
   * Attacker supply server with an excess of packets causing it to drop legitimate packets
    * Makes service unavailable, downtime = lost revenue
   * Particularly a threat for financial and ecommerce vendors
   * Can be automated through botnets
  8. Data Theft/Loss
   * Several Examples: BofA, ChoicePoint, VA
    * BofA: backup data tapes lost in transit
    * ChoicePoint: fraudsters queried DB for sensitive info
    * VA (Veterans Affairs): employee took computer with personal info home & his home was burglarized
   * CA laws require companies to disclose theft/loss
   * Even for encrypted data, should store key in separate media
3. Client State Manipulation (Chapter 7)
4. SQL-Injection (Chapter 8)
5. Password Security (Chapter 9)
6. Cross-Domain Security in Web Applications
