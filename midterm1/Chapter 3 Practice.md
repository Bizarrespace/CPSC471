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
   
* Stop-and-wait channel utilization:
  * If packet 10k bits, and channel trans rate is 10Mbps, and round-trip propagation delay is 10ms. What is max channel util of a stop-and-wait protocol for this channel:
    * use this formula
      * η = (1)/(1 + 2a)
        * a is the ratio of propagation delay(Tp) to transmission delay(Tt)
        * Tt = 10Kbits/10Mbps = 10,000 bits / (10,000,000bits / seconds) = .001seconds - 1ms
        * Tp = half of the round-trip prop delay, so 5ms
        * a = Tp/Tt = 5ms/1ms = 5
        * Sub a into formula
        * η = (1) / (1+2*5) = .09, closest answer is .1
       
* Channel util with pipelining
  * If we are using a arbitrarily high level of pipelining, than the sender does not wait for an act in order to send more packets, therefore the Util is going to be 1.0, or as much as the link can transfer
 
* What is true about pipelining?
  * Pipelined sender can have transmitted multiple packets for which the sender has yet to receive an ACK from the receiver
  * With a pipelined sender, may be transmitted packets “in flight” – propagating through channel – that the receiver has not yet received
 
* Packet buffering in Go-Back-N
  * What reasons are there for discarding received-but-out-of-sequence packets at the receiver in GBN
    * Sender will resend that packet in any case
    * The implementation at the receiver is simpler
  * What is the reason for not discarding?
    * Even though it will be retransmitted, the next retrans could be corrupted, so don't discard perfectly well-received packet
   
* Why haven't red packets been delivered yet?
  * ![image](https://github.com/Bizarrespace/CPSC471-Computer-Communications/assets/78052960/9656b147-1b27-474b-9cd4-7cece089c9a0)
  * There is packet with lower sequence # that has yet to be received, so in-order delivery of data in red packets to app not possible yet

# Stopped at 36
 




































