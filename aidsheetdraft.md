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

| TCP/IP Layers           | TCP/IP Protocols |            |                            |      |
|-------------------------|:----------------:|------------|----------------------------|------|
| Application Layer       |       HTTP       | FTP        | SMTP                       | DNS  |
| Transport Layer         |        TCP       | UDP        |                            |      |
| Network Layer           |        IP        | ARP        | ICMP                       | IGMP |
| Network Interface Layer |     Ethernet     | Token Ring | Other Link=Layer Protocols |      |


<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;}
.tg .tg-s6z2{text-align:center}
.tg .tg-baqh{text-align:center;vertical-align:top}
.tg .tg-yw4l{vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-031e">TCP/IP Layers</th>
    <th class="tg-s6z2">TCP/IP Protocols</th>
    <th class="tg-yw4l"></th>
    <th class="tg-yw4l"></th>
    <th class="tg-yw4l"></th>
  </tr>
  <tr>
    <td class="tg-yw4l">Application Layer</td>
    <td class="tg-baqh">HTTP</td>
    <td class="tg-yw4l">FTP</td>
    <td class="tg-yw4l">SMTP</td>
    <td class="tg-yw4l">DNS</td>
  </tr>
  <tr>
    <td class="tg-yw4l">Transport Layer</td>
    <td class="tg-baqh">TCP</td>
    <td class="tg-yw4l">UDP</td>
    <td class="tg-yw4l"></td>
    <td class="tg-yw4l"></td>
  </tr>
  <tr>
    <td class="tg-yw4l">Network Layer</td>
    <td class="tg-baqh">IP</td>
    <td class="tg-yw4l">ARP</td>
    <td class="tg-yw4l">ICMP</td>
    <td class="tg-yw4l">IGMP</td>
  </tr>
  <tr>
    <td class="tg-yw4l">Network Interface Layer</td>
    <td class="tg-baqh">Ethernet</td>
    <td class="tg-yw4l">Token Ring</td>
    <td class="tg-yw4l">Other Link=Layer Protocols</td>
    <td class="tg-yw4l"></td>
  </tr>
</table>
