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

* Receiver operation in Selective Repeat
  * Why does receiver have to ack packets w/ sequence numbers that are less than(left of) those in its window, which starts at rcv_base
  * ![image](https://github.com/Bizarrespace/CPSC471-Computer-Communications/assets/78052960/3ccc883b-8760-4c45-8a93-17604921368b)
  * B/C sender may not have received an ACK for that packet yet
 
* TCP segment format:
  * Based on the given function of a field in TCP, select the name of that field
    * Source port #:
      * Port # associated with the sending socket for this TCP segment
    * Data(or payload):
      * App data that was written into a socket by the sender of this TCP segment
    * Sequence #:
      * Index in the sender-to-receiver byte stream of the first byte of that data in the payload carried in this segment
      * Reworded:
        * The position of the first byte of data in the payload of this segment, as it appears in the stream of bytes being sent from the sender to the receiver
    * ACK # field:
      * Index in the byte stream of the next in-order byte expected at the receiver
    * ACK bit:
      * If set, this segment cumulatively ACKs all data bytes up to , but not including, the byte index in the ACK value field of this segment
      * Reworded:
        * When activated, this segment acknowledges receipt of all data bytes up to, but not including, the position of the byte indicated in the acknowledgment (ACK) value field of this segment
      * Essentially meaning that it has received all the data bytes sent so far, up to a certain point
    * Receiver advertised window:
      * Number of available bytes in the TCP receiver’s buffer.
    * Checksum:
      * Internet checksum of the TCP segment and selected fields in the IP datagram header
    * Header length:
      * Number of bytes in the TCP header
     
* TCP sequence numbers and ACKs:
  * Why is it that the receiver sends an ACK that is one larger than the sequence # in the received datagram?
    * B/C send-to-receiver segment carries only one byte of data, and after that segment is received, the next expected byte of data is just the next byte in the data stream
    * A TCP sequence # is the index of the first byte of data in that TCP segment in the connection's overall byte stream
  * Now suppose that the figure below, a TCP sender is sending segs w/ 100 bytes of payload. TCP sender sends five segs with sequence # 100,200,300,400,500. Suppose that seg # 300 is lost. TCP receiver will buffer correctly received but  not-yet-in-order segments for later delivery to the application layer
    * Complete the sentence of what will happen:
      * After getting seg 100, R responds with ACK with value: 200
      * After getting 200, R ACK with value: 300
      * After getting 500, R ACK with value: 300, dup ACK (Because we did not get the next in order byte, rather we jump 100, we also skipped 400 in this example)
      * After receiving retransmitted seg 300, R responds with ACK value: 600
      * TCP receiver does not respond in the ex w/ ACK value: 400
     
* EWMA:
  * EstimatedRTTn = (1- a)*EstimatedRTTn-1 + a*SampleRTTn
  * T/F, with this EWMA algo value of EstimatedRTTn has no dependence on the eariler sample, EstimatedRTTn-1
    * False, if you expand the formula, it shows the explicit dependence of EstimatedRTTn on SampleRTTn-1
   
* Consider TCP Telnet scenario below, What timer-related action does sender take on receipt of ACK 120
* ![image](https://github.com/Bizarrespace/CPSC471-Computer-Communications/assets/78052960/21cff69d-38de-49ca-8319-11b2354a9f85)
  * Cancels any running timers
  * B/c of cumulative nature of TCP, ACK, sender knows that the seg with sequence # 92 was received, even though its ACK was lost
  * Since there are no unACKed segs, there's no need for any running timers
 
* TCP Flow control:
  * T/F, with TCP's flow control, receiver tells sender how much free buffer space it has(sender also limits amount of outstanding unACKed, in-flight dat ato less than this amount), it is not possible for the sender to send more data than receiver has room to buffer
  * T
 
* TCP connection management
  * SYN message:
    * Message from client to server initiating a connection request
  * SYNACK message:
    * Message from server to client ACKing receipt of a SYN message & indicating the willingness to establish a TCP connection
  * FIN message:
    * Message indicating that the sending side is initiating the protocol to terminate a connection
  * FINACK message:
    * Message response to a request to terminate connection, ACKing that server/client is also willing to terminate the connection
  * RESET message:
    * General purpose error message used during connection set up or tear down to let the other side know that an error has occurred, and that the referenced connection should be shut down
   
* TCP Fast Retransmit:
  * If the channel cant reorder messages, triple dup ACK indicates to sender that seg loss has happened
    * Actually, even a single dup ACK would indicate seg loss has happened(assuming channel cannot corrupt or reorder messages
  * If channel can reorder messages, trip ACK can occur even though message is not lost
    * It's possible that a message has just been reordered and has not yet arrived when the three dup ACKs were generated
   
* Flow control vs congestion control:
  * Flow concerned about managing data trans rate btw sender and receiver to prevent the receiver from being overwhelmed
  * Congrestion is focused on managing the overall data traffic within network to prevent network congestion and maintain efficient data trans
 
* Two congested sender:
  * Consider figure below, which shows app-to-app throughput achieved when two senders are competing at shared bottleneck link.
  * Suppose overall arrival rate, lambdain (for each sender) is close to R/2(max data trans through link)
  * The throughput to the app layer(at each receiver), lambdaout is equal to 0.8*lambdain
    * What fraction of the packets transmitted at the sender are retransmissions?
      * .20, R/2 is 1.0, if we are just doing .8 is where the in and out are meeting, than there is .2 left for retransmission
      * The app layer is getting .8 of data sent by the sender, so remaining must be the retrans
     
* Different approaches towards congestion control:
  * Match congestion control approach to how sender detects congestion:
    * Sender infers seg loss from absence of an ACK from the receiver: End-end
    * Bits are set at a congested router in a sender-to-receiver datagram, and bits are in the returned to the sender in a receiver-to sender ACK, to indicate congestion to the sender: Network-assisted
    * Sender measure RTTs and uses current RTT measurement to infer the level of congestion: Delay-based
   
* Network-assisted or end-end congestion control?
  * Network-assisted:
    * Router marks a field in the datagram header at a congested router
    * Router sends an ICMP message to a host telling it to slow down its sending rate
  * end-end:
    * Ransport-layer sender decreases its sending rate in response to a measured increase in the RTT
    * Router drops a packet at a congested router, which causes the transport-layer sender to infer that there is congestion due to the missing ACK for the lost packet
    * Datagram experiences delay at a congested network router, which is then measured by the sender and used to decrease the sending rate
    * Sender decreases its sending rate in response to packet loss detected via its transport-layer ACKing

 




































