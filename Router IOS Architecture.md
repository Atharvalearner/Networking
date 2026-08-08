Cisco IOS is the operating system that runs on Cisco routers and switches. It manages hardware resources, provides the CLI, supports routing protocols such as OSPF, EIGRP, and BGP, implements features like ACLs, NAT, and QoS, and forwards packets between networks. Internally, Cisco IOS is organized into four logical planes. The Management Plane provides configuration and monitoring through CLI, SSH, SNMP, and APIs. The Control Plane learns network topology, runs routing protocols, builds the routing table, and determines the best path for traffic. The Data Plane uses this information to perform fast packet forwarding by applying the forwarding table, ACLs, NAT, and QoS. Underneath these planes are the hardware resources, including the CPU, RAM, Flash, interfaces, and ASICs.



During boot, the router performs POST, executes the bootstrap program from ROM, loads the IOS image from Flash into DRAM, reads the startup configuration from NVRAM into RAM as the running configuration, initializes interfaces and routing protocols, and finally becomes operational. When a packet arrives, the router removes the Layer 2 header, performs a longest-prefix-match lookup on the destination IP, decrements the TTL, updates the IP header checksum, applies configured policies such as ACLs or NAT, resolves the next-hop MAC address if necessary, encapsulates the packet into a new Layer 2 frame, and forwards it through the appropriate outgoing interface.





**# Cisco IOS:**

It is a network operating system that manages router hardware, configuration, routing protocols, security features, and packet forwarding.



**# Control and Data plane:**

control plane learns routes and builds forwarding knowledge

data plane uses that information to forward packets.



***# ROMMON:***

* ROM Monitor is a low-level recovery and diagnostic environment
* used when normal booting fails or when manual recovery is required.



**# Simple Internal View of router:**

┌───────────────────────────────────-------┐

│            MANAGEMENT PLANE              │

│ CLI │ SSH │ SNMP │ NETCONF/RESTCONF      │

├───────────────────────────────────-------|

│              CONTROL PLANE               │

│ OSPF │ BGP │ STP\* │ ARP │ Routing Table  │

├──────────────────────────────────-------─┤

│                DATA PLANE                │

│ FIB │ Adjacency │ ACL │ QoS │ Forwarding │

├───────────────────────────────────-------┤

│                  HARDWARE                |

│ CPU │ RAM │ Flash │ Interfaces │ ASIC/NPU│

└───────────────────────────────────-------┘



**# Simple to remember:**

Management Plane → Configure the router

Control Plane    → Decide where traffic should go

Data Plane       → Actually forward the traffic



**# IOS Memory Components:**

| Memory | Contains                             | Volatile? |

| ------ | ------------------------------------ | --------- |

| ROM    | POST, bootstrap, recovery software   | No        |

| Flash  | IOS image                            | No        |

| NVRAM  | Startup configuration                | No        |

| DRAM   | Running IOS state and running-config | Yes       |



**# Easy memory:**

ROM   → How to start

Flash → What OS to run

NVRAM → What configuration to load

RAM   → What is running now



1. ***ROM:***
* contains low-level boot components.
* Traditionally:  POST,

&#x09;	   Bootstrap,

&#x09;	   ROMMON,

&#x09;	   Mini/recovery IOS on some platforms



* At startup: Power ON

&#x20;  		│

&#x20;  		▼

&#x09;	ROM

&#x20;  		├── Test hardware

&#x20;  		└── Find and load IOS



***2. Flash:***

* Flash normally stores the IOS software image.
* IOS is stored persistently in Flash but normally executes from RAM after loading.

Flash

&#x20;  │ IOS image

&#x20;  ▼

&#x20; DRAM

&#x20;  │

&#x20;  ▼

IOS executes



***3. NVRAM:***

* NVRAM traditionally stores: startup-config
* This is the configuration loaded during boot.
* Because NVRAM is non-volatile: Power OFF >> Startup-config remains



***4. DRAM/RAM:***

RAM stores active runtime information.

running-config = Current active configuration



Example:

* Running IOS processes
* Running configuration
* Routing table
* ARP table
* Packet buffers
* Process memory



If power is lost before saving: Unsaved configuration >> Lost

That is why: `copy running-config startup-config` is important.



**# Complete Router Boot Flow:**



Power ON

&#x20;  ↓

POST (Power-On Self-Test)

&#x20;  └── Tests basic hardware:

&#x20;      CPU, DRAM, interfaces, and other hardware components

&#x20;  ↓

Bootstrap Program Starts

&#x20;  └── Initializes the boot process and locates the IOS image

&#x20;  ↓

Find IOS Image

&#x20;  ├── Router commonly searches for the IOS image in Flash

&#x20;  │

&#x20;  └── If a valid IOS image cannot be loaded,

&#x20;      the router may enter ROMMON/recovery mode

&#x20;  ↓

Load IOS Image from Flash into DRAM

&#x20;  │

&#x20;  │    Flash                    DRAM

&#x20;  │    IOS image ─────────────► Running IOS

&#x20;  │

&#x20;  └── IOS begins executing and initializes:

&#x20;      • Hardware interfaces and drivers

&#x20;      • System processes

&#x20;      • Memory management

&#x20;      • Routing components

&#x20;      • CLI and management services

&#x20;  ↓

IOS Looks for startup-config

&#x20;  ├── startup-config found in NVRAM?

&#x20;  │

&#x20;  ├── YES → Continue loading configuration

&#x20;  └── NO  → Router may enter the Initial Configuration

&#x20;            Dialog / Setup Mode

&#x20;  ↓

Load and Apply startup-config from NVRAM into DRAM

&#x20;  │

&#x20;  │    NVRAM                   DRAM

&#x20;  │    startup-config ────────► running-config

&#x20;  │

&#x20;  └── IOS applies the saved configuration:

&#x20;      • Hostname, Interface IP addresses, states, Routing protocol configuration, Static routes, ACLs

&#x20;  ↓

IOS Activates Configured Services and Builds Runtime State

&#x20;  ├── Interfaces operate according to configuration

&#x20;  ├── Routing protocol processes operate

&#x20;  ├── Neighbor relationships can form

&#x20;  ├── Routes are learned

&#x20;  ├── Routing and forwarding tables are built

&#x20;  └── Management services become available

&#x20;  ↓

ROUTER BECOMES OPERATIONAL





**# Packet Flow:**

When a packet arrives, the router removes the incoming Layer 2 frame, checks the destination IP using longest prefix match, decreases TTL, applies configured policies, determines the next hop, creates a new Layer 2 frame, and forwards the packet through the outgoing interface.

