# Handout 3
1) Under what conditions are packet delays and losses are likely to occur?
  * When the arrvial rate of packets are faster than the link's transfer rate, this can cause delays
  * Losses occur when the packet buffer of the link gets filled up, therefore packets can no longer be received, resulting in packet lost
2) Assume circuit switched network, Time div multi. Speed of link 1,000 bps, size of a frame is 1 second. 10 users, share fairly. How long to transmit a 100,000,000,000 bit file?
  * Each user gets 1,000 bpx / 10 users = 100bps, max speed div by # of users
  * 100,000,000,000 / 100 bps = 1,000,000,000,000 seconds
3) Network with 100 users, shared link is 1,000,000. 5% active, when active transmits at rate of 1,000 bps
* a) 1,000,000 / 1,000 = 1,000 at a time
* b) ASK PROFESSOR ABOUT THIS
  * Have to do complex binomial probabilty formula
  * ![image](https://github.com/Bizarrespace/CPSC471/assets/78052960/c95fb796-419f-4f90-960d-55baea4e96cd)
4) Explain structure of the contemporary internet. Explain roles of the residential access nets, regional ISPs, tier-1 ISPS, IXPS, peering links, and content provider networks.
* The contemporary internet is made up of a network of networks
  * Residential access net: Networks that connect individual households to the internet. Wired (DSL, cable) or wireless( WIFI or 4G/5G)
  * Regional ISPs: Internet service providers that operate in specific regions. Connect access networks to the larger structure of the internet
  * Tier-1 ISPs: Large, connected networks with national or international coverage. The backbone of the internet
  * IXPs: Internet exchange points, physical infrastructure through which different networks exchange Internet traffic. Allows data to be routed efficiently between ISPs, reduces cost, and increases the speed of data transmission.
  * Peering links: Connections between ISPs, allowing them to directly exchange traffic. Reduces distance data has to travel, improving speed and reducing costs.
  * Content provider networks: Networks run by companies that provide internet content(like Google or facebook). Often bypass other ISPs to bring their services closer to the end user.
