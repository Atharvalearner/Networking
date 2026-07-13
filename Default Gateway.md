**Default gateway:**

A gateway provides a path from one network to another. A default gateway is the router or Layer 3 interface a host uses when the destination is outside its local subnet and no more specific route exists. The host uses its subnet mask to determine whether the destination is local or remote. For a remote destination, the IP packet keeps the final destination IP, but the local Ethernet frame is addressed to the MAC address of the next hop, usually the default gateway.



**# Is a gateway always a physical router?**

No. It may be a router interface, a Layer 3 switch virtual interface, a firewall interface, or another Layer 3 system performing the forwarding role.



**# What happens if the gateway is wrong?**

Local subnet communication may still work, but communication with remote networks usually fails.





