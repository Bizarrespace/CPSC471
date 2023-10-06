# Handout 1
1) What is a network edge?
  * Hosts, end systems that are connected to the internet
  * Ex: Laptops, smartphones, servers
2) What is a network core?
  * interconnected routers that transport data between dif networks that make up the internet
3) What is a protocol?
  * Set of rules that governs communcations between dif devices on a network.
  * Define format and order of messages exchanged
4) Difference between circuit and packet switching?
  * Cir reserves dedicated communcation path between two devices
    * Guaranteed performance, less efficient
  * Packet breaks data into small packets and sends them independently
    * Can take dif paths to get to the same place.
    * More efficient but variable performance
5) What is store and forward architecture? Why is it necessary?
  * Type of packet switching, where the entire packet must arrive at the router before it can be transmitted to next link.
  * Needed to ensure packet is complete and error-free before forwarded
6) How long transmit 1000 bit packet across 20 bps link?
  * 1000 / 20 = 50 seconds
7)  How long to transmit 1000 bit packet from A to B if: A --- 10bps ---> router --- 20 bps --->B
  * A to R = 1000 /10 = 100 seconds
  * R to B = 1000 /20 = 50 seconds
  * So 150 seconds
8) What is the difference between frequency division multiplexing and time division multiplexing? What are the advantages of each?
  * FDM is dividing the available frequency spectrum into narrow frequency bands, each call its own band
    * More dedicated resources but less efficient
  * TDM dividing into time slots, each call allocated periodic slot, can do max rate of frequency band
    * TDM more efficient use of resources, but may vary in performance
    * ![image](https://github.com/Bizarrespace/CPSC471/assets/78052960/b58f01b1-7da0-4ebc-ab69-5db2196c038c)

