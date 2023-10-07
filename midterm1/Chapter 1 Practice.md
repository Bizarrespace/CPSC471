# Stuff I missed/Hard to remember
* Matching network to their speeds:
  * Ethernet: 100's Gbps
  * 4G Cellular LTE: Wireless 10's Gbps
  * 802.11 Wifi: Wireless 10's to 100's of Gbps
  * Cable access network: wired, 10's of Gbps
  * Digital Subscriber line: wired, 10's Gbps
* Packet Switching vs Circuit switching:
  * Cir uses FDM and TDM
* Packet vs Circuit when it comes to average use rates, and traffic rates over channel with 10Mbps:
  * if 5 users, with average use rate of 2.1, and they generate traffic at rate of 15 Mbps, either one works well
  * If average use rate is 2, and gen traffic at 2, then circuit is great
  * If avg is .21, and gen traffic at 15, packet is great because most of the time we wont hit that 10
* Formula for transmission rate:
  * L / R
  * L is the amount of bits you are transferring
  * R is the Transmission rate
* Formula for propagation delay:
  * Prop speed / distance
* Throughput
  * When dealing with throughput, if we have a shared link, remember to divide it by the total # of users to get the speed of that link
* Layers in the internet protocol stack and their functions:
  * Application layer: Protocols that are part of a distributed network application
  * Transport layer: Transfer of data between one process and another process (typically on different hosts)
  * Network layer: Delivery of datagrams from a source host to a destination host
  * Link layer: Transfer of data between neighboring network devices
  * Physical layer: Transfer of bit into and out of a transmission media
* What's a packet really called?
  * Application layer: Message
  * Transport layer: Segment
  * Network layer: Datagram
  * Link layer: Frame
  * Physical layer: Bit
* ASK PROFESSOR
* ![image](https://github.com/Bizarrespace/CPSC471/assets/78052960/42a46e61-13f2-4f2b-92b9-cba7cc7d6ac4)
  * H3: Transport layer
  * H2: network layer
  * H1: Link layer
* What is "encapsulation?"
  * Taking data from the layer above, adding header fields appropriate for this layer, and then placing the data in the payload field of the packet for that layer
* Networking History, when did it happen?
  * Early studies of packet switching by Baran, Davies, Kleinrock.
    * Early 1960s
  * First ARPAnet node is operational:
    * Late 1960s
  * Internetting: DARPA researchers connect three networks together:
    * 1970's
  * Internet protocol (IP) is standardized in RFC 791:
    * Early 1980s
  * Congestion control is added to the TCP protocol:
    * Late 1980s
  * WWW starts up:
    * 1990s
  * Software-defined networking begins:
    * 2000-2010
  * Number of wireless internet-connected devices surpasses # of connected wired devices:
    * 2010-2020
