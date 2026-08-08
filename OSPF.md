***OSPF (Open Shortest Path First)*** is a Link-State Interior Gateway Protocol widely used in enterprise networks. It was designed to overcome the limitations of RIP, such as slow convergence and the 15-hop limit. OSPF uses Dijkstra's Shortest Path First algorithm to calculate the best route based on link cost, which is primarily derived from bandwidth. Routers exchange Link State Advertisements (LSAs), build a Link State Database (LSDB), and independently compute the shortest path. OSPF supports VLSM, CIDR, authentication, hierarchical design using Areas, and Equal-Cost Multi-Path (ECMP). Because of its fast convergence and scalability, OSPF is one of the most commonly deployed IGPs in enterprise networks.



***OSPF Areas*** are logical divisions of an OSPF network used to improve scalability by reducing the size of the Link State Database (LSDB), minimizing LSA flooding, and reducing CPU utilization. Every OSPF network must have a Backbone Area called Area 0, through which all inter-area communication takes place. Common area types include Standard Area, Stub Area, Totally Stubby Area, NSSA, and Totally NSSA. Stub-based areas reduce routing table size by limiting external route advertisements.



In multi-access networks such as Ethernet, OSPF elects a Designated Router ***(DR)*** and a Backup Designated Router ***(BDR)*** to reduce the number of adjacencies and LSA exchanges. The DR is elected based on the highest OSPF interface priority, and if priorities are equal, the router with the highest Router ID wins. The BDR acts as a standby and immediately takes over if the DR fails. A router with priority 0 cannot become a DR or BDR, and the DR election is non-preemptive.





**# OSPF (Open Shortest Path First):**

It is a Link-State Interior Gateway Protocol that uses Dijkstra's Shortest Path First (SPF) algorithm to calculate the best path based on link cost.



* OSPF says: Here are my links/updates and their status.
* Every router builds the same map of the network.
* OSPF uses: Cost / Bandwidth





**# OSPF Packet Types:**

| Packet | Purpose                     |

| ------ | --------------------------- |

| Hello  | Discover neighbors          |

| DBD    | Exchange database summary   |

| LSR    | Request missing information |

| LSU    | Send requested information  |

| LSAck  | Acknowledge LSAs            |





**# What is LSDB?**

The Link State Database stores the complete topology information of an OSPF area. Every router in the same area has an identical LSDB.



**# What is the difference between LSDB and Routing Table?**

LSDB contains the complete network topology, whereas the routing table contains only the best routes selected after running the SPF algorithm.



**# OSPF Area:**

A logical grouping of routers that share the same Link State Database (LSDB).



**# Why do we divide OSPF into Areas?**

To reduce LSDB size, minimize LSA flooding, reduce CPU usage, and improve scalability.



**# Why is Area 0 mandatory?**

Because it is the Backbone Area through which all inter-area traffic is exchanged.



**# What is an ABR (Autonomous Border Router)?**

A router connecting two or more OSPF areas.



**# What is an ASBR (Autonomous System Border Router)?**

A router that redistributes routes from another routing protocol into OSPF.



**# Why do we need DR and BDR?**

To reduce the number of OSPF adjacencies and minimize LSA flooding on multi-access networks.



**# How is DR elected?**

Highest OSPF interface priority wins. If priorities are equal, the router with the highest Router ID becomes the DR.



**# What happens if the DR fails?**

The BDR immediately becomes the DR, and a new BDR is elected.

