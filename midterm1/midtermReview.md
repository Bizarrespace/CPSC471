# Core Concepts

* What basic service does the network provide to applications?  
  * Infrastructure that supports web browsing, streaming video, email, games etc.

* What is network edge? Network core?  
  * Edge: Hosts or end systems running network apps  
  * Core: Interconnected routers and network of networks

* Does functionality XYZ (e.g HTTP protocol) reside at network edge or network core?  
  * Edge b/c apps running on the end system

* What is protocol? Why are protocols important in computer networking? Be able to illustrate your understanding using examples.  
  * Set of rules to define the format, order of messages sent and received among network entities, actions taken on message transmission and receipt.  
  * Important because they ensure proper communication btw devices and control the sending and receiving of messages  
  * EX: HTTP, TCP, WiFi, they all have their own protocol to handle packets and how things get done

* What is the difference between circuit switching and packet switching? What are advantages and disadvantages of each?  
  * Cir: end-to-end resources allocated and reserved for call between source and destination. Guaranteed performance, inefficient  
  * Pack: Data broken into packets and transmitted independently. More efficient, but can experience congestion, leading to packet delay and loss

* What sort of applications are most likely to benefit from circuit/packet switching?  
  * Cir: Audio and video apps  
  * Pack: Apps with bursty data, instant messaging, IoT devices, they send small amounts of data now and then.

* Dif network models: p2p, client-server, hybrid  
  * p2p: All devices act as both client and server, can request and provide resources to other devices. BitTorrent, Skype  
  * Client-server: Dedicated server that provdie resources or services to clients. Ex: HTTP, FTP  
  * Hybrid: Combines both p2p and client-server, some nodes act as servers, providing resources to other nodes, while also acting as clients, requesting resources from other nodes.  
    * Ex: Content delivery network (CDN), dedicated servers and p2p connections to distribute content efficiently

# Accessing the internet

* What is the difference between DSL and HFC?
  * DSL: Uses existing telephone lines to provide internet, slow speeds, not shared with others, so consistent speeds
  * HFC: Combo of fiber-optic cables and coaxial to deliver internet. Way faster, shared among others, so varying speeds

* How does HFC compare to fiber-optic? Why does fiber-optic not yet replace HFC?
  * Fiber-optic much higher speeds, 10-100's Gbps, compared to HFC 40Mbps-1.2Gbps
  * Lower latency, speed of light travel time, compared to electrical signals
    * Dis:
      * High cost, have to replace the HFC infrastructure already in place, not available everywhere
      * HFC can leverage existing coaxial cable infrastructure, so easier and more cost efficient

* How are ISPS structured? Be able to compare and contrast different approaches and their practicality
  * Hierarchical manner
    * Tier 1 ISPs: Large, well-connected networks with national or international coverage. Backbone of Internet, exchange traffic with other Tier 1s
      * Example: AT&T, NTT
    * Tier 2 ISPs: regional or national ISPs, connect to Tier 1 for access to global internet
    * Tier 3 ISPS: Local or access ISPs, provide internet to end-users, residential customers, businesses etc.
      * Connect to Tier 2 or 1 for broader internet
    * Content provider Networks: Networks operated by large content providers, Google, Facebook.
    * Make own networks to bring services and content closer to end-users, bypassing Tier 1 and Tier 2
  * Various approaches to connect their networks, peering agreements, Internet Exchange points, transit agreements. 

# Physical Media

* What is the dif btw guided and unguided media? Give Ex. What are the Adv and dis of each?
  * Guided: Wired media, physical transmission media uses physical conductor to transmit signals.
    * Ex: Coaxial cables, fiber-optic cables:
    * Adv: higher data trans speeds
      * More secure less prone to interference
    * Dis: Installation and maintenance harder
      * susceptible to physical damage
  * Unguided: Wireless media, electromagnetic waves to transmit signals through air or space, without physical conductor
    * Ex: Radio waves, microwaves
    * Adv: Greater flexibility
      * Easier to install, works in remote/hard to reach locations
    * Dis: Lower speeds
      * More susceptible to interference
      * Less secure

