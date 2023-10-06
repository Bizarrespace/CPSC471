# Handout 4
* What are nodal, queuing, transmission, processing, and propagation delays?
  * Nodal delay: total delay at a node, time taken for processing, queuing, transmission, and propagation
  * Queuing delay: time a packet spends in a routing queues of a node waiting for its turn to be processed
  * Transmission delay: Time required to push all packet's bits into the link, depened on the packet's length and link's transmission rate
  * Processing delay: Time taken to examine packet's header anddetermine where to direct packet
  * Propagation delay: Time takes for bit to travel from sender to receiver, dependent on the distance between the two and progagation speed.
* What is the difference between progagation and transmission delays?
  * Propagation is from sender to receiver, so the entire distance traveled, whiel transmission delay is only referring to time it takes to push all packet's bits into the link.
  * Prop depeneds on distnace between sender and receiver, and prop speed.
  * Trans depeneds on packet's length and link's trans rate