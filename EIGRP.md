EIGRP, or Enhanced Interior Gateway Routing Protocol, is an Advanced Distance Vector Interior Gateway Protocol developed by Cisco. It uses the DUAL algorithm to calculate loop-free paths and provides very fast convergence. Unlike RIP, which uses hop count, EIGRP uses a composite metric based primarily on bandwidth and delay. It supports VLSM, CIDR, authentication, incremental updates, equal-cost and unequal-cost load balancing, and maintains backup routes called Feasible Successors for immediate failover. Because of its efficiency and fast convergence, EIGRP has been widely used in Cisco enterprise networks.





**EIGRP:**

EIGRP is an Advanced Distance Vector (Hybrid) Interior Gateway Protocol developed by Cisco. It uses the DUAL algorithm to calculate the best path and provides fast convergence with loop-free routing.



**# Why is it called Hybrid?**

It combines features of both Distance Vector and Link-State protocols.



***I) Like Distance Vector:***

Learns routes from neighbors.

Maintains neighbor relationships.



***II) Like Link-State:***

Fast convergence.

Incremental updates.

Backup routes.

Efficient routing calculations.



**# EIGRP Metric:**

Bandwidth, Delay, Reliability, Load, MTU 

By default, only bandwidth and delay are used.





**# DUAL (Diffusing Update Algorithm):**

Purpose:

* Finds the best path.
* Prevents routing loops.
* Provides fast convergence.
* Maintains backup routes.



**# Advantages:**

Very fast convergence.

Loop-free.

Backup routes.

Incremental updates.

Low bandwidth usage.

Unequal-cost load balancing.

Supports VLSM and CIDR.



**# Disadvantages:**

Historically Cisco proprietary (today it's documented, but OSPF remains more universally supported across vendors).

Less common in multi-vendor environments.





**# Configuration**

Router(config)# router eigrp 100

Router(config-router)# network  192.168.1.0  0.0.0.255

Router(config-router)# network  10.0.0.0   0.0.0.255



**# Successor:** The best loop-free route to a destination.

**# Feasible Successor:** A loop-free backup route that can immediately replace the primary route if it fails.



**# Which table stores Feasible Successors?**

The EIGRP Topology Table.



**# What is the difference between Feasible Distance and Reported Distance?**

Feasible Distance (FD) is the total metric from the local router to the destination. Reported Distance (RD), also called Advertised Distance, is the metric reported by a neighboring router to reach the destination.

