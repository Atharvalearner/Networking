Access Switch → Usually many Ethernet access ports

For example: 24-port switch, 48-port switch



***# Simplify for quick revision:***

SWITCH

&#x20;  │

&#x20;  ├── Outside

&#x20;  │     ├── Many Ethernet ports

&#x20;  │     ├── High-speed uplinks

&#x20;  │     ├── SFP/Fiber

&#x20;  │     ├── Console/MGMT

&#x20;  │     └── PoE

&#x20;  │

&#x20;  ├── Inside

&#x20;  │     ├── CPU

&#x20;  │     ├── RAM/Flash

&#x20;  │     ├── ASIC

&#x20;  │     ├── CAM/TCAM

&#x20;  │     └── Buffers

&#x20;  │

&#x20;  └── Logic

&#x20;        ├── MAC table

&#x20;        ├── VLANs

&#x20;        ├── STP

&#x20;        ├── Trunks

&#x20;        ├── EtherChannel

&#x20;        └── Port security





***1. Switch Access Ports:***

These connect end devices: PC, Printer, IP Phone, Camera, Access Point, Server



***2. Switch Uplink Ports***

A switch may have higher-speed uplink interfaces.

Many users generate combined traffic: So, The uplink carries aggregated traffic from many access ports.



PC 1 ──┐

PC 2 ──┤

PC 3 ──┤

...    ├── Access Switch

PC 48 ─┘ │

&#x20;         │ High-speed uplink

&#x20;         ▼

&#x20;    Distribution Switch



***3. SFP/SFP+ Ports:*** 

Just like routers, switches can contain: SFP, SFP+, SFP28, QSFP

Common uses:

* Switch-to-switch connection
* Access-to-distribution uplink
* Fiber backbone
* Long-distance building connection



***4. PoE Ports***

Many switches support: Power over Ethernet

The Ethernet cable carries: Data + Electrical Power



***5. Console, Management, and USB Ports***

Console → Initial/local management

MGMT    → Separate management network

USB     → Files/software/configuration





**# What Is Inside a Switch?**

A switch may contain:

* CPU
* RAM
* Flash
* Switching ASICs
* CAM/forwarding memory
* Packet buffers
* Power supplies
* Fans



***# ASIC (Application-Specific Integrated Circuit):***

It is most important special component.

It is hardware designed for specific high-speed tasks: MAC lookup, VLAN processing, ACL lookup, QoS processing, Packet forwarding

CPU frame processing power is Lower, to overcome this ASIC a special hardware used to do high speed tasks.



**# Switch may provide features:**

VLANs

Access Ports

Trunk Ports

STP/RSTP/MST

EtherChannel

LACP

Port Security

QoS

PoE

DHCP Snooping

Dynamic ARP Inspection

802.1X

Port Mirroring

SNMP

Telemetry