* What are the differences between GEO and LEO satellites?
  * GEO(Geostationary Earth Orbit): positioned at altitude 22,236 miles above Earth's equator, orbit Earth same speed as rotation. So looks stationary. Used for communication, broadcasting, weather monitoring
  * LEO(Low Earth orbit): 310 - 1240 miles. Moves quicker than earth, and provide coverage for small area.
    * Used for lower latency communications, Earth observations

# Quantitative Analysis of Networks
* How many users can you support given the following network parameters? In circuit
switched networks (TDM & FDM)? 
  * depends on # of users that can be supported depends on the available bandwidth and the bandwidth requirements of each user
  * TDM: Link div into time slots, each user is assigned a slot
  * FDM: Div into frequency bands, each user assigned a band

* How does store-and-forward architecture affects performance?
  * introducing delays at each intermediate node (e.g., routers) in the network, packet stored in buffer, then forwarded to next node
  * Adds processing, queuing, and transmission delays.

* Be able to compute different kinds of delays (e.g. processing, transmission, propagation, queuing, and end-to-end delays)
  * For trans: L bits over R link rate, for given example: 10000/1000 = 10 seconds

* Understand and be able to solve problems on how traffic intensity affects queuing delays
  * More traffic = more chance of packets waiting in the queue, leading to higher queuing delays

* When does packet loss occur?
  * When the buffer becomes full, no space to store incoming packets.
  * Arrival rate of packet more than processing rate

* Be able to compute maximum network throughput
  * Capacity of link, # of users, efficiency of network protocols used. 

* What is the difference between frequency division multiplexing and time division multiplexing? What are the advantages and disadvantages? Be able to solve related problems:
  * – Example: How can I partition a 10000bps link among 10 users using time division multiplexing?
  * FDM allows simultaneous transmission of multiple signals, while TDM allows users to take turns using the entire bandwidth.
  * To partition 10,000bps link among 10 users using TDM, each user would assinged a time slot with bandwidth of 10,000/10 users, so 1000 bps per user

# Protocol Stack Concepts

* Why use a layered protocol model?
  * Simplify design, implementation and management of complex network systems by dividing them into smaller, more manageable components

* Where is each layer implemented?
  * Implemented in different parts of the network stack, application, transport, network, an link layers

* What is the function/services of each layer?
  * Specific functions and services, such as data transmission, routing, error detection, and flow control
  * [Get the list of what they do from one of the handouts]

* What is the dif btw TCP/IP and OSI models? Compare and contrast two models.
  * Main dif is # of layers and organization
  * The TCP/IP model has four layers (Application, Transport, Network, and Link)
  * OSI model has seven layers (Application, Presentation, Session, Transport, Network, Data Link, and Physical)
  * TCP more widely used in practice

* Trace how the packet traverses the protocol stack.
  * Starts at the application layer, where the data is generated.
  * The data is then passed down through the transport, network, and link layers, with each layer adding its own header information
  * Receiving end, packet passed up through the layers, each layer processing and removing its respective header info
  * in the end delivering data to the application layer

# Application Layer
* Where do apps run?
  * End systems, computers, smartphones and servers. Communicate using app-layer protocols that define the rules and formats for exchanging messages btw apps

