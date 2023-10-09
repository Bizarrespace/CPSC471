# Handout 6
1) HTTP is known as a stateless protocol. What does this mean?
  * Each request and response between a client and a server are independent of each other, and the server does not maintain any ifo about past client requests
  * Makes things simpler, no need to maintain or recover state info between multiple transactions
2) What is the difference between HTTP persistent and non-persistent connections?
  * Non-per: Separate TCP connection is opened and closed for each object requested and sent between client and server, downloading mutple objects requires multiple connections.
  * Per: Single TCP connection opened, multiple objects can be sent over this connection. Connection closed after transfer of objects is complete.
3) What are advantages and drawbacks of persistent and non-persistent connections?
  * Adv of per: Reduces response time for client requests, lower overhead for opening and closing connections
  * Dis of per: Idle connections, connection consume server resources for nothing if the connection is idle.
  * Adv of non-per: Robustness, if a crash or failure, only affects the current request and not the whole session of requests. 
  * Dis of non-per: Requires 2 round trip times per object, increasing response time.
  * Higher overhead for operating system due to multiple TCP connections
4) Describe the basic structure of HTTP request and HTTP response:
  * Request: request line(method, URL, and HTTP version), header lines(containing key-value pairs), and an optional message body.
  * Response: Status line(protocol, status code, and status phrase), header lines (containing key-value pairs), and a message body( containing the requested data)
5) What is round trip time (RTT)? How many RTTs does it take to fetch a webpage from a server explain
  * Time it takes for a small packet to get from client to the server and back. Non-per HTTP connections, takes 2 RTTs to fetch single object from server: One RTT to initiate the TCP connection, another RTT for the HTTP request and the first few bytes of the HTTP response to return.
6) Dif between HTTP GET and HTTP POST methods?
  * GET: Used to request data from a specified resource
    * Can include user data in the URL
  * POST: Used to send data to a server to create or update a resource
    * Sends user data in the message body
7) What HTTP message fields are used for implementing web cookies?
  * "Set-Cookie" header field in the HTTP response message and the "Cookie" header field in the subsequent HTTP request message
8) How long (RTT time) would it take to retrieve a webpage containing 10 negligibly small images using a. Persistent connection and b.non-per connection
  * Per, little as 1 RTT for all the referenced objects, as multiple objects can be sent over a single connection
  * Non-per: 2 RTTs per object, for 10 images, would take 2 * (1 + 10) = 22 RTTs, each image needs a separate connection and need the first 2 RTT to establish connection and request and receive objects
9) What are the two key advantages of web proxies?
  *
