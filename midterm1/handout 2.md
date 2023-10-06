# Handout 2
1) How does the digital subscriber line allow telephy and internet to co-exist on the same link?
  * using different frequencies for data nd voice transmission.
2) What is the function of DSL access multiplexer (DSLAM)?
  * To separate voice and data signals at the central office
  * Data sigs to internet and voice sigs to telephone network
3) What is the main limiation of DSL?
  * As the distance between the user's location and the central office goes up, the signal quality is decreased, resulting in lower data transmission rates
4) Explain structure and function of hybrid fiber coat(HFC) approach to connecting residences on the internet. How does it differ from DSL? What are the advantages? Are there security concerns?
  * Connects residences to internet using combo of fiber-optic and coaxial cables. Uses FDM instead to transmit data an dTV sigs at different freq over shared cable.
  * Higher speeds compared to DSL, but there are secuirty concerns because of the fact that it has to use a shared access network
5) Difference between guided and unguided media?
  * Guided: sigs through solid media like copper, fiber, coax
  * Unguided: Sigs freely through air like radio
6) A B connected through two intervening routers. All links have speeds of 10 bps.
  * A --10bps-->Router---10bps-->Router--10bps-->B
  * A) 10000 / 10 = 1000 * 3(because 3 links) = 3000 seconds
  * B) At each link gotta wait for the entire message to be sent, each message takes 1000 seconds
    * Total time: 3*1000 for the links, and 2*1000 fo rthe routers = 5000 seconds
7) Why is store-and-forward approach necessary?
* Allows routers to check packets for errors, also allows for efficient use of network's bandwidth, waiting for less congrested time to send packet
8) When can packets experience queueing delays or be lost?
* Queuing delays or packet loss can be experienced when arrival rate of packets exceeds the link's transmission rate for period of time
  * The link is not able to send out the packets as fast as it gets packets, and if the memory buffer of the router is full, then it cant hold anymore packets, and packet lost can be experienced
9) Assume that 25 users are fairly sharing a 100 bps link. How long will it take on user to transmit a 20,000 bit file?
* 20,000 / (100/25) = 5000 seconds
10) Assuming a 1,000,000 bps link and users who transmit at a rate of 56,000 bps each, how many users can we support using circuit switching? Packet Switching?
*  circuit switching: 1,000,000 / 56,000 = 17 users rounded down
*  Packet switching: # of users not fixed, depends on current network conditions and users' activity patterns. But this number usually higher,especially when users are not always online. 