* Understand all application-layer protocols discussed in class:
  * HTTP: Hypertext Transfer Protocol, transferring web pages and related resources between a web server and a client (usually a web browser).
    * Request-response model, client sends request, server responds with resource or error message\
  * FTP: (File Transfer Protocol): Used for transferring files between a client and a server.
    * Uploading, downloading, managing files on server.
    * Uses two separate connections for control (commands) and data transfer.
  * SMTP (Simple Mail Transfer Protocol): Sending email messages between mail servers.
    * Text-based protocol, uses a series of commands and responses to transfer email messages from the sender's server to the recipient's server.
  * POP (Post Office Protocol): Used for retrieving email messages from a mail server to a client.
    * Simple protocol that does not support advanced features like folders or message synchronization.
  * DNS (Domain Name System): A distributed, hierarchical system that translates human-readable domain names (e.g., www.example.com) into IP addresses (e.g., 192.0.2.1).
    * Series of name servers organized to resolve domain names to IP addresses
  * Example question:
    * Requested page /index.html
    * Domain name: www.google.com
    * Persistent, we know this because of "Connection: keep-alive" header

* Why is it important for clients to specify both server’s IP address and port number?
  * Uniquely identify the server and the specific service they want to access, IP to get the computer or server, port # to get the process

* What are two different types of transport layer services?
  * Connection-oriented (e.g., TCP) and connectionless (e.g., UDP).

* What is the difference between TCP and UDP transport?
  * TCP provides reliable, connection-oriented communication with error checking and flow control,
  * UDP provides unreliable, connectionless communication without error checking or flow control.

* What is the difference between stateful and stateless protocols?
  * Stateful protocols maintain information about the state of communication between the client and server
  * Stateless protocols do not store any information about previous interactions.

* What is the difference between HTTP persistent vs non-persistent connections?
  * HTTP persistent connections allow multiple requests and responses to be sent over a single TCP connection
  * Non-persistent connections require a new TCP connection for each request-response pair.

* Understand how cookies work.
  * Small pieces of data stored by a web browser on the user's device
  * Used to maintain state and track user preferences, login information, and other data across multiple visits to a website.

* What is the purpose of web caching? What are its advantages?
  * Store copies of frequently accessed web content, reducing the load on the origin server and improving the response time for the user
  * Advantages include reduced latency, lower bandwidth usage, and decreased server load.

* What is conditional GET? Illustrate its usage.
  * Allows a client to request a resource only if it has been modified since a specified date.
  * Improves performance by only downloading updated content.

* Understand the purpose of DNS, DNS hierarchy, local name servers, root servers, top-level domain servers, and authoritative servers. Be able to trace DNS lookups.
  * Purpose: Translates human-readable domain names (e.g., www.example.com) into IP addresses (e.g., 192.0.2.1).
  * Name servers organized in a hierarchy:
    * Root name servers: top-level name servers in DNS hierarchy
      * Provide information about the Top-Level Domain (TLD) name servers and are responsible for directing queries to the appropriate TLD name servers.
    * Top-Level Domain (TLD) name servers: Responsible for managing the domain names within a specific TLD, such as .com, .org, or .edu.
      * Provide info about authoritative name servers for each domain within their TLD.
    * Authoritative name servers: Provide the actual IP address mappings for a specific domain.
      * Store the DNS resource records for the domain and respond to queries with the corresponding IP addresses.
    * Local name servers: AKA Caching or recursive name servers, usually provided by ISP or organization's internal network
      * Cache DNS query results to speed up subsequent queries
      * Forward queries to the appropriate name servers in the DNS hierarchy if the information is not already cached.
  * Flow:
    * DNS lookup is performed, the query is sent to a local name server, which checks its cache for the requested domain name.
    * If the information is not in the cache, the local name server forwards the query to a root name server, which directs the query to the appropriate TLD name server.
    * TLD name server then provides the information about the authoritative name server for the requested domain.
    * The authoritative name server is queried, and it returns the IP address for the domain name.

* What are different types of DNS resource records? What is each one used for?
  *  A (IPv4 address), AAAA (IPv6 address), CNAME (canonical name), MX (mail exchange), and NS (name server).
    *  A (Address) record: This record maps a domain name to an IPv4 address.
      * Used to locate a host within the domain, domain name into an IP address used for routing purposes.
    * AAAA (IPv6 Address) record: Similar to the A record,
      * Maps a domain name to an IPv6 address. It is used for routing purposes in IPv6 networks.
    * CNAME (Canonical Name) record: This record creates an alias for another domain name, allowing multiple domain names to point to the same IP address.
    * MX (Mail Exchange) record: This record specifies the mail server responsible for handling email for a domain.
    * NS (Name Server) record: This record specifies the authoritative name server(s) for a domain.

