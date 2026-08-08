When multiple routers are connected in a network, each router needs to know how to reach remote networks. We can either configure routes manually (Static Routing) or let routers exchange routing information automatically using Routing Protocols. RIP is one of the oldest Interior Gateway Routing Protocols (IGPs). It uses the Distance Vector routing algorithm and selects the best path based on the number of hops. The route with the lowest hop count is preferred, and the maximum hop count allowed is 15. A hop count of 16 is considered unreachable. Routers running RIP exchange their routing tables every 30 seconds with directly connected neighbors. Although RIP is simple to configure, it converges slowly and is suitable for small networks.





**# RIP (Routing Information Protocol):**

It is a Distance Vector Interior Gateway Routing Protocol that uses hop count as its routing metric.





**# Why was RIP developed?**

Imagine three routers: Network A ---- R1 ---- R2 ---- R3 ---- Network B

Without a routing protocol:

* Every router must be configured manually.
* If a new network is added, administrators must update multiple routers.



With RIP:

* Routers automatically exchange routing information.
* New routes are learned automatically.





**# RIP Versions:**

**| RIP Version 1 (RIPv1)	|	RIP Version 2 (RIPv2)	|**

| ----------------------|-------------------------------|

| Classful		|  Classless			|

| No VLSM support	|  Supports VLSM		|

| No CIDR support	|  Supports CIDR		|

| Broadcast updates	|  Uses multicast (224.0.0.9)	|

| No authentication	|  Supports authentication	|





**# Timer:**

| Timer           | Default |

| --------------- | ------- |

| Update Timer    | 30 sec  |

| Invalid Timer   | 180 sec |

| Hold-down Timer | 180 sec |

| Flush Timer     | 240 sec |





**# RIP Configuration (Cisco)**

Router(config)# router rip			.. Enable RIP

Router(config-router)# version 2		.. Use Version 2

Router(config-router)# network 192.168.1.0	.. Advertise a network

Router(config-router)# network 10.0.0.0





**# Verify Commands:**

show ip route			.. Show routing table

show ip protocols		.. Show RIP routes

show ip rip database		.. Show RIP database





**# Why is RIP called a Distance Vector protocol?**

Because it determines the best route based on the distance (hop count) and the direction (next-hop router).



**# Does RIP support load balancing?**

Yes. RIP supports equal-cost load balancing across multiple paths with the same hop count.



**# If one path has 2 hops but a 10 Mbps link, and another has 3 hops but a 1 Gbps link, which one will RIP choose?**

RIP will still choose the 2-hop path because it considers only hop count. It does not evaluate bandwidth, delay, or link quality.



**# What happens if a router stops receiving RIP updates from a neighbor?**

If no update is received within the invalid timer (180 seconds by default), the route is marked invalid. Eventually, after the flush timer (240 seconds), it is removed from the routing table.

