1 **What is the internet?**
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
 * 