* What are the steps involved in registering a new domain?
  * Choosing a domain name
  * Selecting a domain registrar, providing contact and technical information
  * Paying a registration fee
  * Registrar then creates the necessary DNS records and submits them to the appropriate DNS servers.

* What is DNS caching? What are its benefits?
  * Process of storing DNS query results temporarily to speed up subsequent queries for the same domain name.
  * Reduced latency, decreased load on DNS servers, and improved performance.

* What is a socket?
  * Know the system calls/functions used in sockets programming. For example, what does listen() system call do?
    * Socket is an endpoint for sending and receiving data across a network, like a door, to establish connection btw 2 processes
    * Key functions:
      * socket(): This function creates a new socket.
      * bind(): This function associates a socket with a specific address (IP and port).
      * listen(): This function is used by a server to mark a socket as a passive socket that will be used to accept incoming connection requests.
      * connect(): This function is used by a client to establish a connection with a server.
      * send(), recv(): These functions send and receive data over a connected socket.
      * sendto(), recvfrom(): These functions are used to send and receive data over a connectionless socket (e.g., UDP).
      * close(): This function closes a socket and releases its resources. 

* Know the difference between flow of control in server and client.
  * Server typically listens for incoming connections and processes requests from multiple clients.
  * Client initiates connections and sends requests to a server.

* Know the difference between sockets programming using TCP and UDP.
  * With TCP, you need to establish a connection between the client and server before exchanging data.
    * Three-way handshake to set up the connection and ensure both parties are ready to communicate.
  * UDP does not require a connection setup
    * Allowing for faster communication initiation but without the reliability guarantees of TCP.
  * In TCP, error handling is built into the protocol, with automatic retransmission of lost or corrupted data segments
  * UDP, error handling must be implemented at the application level if needed, no automatic error recovery

# Transport Layer
* What basic service does the transport layer deliver?
  * Provide logical communication between application processes running on different hosts.
  * Breaking application messages into segments and passing them to the network layer at the sender's end
  * Then reassembling segments into messages and passing them to the application layer at the receiver's end
  * Protocols include TCP and UDP

* Given systems with opened sockets and packets labeled with IPs and port numbers, to what socket in the receiver will each packet be de-multiplexed to? E.g. slides 7-13 of Transport Layer.
  * Will be de-multiplexed to the receiver socket that matches the packet's destination port number.
  * Uses the destination port number to direct the segment to the appropriate socket

* UDP provides a “best-effort” service. What does this mean?
  * It does its best to deliver the packets but does not guarantee delivery.
  * Does not provide robust error checking or correction, so packets may be lost or delivered out of order

* What are different fields of the UDP packet? What is their function?
  *  Source port number, destination port number, length, and checksum.
  *  Source and destination port numbers are used for multiplexing and demultiplexing data to the correct application.
  *  Length field specifies the length of the UDP header and data.
  *  Checksum is used for error checking

* Given e.g. words 000110010, 010110011, and 000111111 that comprise the UDP packet, what is the checksum?
  * Steps:
    * Add the numbers together in binary form
