# Handout 5
1) Describe the function of each layer of the TCP/IP model:
  * <ins>Application Layer</ins>: Support network applications like HTTP
  * <ins>Transport Layer</ins>: Manages process-to-process data transfer, using protocols like TCP and UDP
  * <ins>Network Layer</ins>: Handles routing of datagrams from source to destination, using IP and routing protocols
  * <ins>Link Layer</ins>: Manages data transfer between neighboring network elements, using tech like WiFi or Ethernet
  * <ins>Physical Layer</ins>: Deals with the transmission of bits "on the wire," so dealing with things such as converting digital data into signals that can be transmitted over the physical medium
2) Advantages of layering network protocols? What are the disadvantages?
  * Adv:
    * Modularity: Eases maintenance and updating of the system
    * Abstraction: Changes in one layer's implementation are transparent to the rest of the system.
    * Organization: Provides clear structure for understanding and discussing complex systems.
  * Dis:
    * Overhead: Each layer may introduce additional processing or data overhead.
    * Inefficiencies: Some layers may duplicate functionality or not be fully optimized for specific use cases
3) Does the application layer reside in the network edge, core, or both? Explain
  * In edge, deals with end systems that are running the network applications
4)  From the POV of the application layer, what are the two fundamental approaches for structuring an application? Explain
  * Client-server: Always-on server with permanent IP, Clients then contaft and communicate with server, clients do not talk to each other
  * Peer-to-peer(P2P): Arbitrary end systems directly communicate with each other, peers request services from other peers and provide services in return. More complex management because of the changing of IPs.
5) What are the adv of the P2P model when compared to client-server model? What are the disadvantages?
  * Self-scalability: New peers bring more service capacity and demands, allowing system to scale naturally
  * No need for central server: Reduces the cost and potential bottlenecks associated with maintaining a central server.
  * Dis:
    * Complex management: Intermittently connected and change IP addresses, making management more challenging
    * Security and reliability: No central authority, more difficult to enforce security measures and ensure reliable service
6) Is the IP address all we need to communicate with the process on the remote system? If so, then explain why, if not then explain what is missing why it is essential?
  * Also need port number to be associated with the process on the host. The IP identifies the host, and the port number identifies the individual process.
7) To send a message over the network, the process places the message into the ____.
  * places the message into the socket, like a door. The socket takes the message and relies on the transport infrastructure on the other side to deliver the message to the socket at the receiving process.
8 ) Does the transport layer of the internet provide timing and througput guarantees? If so, then explain how. If not, then explain why not
  * Does not provide timing and throughput guarantees. Has best-effort service, tries to deliver packets as efficiently as possible but does not guarantee delivery or specific performance levels.
9) Fundamental dif between TCP and UDP? What are the adv and disadv of each? Give examples of applications for which TCP is best suit, and do the same for UDP
  * Adv TCP:
    * Reliable data transfer, flow control, congestion control to throttle the sender when network is overloaded
  * Dis TCP:
    * No timing or throughput guarantees, connection setup overhead
  * Example:
    * File transfer, email, bank app
  * Adv UDP:
    * Fast and suitable for apps that can tolerate data loss
    * Lower overhead due to no connection setup and reliability features
  * Adv UDP:
    * Unreliable data transfer, no flow control, congestion control, timing, or throughput guaratees
  * Example:
    * Real-time audio/video streaming, voice over IP
