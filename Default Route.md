Default route is a special route, written as 0.0.0.0/0 in IPv4, that a router uses when no more specific route matches the destination IP address. It is called the Gateway of Last Resort because it is used only after all other routing table entries have been checked. On end devices, the equivalent concept is the default gateway, which is the local router's IP address used to reach networks outside the local subnet.





**# Routing:**

Process of selecting the best path and forwarding packets from one network to another using a routing table.





***# Default route is simply a route that says:***

* If you don't know where to send the packet, send it here.

*Known destination?*

&#x20;  *Yes  ▼  No*

*Use specific route*

&#x20;       *▼*

*Otherwise use DEFAULT ROUTE*





***# Why is called "Gateway of Last Resort" ?***

* Because it is used only after every other route has failed to match.

Specific Route

&#x20;     ↓

Found?

&#x20;     ├── Yes → Use it

&#x20;     └── No

&#x20;            ↓

Default Route Exists?

&#x20;            ├── Yes → Use Default Route

&#x20;            └── No

&#x20;                   ↓

&#x20;                Drop Packet





**# The default route is written as:**

***0.0.0.0/0*** or Destination: 0.0.0.0 Mask: 0.0.0.0

The prefix: 0.0.0.0/0 matches every IPv4 address because it has 0 network bits.





***# Static Default Route:***

* A network administrator can configure:

***Syntax:  `ip  route  0.0.0.0  0.0.0.0  DEFAULT\\\_ROUTE\\\_INTERFACE\\\_IP`***



Meaning: Any Unknown Network send to default route interface IP



***# What happens if no default route exists?***

Router checks: Specific Route present? (if No) and Default Route present? (if No) then Usually Drop those packets.



***# What is the difference between a default gateway and a default route?***

* Default Gateway

Configured on end devices (PCs, laptops, phones).

It is the router's IP address on the local network

Used when traffic network are unknown then it sends unknow-network traffic to router's IP/Default Gateway.



* Default Route

Configured or learned on routers.

It specifies where to send traffic for unknown destinations.

Used when traffic network are unknown/not present in routing table of router then it sends unknown-network traffic to Default route interface.





***# Can there be multiple default routes?***

Yes, Routers can have multiple default routes for redundancy or load balancing, depending on metrics/administrative distance and the routing protocol or configuration.

