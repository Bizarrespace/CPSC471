# Handout 4
1) <b>What are nodal, queuing, transmission, processing, and propagation delays?</b>
  * <u>Nodal delay</u>: total delay at a node, time taken for processing, queuing, transmission, and propagation
  * <u>Queuing delay</u>: time a packet spends in a routing queues of a node waiting for its turn to be processed
  * <u>Transmission delay</u>: Time required to push all packet's bits into the link, depened on the packet's length and link's transmission rate
  * <u>Processing delay</u>: Time taken to examine packet's header and determine where to direct packet
  * <u>Propagation delay</u>: Time takes for bit to travel from sender to receiver, dependent on the distance between the two and progagation speed.
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
  * So it takes 10s + 10s + 2ms + 20ms = <u>20.022 seconds</u>  