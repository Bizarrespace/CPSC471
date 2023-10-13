# Chapter 2 Quiz

* P2P does not use HTTP 

* Transport services that are provided to app by TCP:
  * Flow control, congestion control, loss-free data transfer
 
* What is an HTTP cookie used for?
  * Code used by server, to access info server had eaeriler stored about an eariler interaction with this web <ins>browser</ins>

* HTTP GET
  * Be careful when looking at the languages
  * the "q" is the quality factor, the lower the number less prefered the language to the left of it is
 
* HTTP reply
  * If we are using HTTP 1.0 then TCP onnections do not stay open persistently
 
* Web caching
  * Caching gives benefit of faster page load, if web cache in client's instituional network
  * Also caching allows for less bandwidth coming into an institutional network where the client is lcoated, if cache is also located in that institutional network.
 
* HTTP/2 VS HTTP/1.1
  * Persistent connection
  * Large object to be broken down into smaller pieces
    * Preveting large object from focing many smaller objects to wait their turn
   
* What's in an HTTP reply?
  * A response code
  * A response phrase associated with a response code
 
* Purpose of the If-Modified-Since field in a HTTP GET request message
  * Indicate to the server that the client has cached this object from a previous GET, and the time it was cached.
 
* Purpose of a cookie value in the HTTP GET request
  * Cookie value itself doesn't mean anything.
  * It is just a value that was returned by a web server to this client during an earlier interaction.
 
* Third party cookies
  * Are explicitly mentioned in new privacy laws such at the EU General Data Protection Regulation (GDPR).
  * Provide a mechanism for a website to track a browser's accesses to multiple other websites.
 
* The following characteristics apply to HTTP only:
  * Server port 80
  * Uses blank line(CRLF) to indicate end of request header
  * Operates mostly as a client pull protocol
 
* Characteristics of SMTP only:
  * Uses CRLF.CRLF to indicate end of message
  * Server port 25
  * Operates mostly as a client push protocol
 
* Characteristics of both HTTP and SMTP:
  * Persistent TCP connection to transfer multiple objects
  * ASCII command/response interaction
  * Status codes

* which e-mail protocol?
  * Pushes email from a mail client to mail server: SMTP
  * Pulls email to a mail client from a mail server: IMAP
  * Pulls mail from one mail server to another mail server: Neither SMTP nor IMAP
 
* Function of DNS server in DNS hierarchy:
  * Authoritative:
    * Provides authoritative hostname to IP mappings for org's named hosts
  * Local:
    * Replies to DNS query by local host by contacting other DNS servers to answer the query.
  * Top Level Domain (TLD):
    * Responsible for a domain (e.g., *.com, *.edu); knows how to contact authoritative name servers.
  * DNS root server:
    * Highest level of the DNS hierarchy, knows how to reach servers responsible for a given domain (e.g., *.com, *.edu).
   
* True property of local DNS server:
  * Decrease Name-to-IP address resolution time when compared to querying into the DNS hierarchy
    * Because you just get it from the local DNS server, rather than having to ask around
  * Local DNS server record for remote host is sometimes dif from that of authoritative server for that host
    * Reason is that Local is just caching now and then, not always the most up to date data
   
*  The role of an authoritative name server in the DNS
  *  Provides definitive answer to the query with respect to a name in the auth name server's domain

*  Which forms of caching does user benefit from its own requests and the recent requests of others
  *  HTTP Local web caching and Local DNS server caching
    * Reason is that both do caching for a group of people, rather than just one person
    * HTTP browser caching is only for that person, not a group of others

* Streaming video definitions
  * Chunk:
    * Unit of vid, encoded at multiple dif rates, stored in dif files
  * Manifest:
    * File containing the location and encoding rate of files corresponding to video segments in a video
  * DASH:
    * Approach that allows a client to adapt the encoding rate of retrieved video to network congestion conditions
  * Enter deep:
    * CDN approach that stores content in access networks, close to clients

* What is DASH?
  * Dynamic, Adaptive streaming over HTTP
  * vid files into chunks that are encoded at different rates(vid quality)
  * Client plays chunk by chunk, each chunk requested at encoding rate that fits available bandwidth
 
* Characteristics of UDP socket
  * Data from different clients can be received on the same socket
  * socket(AF_INET, SOCK_DGRAM) creates this type of socket
  * The application must explicitly specify the IP destination address and port number for each group of bytes written into a socket
  * Provides unreliable transfer of a groups of bytes (“a datagram”), from client to server 

* Characteristics of TCP socket:
  * When contacted, the server will create a new server-side socket to communicate with that client
  * Socket(AF_INET, SOCK_STREAM) creates this type of socket
  * Provides reliable, in-order byte-stream transfer (a “pipe”), from client to server
  * A server can perform an accept() on this type of socket

* Suppose web server with 5 ongoing connections using TCP port 80, assume no other TCP connections. How many TCP sockets are in use at this server?
  * Going to be 6, reason is that we have 5 from the ongoing connections, and then 1 listening socket for any new TCP connections on port 80
 
* What happens when socket connect() is called?
  * Creates new socket at the client, and connects that socket to specified server

















