```
0 + 0 = 0
0 + 1 = 1
1 + 0 = 1
1 + 1 = 0, carry over the 1, i.e. 10
```
* ![image](https://github.com/Bizarrespace/CPSC471-Computer-Communications/assets/78052960/7737c389-a7d4-4ef2-912a-ce09ae7a7aee)
  * If the leftmost spot is a 1, then you wrap it around, add it to the to rightmost digit
  * Then after wrapping, you do 1s complement, turn 1s into 0s and 0s into 1s

* Given a reliability state machine, be able to answer questions
  * LOOK AT EXAMPLE IN CHAP 3 AND UNDERSTAND
  * E.g:
    * Sender sends a packet that is lost, it will not receive an acknowledgment (ACK) from the receiver.
    * After a timeout period, the sender will retransmit the packet

* What is the purpose of sequence numbers?
  * Keep track of the order of packets
  * Used to ensure that packets are delivered in the correct order and to detect and handle duplicate packets

* How does e.g rtd3.0 handle packet loss? Packet corruption? How does the receiver react when receiving a packet with unexpected sequence number? Be able to answer similar questions.
  * Rdt3.0 handles packet loss by using timeouts and retransmissions.
  * If a packet is corrupted, the receiver will send a negative acknowledgment (NAK), and the sender will retransmit the packet.
  * If the receiver receives a packet with an unexpected sequence number, it will discard the packet and resend the ACK for the last correctly received packet

* What services does TCP provide?
  * Reliable, in-order delivery of packets, congestion control, flow control, and connection setup

* What is the problem with stop-and-wait protocols?
  * inefficient
  * The sender sends one packet and then waits for an acknowledgment from the receiver before sending the next packet.
  * Sender is idle for the time it takes for the packet to travel to the receiver and for the acknowledgment to travel back
    * If propagation delay is high, then it will be a lot of time for this protocol

* Be able to calculate sequence and ACK numbers of protocols.
  * Client sequence # 2000, Server 4000. Client sends 300 byte segment to server. Assuming segment received successfully, what will be the sequence # and the acknowledgement in server's response?
    * Sequence # sent by client will be 2000
    * Server receives segment successfully, sends acknowledgment w/ sequence # of 4000(its initial sequence #)
      * Sends acknowledgement # of 2301(client's sequence # plus size of received segment + 1)

* Why must TCP estimate RTT? How does TCP estimate RTT. Example: What is EstimatedRTT? How is it computed?
  * Must estimate Round-Trip Time (RTT) to set the timeout period for acknowledgments.
  * If ack is not received within the estimated RTT, the packet is assumed to be lost and retransmitted.
  * TCP estimates RTT by taking a weighted avg of measured RTT for each segment and previous estimated RTT

* How does TCP handle lost segments?
  * Ex: TCP and client choose sequence # 500 and 800. Clients send 3 back-to-back segments. The size of the segments is 400, 600, 900.
    * Suppose the second segment gets lost, but the first and third segments arrive successfully.
    * What ack will the server send when receiving these segments?
      * Handles lost segments by using acknowledgments and retransmissions.
      * If a segment is lost, the sender will not receive an acknowledgment for that segment.
      * How it would play out:
        * Server 500, Client 800
        * Client sends first seg of 400. Sequence # for this would be 800(initial) + 400(data size) = 1200
        * Ser gets this and sends ack, which is going to be 1200 (800 - 1200)
        * Client now sends second seg of 600, sequence # is going to be 1200 + 600 = 1800, but lets say this segment gets lost
        * Sever waiting for the segment with sequence # of 1200
        * Client now sends third seg of 900. Sequence # is 1800(previous sequence #) + 900(data size) = 2700 (1800 - 2700)
        * Ser receives 1800 - 2700 and gets confused because it never got the buffer for 1201 - 1800
        * Sends duplicate ack for last segment recieved in order, which ended at 1200. Telling it was good up till 1200
        * Client gets dup ack so it resends second segment with sequence 1800(1200 + 600).
        * Ser sends ack for 1800, so client knows second segment received, doesnt need to send third because server got it
          * Client knows because server send ack for 1800 + 900 = 2700 (1800 - 2700)
        * Communication continues with enxt sequence # after third segment of 2700
        
* Understand the concepts behind fast retransmit, and be able to solve problems.
  * Ex: Sender sends 6 packets of size 100. The initial Sequence # of the sender is 300. Suppose packet 3 is lost. All other packets and ACKs arrive successfully. What ACK # will the sender receive? When will the sender perform a fast retransmit?
    * The ACK that the sender receives is going to be
      * ACK 400, successful receipt of packet 1
      * ACK 500, succ receipt of packet 2
        * Server then receives packet 4, and see that there is a gap in the sequence numbers
        * So it sends ACK 500 again for that packet 4, does the same with packet 5, and 6 because the gap is still there
      * When the sender receives 3 Dup ACK of 500, it then performs a fast retransmit of packet 3

* Be able to solve problems related to flow control
  * Example: The receiver has a buffer size of 10 KB. The buffer already contains 5 KB of data. What (rwnd) window size will the sender advertise?
  * Flow control used to prevent sender from overwhelming a receiver by sending too much data too fast.
  * Receiver advertises a window size(rwdn) to sender, showing how much data it can accept.
    * In the example, if buffer size is 10 KB, and already has 5KB of data, window size of 5KB will be advertise
      * This shows that only 5 more KB is able to be accepted

* Why does TCP use a 3-way connection rather than 2-way (slide 78 of Transport Layer)?
  * Uses 3-way so that both parties is able to ensure that the other is ready, also allows them to agree on initial sequence numbers.
  * Help prevent data lost and duplication
    * Example: If it was a 2-way, client would ask if server ready, server says ready, but then client does not say if it knows if the server is ready,
      * Also if client never received SYN ACK by server it might send another SYN which the server might think that the clients wants another connection

*  What sequence of messages are exchanged when setting up a connection? (slide 76 of Transport Layer)?
  *  Client sends SYN packet to server
  *  Server responds with SYN-ACK packet
  *  Client sends ACK packet to server 

* What sequence of messages do server and client exchange when closing the connection? (slide 82 of Transport Layer).
  * Client sends FIN packet to server
  * Server responds with ACK packet, and then sends its own FIN packet
  * Client responds with ACK packet

* What is the difference between Go-Back-N and Selective-Repeat? Be able to solve problems such as:
  * Example: Suppose the sender sends 5 packets with sequence numbers 1-5, respectively. Packet 3 gets lost. What ACKs will the receiver send (assuming all packets arrive successfully) when using Go-Back-N and Selective-Repeat. What packets will be resent and when?
  * Go-Back-N retransmits all packets from lost packet to the last transmitted packet
  * Selective Repeat only retransmits the lost packet.
  * Selective more efficient in terms of bandwidth usage, but requires more memory and processing power than Go-Back-N
    * Example:
      * ACKs that the receiver sends when using Go-Back-N would be:
        * ACKs for packets 1 and 2, when 4 arrives, receiver send ACK for packet 2 again, showing that it expected 3
        * Sender once it gets the dup will retransmit packets 3, 4, 5
      * ACKs that the receiver sends when using Selective Repeat Protocol:
        * Receiver sends ACKs for packets 1,2,4,5
        * Sender when not getting ACK for 3 within a certain timeout period, will retransmit only packet 3

# Sample Questions
* Suppose a DNS resource record has Type=CNAME.
  * A) Value is the hostname of the DNS server that is authoritative for Name 
  * B) Value is the IP address of the host that has the alias hostname Name
  * C) Value is the canonical name of the host that has the alias hostname Name
  * D) None of the above 

* (6 points) Suppose you would like to urgently deliver 40 terabytes (1T = 1000G) data from Boston to Los Angeles. You have available a 100 Mbps dedicated link for data transfer. Would you prefer to transmit the data via this link or instead use FedEx overnight delivery? Explain.
  * 40 Terabytes = 40000 GB = (40000GB * 1000 MB/GB) = 40,000,000 MB / (100Mbps/  1MBps/8Mbps) 12.5MBps = 3200000 seconds / 60 seconds = 53333.3333 mintues / 60(1hr/mins) = 888.88889 hours
  * If overnight is 24 hours, FedEx overnight much better than 888 hours

