A switch learns MAC addresses dynamically from the source MAC address of incoming Ethernet frames. It stores the source MAC and incoming port in its MAC or CAM table. It then checks the destination MAC address: if the destination is known, it forwards the frame only to the associated port; if unknown, it floods the frame within the same VLAN. Dynamic MAC entries age out after inactivity and are relearned when new traffic arrives.





***# The four major switching actions:***

A Layer 2 switch mainly performs these actions:

|--------------------------------------------------------------------|

| Action     | Meaning                                       	     |

| ---------- | --------------------------------------------- --------|

| Learning   | Learn source MAC and incoming port from Incoming frame|

| Forwarding | Send known unicast to correct port            	     |

| Flooding   | Send unknown unicast/broadcast where required 	     |

| Filtering  | Do not forward where unnecessary              	     |

|--------------------------------------------------------------------|



***# complete switch algorithm***

When a frame arrives:



&#x20;              FRAME ARRIVES

&#x20;                    │

&#x20;                    ▼

&#x20;      Read Source MAC Address

&#x20;                    │

&#x20;                    ▼

&#x20;    Learn Source MAC → Incoming Port

&#x20;                    │

&#x20;                    ▼

&#x20;    Read Destination MAC Address

&#x20;                    │

&#x20;         ┌────────────────┐

&#x20;         │          │          │

&#x20;       Known      Unknown   Broadcast

&#x20;         │          │          │

&#x20;         ▼          ▼          ▼

&#x20;      Forward      Flood      Flood

&#x20;      correct      within     within

&#x20;       port        VLAN       VLAN





***# How does a switch learn MAC addresses?***

A switch learns the source MAC address of each incoming Ethernet frame and associates it with the port on which the frame arrived.



***# Does a switch learn from the source or destination MAC?***

It learns from the source MAC and uses the destination MAC for forwarding decisions.



***# What happens if the destination MAC is unknown?***

The switch performs unknown unicast flooding, sending the frame out other ports in the same VLAN except the incoming port.



***# What is known unicast forwarding?***

When the destination MAC exists in the MAC table, the switch forwards the frame only through the associated port.



***# What is MAC table aging?***

Dynamically learned MAC entries are removed after a period of inactivity so stale location information does not remain forever.



***# What happens if a device moves to another switch port?***

When the switch receives a frame from that source MAC on the new port, it updates or relearns the MAC-to-port mapping.



***# What is the difference between an ARP table and a MAC table?***

An ARP table maps IP addresses to MAC addresses, while a switch MAC table maps MAC addresses to switch ports.



***# Does a switch send every frame to every port?***

No. It floods broadcasts and unknown unicasts within the VLAN, but known unicast frames are normally sent only to the correct destination port.



***# Does a switch change the source and destination MAC addresses?***

A normal Layer 2 switch does not replace them while forwarding within the same Layer 2 domain. A router creates new Layer 2 framing when forwarding between networks.



***# What happens to the MAC table after a switch restart?***

Dynamically learned entries are normally lost, and the switch relearns them as traffic arrives.



***# Why doesn't the switch learn from the destination MAC?***

Because the destination field only says where the sender wants the frame to go. The source MAC on an incoming port proves where the source device is reachable.

