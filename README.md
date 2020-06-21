# DMVPN-Phase-2-using-RIP-OSPF-and-EIGRP
## DMVPN Phases 
When there is a data exchange between two Spokes, the first spoke contacts the Hub, in order to obtain the information required on the other end, in order to be able to create a dynamic IPsec VPN tunnel directly between them. If the spoke uses a dynamic IP address, it must register with the headquarters router (Hub) while it joins the network every time. Then after passing the confirmation step, both routers can implement direct communication between them. The communication between spokes is done according to one of the three phases of DMVPN.

 1. ### Phase 1: 
Hub to Spoke In this phase, each spoke is configured with the IP address of the hub as the network server. Hence, each spoke has a static tunnel with a fixed destination IP which represents the Hub’s physical address. Consequently, spokes can only get to each other across the hub. The key advantage of DMVPN Phase 1 is the simplified Hub configuration. Additionally, the choice of routing protocol is much easier since almost any dynamic routing protocol would help with attaining reachability. The hub just needs to advertise a default route to spokes, while spokes should advertise their subnets dynamically to the hub. However, the main drawback is inability to establish spoke-to-spoke shortcut tunnels. NHRP Phase 2 resolves this issue and allows for spoke-to-spoke tunnels 

2. ### Phase 2:
 Spoke to Spoke This mode requires all the spokes to have complete routing information with the next-hop preserved. Since not all spokes may accept full load of routing updates, this requirement may limit the scalability especially in large networks. The second phase limitation occurs in case of a network with 1000 spokes for example, where the routing table on each spoke will have too many entries, which essentially isn’t needed. Hence it becomes difficult for the routers to have such a huge routing table. 
 
3. ### Phase 3:
 Spoke to Spoke with Scalable Infrastructure Basically, this phase accomplishes the same things as phase 2, but it improves on some of its limitations. Phase 3 fixed this problem in the most effective way. Because all spokes see the entire network being learned from the hub. The solution is to summarize the network on the hub. Hence DMVPN phase 3 can be used for very large deployments and it is a lot more scalable than DMVPN phase 2 and has a better hierarchy.

# Getting Started 
File consists of the netwrok topology and the configuration for the hub, spoke-1, spoke-2 and spoke-3. It is implemented using GNS3.
