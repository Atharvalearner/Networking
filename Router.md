***# Simplify for quick revision:***

**ROUTER**

&#x20;  │

&#x20;  ├── Outside

&#x20;  │     ├── LAN/WAN Ethernet

&#x20;  │     ├── Fiber/SFP

&#x20;  │     ├── Console

&#x20;  │     ├── MGMT

&#x20;  │     └── USB

&#x20;  │

&#x20;  ├── Inside

&#x20;  │     ├── CPU

&#x20;  │     ├── RAM

&#x20;  │     ├── Flash

&#x20;  │     └── Forwarding hardware

&#x20;  │

&#x20;  └── Logic

&#x20;        ├── Routing table

&#x20;        ├── ARP/Neighbor table

&#x20;        ├── NAT

&#x20;        ├── ACL

&#x20;        ├── VPN

&#x20;        └── Routing protocols



**# What Is Inside the Router?**

A router is essentially a specialized computer.

It contains following components along with their respected feature/work:

* ***CPU:*** Running network operating system, Routing protocols, Management, CLI commands, Control-plane operations
* ***RAM:*** Stores Running configuration, Routing info, ARP/neighbor info, Process info, Packet buffers
* ***Flash Storage:*** stores persistent files such as: OS image, Software packages, Configuration files, Logs, Crash info
* ***Boot firmware:*** Boot firmware initializes routers hardware and loads the network operating system.
* ***Network interfaces:***
* ***Packet-forwarding hardware***



**# Router maintain tables:**

1. ***Routing Table:*** Maps: Destination Network >> Next Hop / Exit Interface
2. ***ARP / Neighbor Table:*** For IPv4: IP Address → MAC Address
For IPv6, Neighbor Discovery serves the corresponding neighbor-resolution role.
3. ***NAT Table:*** Tracks the translation so return traffic can be sent to the correct internal device.
4. ***Connection/Session Table:***
5. ***Forwarding Table:*** Optimized forwarding structures are used for fast packet forwarding.



**# Router Features:**

* Static Routing
* Dynamic Routing
* NAT/PAT
* ACLs
* VPN
* QoS
* DHCP
* IPv4 and IPv6
* Multicast Routing
* High Availability
* Telemetry



***# Router Ports:***

***1. Router Ethernet Interfaces:***

A router commonly has Ethernet ports such as: GigabitEthernet0/0, GigabitEthernet0/1, GigabitEthernet0/2

or newer high-speed interfaces: TenGigabitEthernet, TwentyFiveGigabitEthernet, FortyGigabitEthernet, HundredGigabitEthernet



| Interface | IP Address        | Purpose        |

| --------- | ----------------- | -------------- |

| Gi0/0     | `192.168.1.1/24`  | Internal LAN   |

| Gi0/1     | `203.0.113.10/30` | ISP connection |

| Gi0/2     | `172.16.1.1/24`   | DMZ            |





***2. WAN Interfaces:***

Historically, enterprise routers commonly included dedicated WAN interfaces.

Examples: Serial, T1/E1, DSL, ISDN

You may see names such as: Serial0/0/0, Serial0/0/1

Older enterprise routers commonly used serial interfaces for leased WAN links. Modern deployments more often use Ethernet and fiber-based service-provider connections.



***3. Fiber Interfaces and SFP Slots:***

A router may have: SFP, SFP+, SFP28, QSFP



SFP   → Commonly 1 Gbps class

SFP+  → Commonly 10 Gbps class

SFP28 → Commonly 25 Gbps class

QSFP  → Higher-speed multi-lane connectivity



The slot is the interface socket; the transceiver determines the physical media and supported optical/electrical characteristics.



***4. Console Port:***



Laptop

&#x20;  │ Console Cable

&#x20;  ▼

Router Console Port



A router usually has a management console port.

The console connection is used for: Initial configuration, Password recovery, Troubleshooting, Configuration when network access is unavailable.



***5. AUX/Auxiliary Port:***

Some routers, especially older enterprise models, may have an: AUX port.

Historically it was often used for remote out-of-band management through a modem.

Today, dedicated management Ethernet interfaces are more common.



***6. Dedicated Management Port:***

Modern enterprise devices may have a dedicated port such as: MGMT, Management Ethernet

Example:

Production Network		Separate Management Network

&#x20;       │									|

&#x20;       ▼				    ▼

Router Data Ports			 MGMT Port



Suppose the production network fails, Then administrator may still access: Separate Management Network >> MGMT Port >> Router

This is called: ***Out-of-band management***



***7. USB Port:***

Routers may contain USB ports.

Uses can include: Copying configuration files, Loading software images, Saving logs, Backup and recovery, External storage





**# The router may support:**

OSPF, BGP, IS-IS, RIP, EIGRP on supported ecosystems

