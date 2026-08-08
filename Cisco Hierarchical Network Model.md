It is a network design model that divides an enterprise network into Access, Distribution, and Core layers to improve scalability, manageability, performance, and redundancy.



***Access Layer connects devices, Distribution Layer controls traffic, and Core Layer transports traffic quickly.***



&#x20;            CORE LAYER

&#x20;                │

&#x20;       ┌────--──┴--──────┐

&#x20;       │                 │

&#x20;  DISTRIBUTION       DISTRIBUTION

&#x20;     LAYER               LAYER

&#x20;       │                 │

&#x20;   ┌-──┴-──┐         ┌-──┴-──┐

&#x20;   │       │         │       │

&#x20; ACCESS  ACCESS    ACCESS  ACCESS

&#x20;  LAYER   LAYER     LAYER   LAYER

&#x20;   │       │         │       │

&#x20;  PCs    Phones    Printer  Servers



**|---------------------------------------------------|**

**| Layer        | Main Job                           |**

**| ------------ | ---------------------------------- |**

| Access       | Connect end devices                |

| Distribution | Control, route, and apply policies |

| Core         | Fast and reliable transport        |

|---------------------------------------------------|



***# Access Layer(Contains Switch):***



&#x20;            Distribution

&#x20;                 │

&#x20;           ACCESS SWITCH

&#x20;         ┌---─────┼──────┐

&#x20;         │        │      │

&#x20;        PC     Phone   Printer



* Main Work: Provide network access to devices.
* It connects: PCs, Laptops, Printers, IP phones, Cameras, Wireless Access Points, Servers in some designs
* The Access Layer answers: Who is connecting to the network?
* It connects end devices to the network and commonly handles VLAN assignment, edge security, PortFast, BPDU Guard, PoE, and user access control.



***# Distribution Layer:***



&#x20;            Distribution Switch

&#x20;            /        |        \\

&#x20;           /         |         \\

&#x20;     Access-SW1  Access-SW2  Access-SW3



* It aggregates multiple access switches and applies Layer 3 routing, security, and network policies.
* This Layer answers: What traffic is allowed, and where should it go?
* It aggregates access switches and commonly performs routing, inter-VLAN routing, ACL enforcement, policy control, and route summarization.



***# Core Layer:***



&#x20;                 CORE

&#x20;             ┌────┴───---┐

&#x20;             │           │

&#x20;      Distribution 1  Distribution 2



Its main job: Transport large amounts of traffic quickly and reliably between different parts of the network.

The Core Layer answers: How can traffic move across the network as quickly and reliably as possible?

The Core should focus on: High speed, Low latency, High availability, Redundancy, Fast convergence, Reliability





***# Basic Simple Terminology:***

Access: Connect

Distribution: Control

Core: Transport



***# Complete packet journey:***

Suppose the company has two buildings.



BUILDING A                              BUILDING B

PC A                                      Server

&#x20;│                                          │

Access SW                                Access SW

&#x20;│                                          │

Distribution A                          Distribution B

&#x20;       \\                                  /

&#x20;        \\                                /

&#x20;         └---─────────CORE ────---──────┘





***# Does every packet pass through all three layers?***

No. Traffic may remain within an access switch or distribution block depending on the source, destination, and network design.



***# Why is redundancy important in the hierarchical model?***

It removes single points of failure and allows traffic to use alternate paths when a device or link fails.

