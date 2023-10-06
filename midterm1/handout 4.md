# Handout 4
1) <b>What are nodal, queuing, transmission, processing, and propagation delays?</b>
  * <ins>Nodal delay</ins>: total delay at a node, time taken for processing, queuing, transmission, and propagation
  * <ins>Queuing delay</ins>: time a packet spends in a routing queues of a node waiting for its turn to be processed
  * <ins>Transmission delay</ins>: Time required to push all packet's bits into the link, depened on the packet's length and link's transmission rate
  * <ins>Processing delay</ins>: Time taken to examine packet's header and determine where to direct packet
  * <ins>Propagation delay</ins>: Time takes for bit to travel from sender to receiver, dependent on the distance between the two and progagation speed.
2)  <b>What is the difference between progagation and transmission delays?</b>
  * Propagation is from sender to receiver, so the entire distance traveled, whiel transmission delay is only referring to time it takes to push all packet's bits into the link.
  * Prop depeneds on distnace between sender and receiver, and prop speed.
  * Trans depeneds on packet's length and link's trans rate
3)  <b>Two systems connected by a router. Both systems and router have transmission rates of 1,000 bps. Each link has a propagation delay of 10ms. Takes router 2ms to process the packet(where to send packet to). Suppose first system wants to send a 10,000 bit packet to the second system. How long will it take before receiver system recieves the entire packet?</b>
  * A --> Router --> B
  * 10,000 / 1,000 = 10s to get from A to router
  * 2ms for processing delay
  * 10s from router to B
  * total propagation delay of 20ms (10ms * 2links)
  * So it takes 10s + 10s + 2ms + 20ms = <ins>20.022 seconds</ins> 
4) <b> Two hosts <ins>A</ins> and <ins>B</ins>, connected by link with rate <ins>R</ins>. Two hosts separated by <ins>m</ins> meters progagation speed along link is <ins>s</ins> meters/sec. Host A sends packet of size L bits to host B.</b>
  * a) Express propagation delay, dprop, in terms of m and s: 
    * Distance div by prop speed. Dprop is m/s
  * b) Determine the transmission time of packet, dtrans, in terms of L and R:
    * Trans time is packet size L div by trans rate R, L/R
  * C) Ignoring processing and queuing delays, obtain an express for the end-to-end delay:
    *  dprop + 2dtrans = m/s + 2L/R
  * D) Suppose A begins to transmit the packet at time t = 0. At t = dtrans, where is the last bit of the packet?
    * The last bit of the packet would still be on the link, the reason being that lets say if it takes 10 seconds for the transmission time, that means that it takes 10 seconds to get from A to link, so at 10 seconds, the packet is able to travel that entire distance to that link, therefore the last bit of the packet is <ins>just on the link</ins>, or little bit behind still transferring if we are according for propagation delay.
   * E) Suppose dprop is greater than dtrans. At time t = dtrans, where is the first bit of the packet?\
     * Still on the transfer way from A to router
   * F) Suppose dprop is less than dtrans. At time t = dtrans, where is the first bit of the packet?
     * if dprop is less than dtrans, than at t = dtrans, that means the first bit of the packet is already at B, because dprop is the time it takes to get from A to B
   * G) Suppose s = 2.5*10^8, L = 120 bits, and R = 56kbps. Find the distance m so that dprop equals dtrans
     * Since we want to find when dprop is equal to dtrans we have to set them equal to each other, and then solve for m so then we are able to find out what m is
     * m = (L/R) * s = (120bits/56000bits per second) * 2.5*10^8m/s = <ins>535.71 km</ins>
