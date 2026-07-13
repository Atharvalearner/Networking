An access port normally carries traffic for one VLAN and commonly connects an end device such as a PC or printer. The device usually sends and receives untagged Ethernet frames, while the switch associates the port with a configured VLAN. A trunk port carries traffic for multiple VLANs over one physical link, usually using IEEE 802.1Q tags so the receiving device knows which VLAN each frame belongs to. Trunks are commonly used between switches and other VLAN-aware network devices.



***# 802.1Q supports VLAN IDs from 1 to 4094 for normal VLAN identification.***



***Normal Ethernet frame:***

**┌──────────────┬────────────┬──────────┬──────────┐**

**│ Destination  		│ Source MAC 	│ EtherType	   │   Data   	 │**

**│ MAC          		│            	│          	   │             │**

**└──────────────┴────────────┴──────────┴──────────┘**



**On a trunk, a VLAN tag is inserted:**

**┌──────────────┬────────────┬──────────┬──────────┬──────────┐**

**│ Destination  		│ Source MAC 	│ 802.1Q   		│ EtherType	 │   Data   	│**

**│ MAC          		│            	│ VLAN Tag 		│          	 │          	│**

**└──────────────┴────────────┴──────────┴──────────┴──────────┘**





***# access port:***

An access port normally carries traffic for one VLAN and is commonly used to connect an end device.

Ordinary traffic toward the end device is usually untagged because it flows as normal Ethernet frame.

eg. PC sends:

┌─────────────────────┐

│ Ethernet Frame            │

│ No 802.1Q tag normally    │

└─────────────────────┘



***# trunk port:***

A trunk port carries traffic for multiple VLANs over one physical link, commonly using IEEE 802.1Q tagging.

VLAN tag is added to the Ethernet frame, so it will differentiate and pass it to correct VLAN.



eg. Switch sends:

┌──────────────────────┐

│ Ethernet Frame             │

│ 802.1Q Tag: VLAN 10        │

└──────────────────────┘

Same physical cable can able to send traffic to another switch/router/firewall/device via trunk port:

\[VLAN 10 Frame] ─────────────>

\[VLAN 20 Frame] ─────────────>

\[VLAN 30 Frame] ─────────────>



***# Where do we use trunk ports?***

Switch ↔ Switch

Switch ↔ Router

Switch ↔ Firewall

Switch ↔ Wireless Access Point

Switch ↔ Virtualization Host

* But there is an important condition: The connected device must need to handle multiple VLANs.



***# Why do we need trunk ports?***

Without trunking, separate physical links would be required to extend each VLAN between network devices. A trunk carries multiple VLANs over one link.



***# Native VLAN:***

With an 802.1Q trunk, one VLAN can be configured as the native VLAN.

Traffic for the native VLAN is traditionally sent untagged on the trunk.

Example: Native VLAN = 99

The receiving side interprets untagged traffic arriving on that trunk as belonging to the native VLAN.



***# How does the receiving switch know which VLAN a frame belongs to?***

The 802.1Q VLAN tag contains VLAN identification information.



***# Does an access port belong to a VLAN?***

Yes. An access port is normally assigned to one VLAN.



***# Does a trunk merge multiple VLANs?***

No. It carries multiple VLANs while keeping their traffic logically separated.



***# Can devices in VLAN 10 and VLAN 20 communicate because both VLANs cross the same trunk?***

No. Communication between different VLANs requires inter-VLAN routing through a router or Layer 3 switch.



***# What is the native VLAN?***

On an 802.1Q trunk, the native VLAN is traditionally associated with untagged traffic on that trunk.



***# What happens if native VLANs do not match?***

Untagged traffic may be associated with different VLANs on each side, creating connectivity and security problems.



***# What are allowed VLANs?***

They define which VLANs are permitted to cross a particular trunk.

A trunk can be configured to carry only selected allowed VLANs.



***# Can a PC connect to a trunk?***

A VLAN-aware device can, but ordinary end-user PCs are normally connected to access ports.



***# Is every switch-to-switch link automatically a trunk?***

No. The ports must be configured or negotiated appropriately. A switch-to-switch link can also be an access link carrying only one VLAN.



***# Which protocol is commonly used for VLAN tagging?***

IEEE 802.1Q.

