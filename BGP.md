Routing protocols like RIP, OSPF, and EIGRP work well within a single organization or Autonomous System (AS). However, the Internet consists of thousands of different Autonomous Systems owned by ISPs, cloud providers, universities, and enterprises. A routing protocol is needed to exchange routing information between these Autonomous Systems. BGP (Border Gateway Protocol) is an Exterior Gateway Protocol (EGP) that performs this function. Instead of choosing routes based on hop count or bandwidth, BGP selects the best path using routing policies and path attributes, the most important being the AS Path.



It is a Path Vector protocol that selects routes based on routing policies and path attributes rather than simple metrics like hop count or bandwidth. One of its most important attributes is the AS Path, which helps select the best route and prevents routing loops. BGP operates over TCP port 179 to ensure reliable communication and supports both External BGP (eBGP) between different Autonomous Systems and Internal BGP (iBGP) within the same Autonomous System. Because of its scalability and policy-based routing capabilities, BGP is the routing protocol that powers the Internet.



**# Autonomous System :**

* A collection of networks under a single administrative control that follows a common routing policy.
* Examples: Airtel, Jio, Google, Microsoft, Amazon AWS
* Each has its own: AS Number



**# Why do we need BGP if OSPF already exists?**

OSPF works only within a single Autonomous System. BGP is designed to exchange routing information between different Autonomous Systems across the Internet.



**# What is an Autonomous System?**

An Autonomous System is a group of IP networks managed by a single organization under one routing policy. Each AS has a unique Autonomous System Number (ASN).



**# What is the difference between iBGP and eBGP?**

iBGP			eBGP

Same AS			Different AS

Internal route sharing	Internet/ISP route exchange



**# Which port does BGP use?**

TCP Port 179.



**# Why does BGP use TCP while OSPF doesn't?**

Because BGP exchanges critical Internet routing information and requires reliable delivery. TCP provides acknowledgements, sequencing, retransmissions, and error recovery. OSPF implements its own reliable flooding mechanism directly over IP and therefore does not require TCP.



**# What metric does BGP use?**

BGP uses path attributes such as AS Path, Local Preference, MED, Next Hop, Origin, and others to select the best route.



**# Why is BGP called a Path Vector protocol?**

Because it advertises the complete AS Path to a destination, allowing routers to make policy-based decisions and prevent routing loops.



**# What is AS Path?**

AS Path is the list of Autonomous Systems that a route has traversed. BGP generally prefers the route with the shorter AS Path.

