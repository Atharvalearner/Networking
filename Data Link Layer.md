The Data Link Layer provides reliable node-to-node communication within the same network. It performs framing, adds source and destination MAC addresses, detects transmission errors using FCS/CRC, controls access to the physical medium, and delivers frames across the local network. It has two sublayers: the LLC sublayer, which interfaces with the Network Layer and identifies the Layer 3 protocol, and the MAC sublayer, which handles MAC addressing, media access, and frame transmission.





**# Purpose:**

* The Data Link Layer (Layer 2 of the OSI model) is responsible for reliable node-to-node communication over a physical link. 
* It takes packets from the Network Layer, encapsulates them into frames, adds source and destination MAC addresses, detects transmission errors using FCS (CRC), controls access to the transmission medium, and delivers frames to the correct device within the same LAN.





1. **LLC (Logical Link Control):**
* Upper part of Layer 2.
* Responsibilities

&#x09;Identifies the Layer 3 protocol.

&#x09;Provides an interface between Layer 2 and Layer 3.

&#x09;Multiplexes multiple Network Layer protocols.



* Suppose the frame contains the protocol amongs: IPv4, IPv6, ARP
* The LLC helps identify which Network Layer protocol should receive the payload.



**2. MAC (Media Access Control):**

* responsible for physical addressing, controlling access to the transmission medium, and sending and receiving Ethernet frames.
* Lower part of Layer 2.
* Responsibilities:

&#x09;MAC addressing.

&#x09;Media access.

&#x09;Frame transmission.

&#x09;Frame reception.

* Adds: Destination MAC, Source MAC



| LLC                         | MAC                             |

| --------------------------- | ------------------------------- |

| Upper Layer 2               | Lower Layer 2                   |

| Interface to Layer 3        | Interface to Physical Layer     |

| Identifies Layer 3 protocol | Uses MAC addresses              |

| Protocol identification     | Media access and frame delivery |



