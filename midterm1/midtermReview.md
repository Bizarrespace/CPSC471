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
  * 

