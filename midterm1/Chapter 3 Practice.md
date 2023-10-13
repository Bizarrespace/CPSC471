# Chapter 3 Quiz
* Transport layer services using TCP
  * Check services provided by TCP protocol
  * Reliable, in order data, congrestion control, flow control
  * Byte stream abstraction, no boundaries btw messages data sent in dif socket send calls at sender.
    * TCP does not preserve boundaries between data sent in separate 'send' operations on the sender's socket.
    * Reason is that TCP sends all data as a continue stream of data
   
* What is multiplexing?
  * Taking data from one socket or more and encapsulating data chuck w/ header info.
  * This creates the transport layer segment, and passing it to the network layer
 
* Multi/Demulti TCP and UDP port numbers:
  * UDP:
    * If multiple clients send to the same destination port number, those segments will be directed to the same socket at the receiving host
  * TCP:
    * If multiple clients send to same destination port number at receiving host, segments will not always b directed to the same socket at the receiving host
    * Reason for this is because of how with TCP we use 4-tuple, source, dest IP and port number
      * Therefore if we have two different clients at different IP addresses than they will be demultiplexed to different sockets
    * This also means that it is much easier for TCP segments from one server to be sent to different clients as long as their IP addresses are different, or their port number is different
   
* UDP preserves app layer message boundaries

* UDP header fields:
  * Source port number
  * Destination port number
  * Checksum
  * length
    * Need length because we need to know when the segment ends
   
* What set of bytes is checksum field in UDP header computed?
  * Entire UDP segment
  * Except checksum field itself, IP sender, and receive address field
 
* What is a checksum?
  * Computed at a sender by considering each byte within a packet as a number, and then adding these numbers (each number representing a bytes) together to compute a sum(checksum)
  * The sender-computed checksum value is often included in a checksum field within a packet header
  * The receiver of a packet with a checksum field will add up the received bytes and compare them with the checksum value in the packet header
    * If two values are different, then receiver knows that one of the bits in the received packet has been changed during transmission from sender to receiver
 
* Limitation of checksum:
  * Can detect a single flipped bit
    * But won't always detect it when a single flipped bit is done in each of the two numbers
    * The receiver can't tell for certain whether errors (bit flips) have occurred in the received data in the segment, but can be relatively confident that no errors have occurred.
