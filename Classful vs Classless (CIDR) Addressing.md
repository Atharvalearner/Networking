Initially, IPv4 used Classful Addressing, where IP addresses were divided into fixed classes such as Class A, Class B, and Class C. Each class had a predefined default subnet mask—for example, Class A used /8, Class B used /16, and Class C used /24. Routers assumed these default masks, and early routing protocols like RIPv1 did not include subnet mask information in routing updates.



The problem with classful addressing was that it was inefficient. Organizations often received much larger address blocks than they actually needed, leading to significant IP address wastage. It also could not support variable-length subnetting because routing updates did not carry subnet mask information.



To solve these limitations, Classless Addressing, also known as CIDR (Classless Inter-Domain Routing), was introduced. CIDR removes the concept of fixed address classes and represents networks using a prefix length, such as /20, /22, or /27. The subnet mask or prefix length is carried along with the network information, allowing routers to correctly interpret networks of different sizes.



CIDR enables efficient IP address allocation, supports VLSM, allows route summarization, and significantly reduces the size of routing tables. Today, modern routing protocols such as OSPF, EIGRP, IS-IS, RIPv2, and BGP all use classless addressing.



**| ---------------------------------------------- | ------------------------------------------------------------------- |**

**| Classful Addressing                            | Classless Addressing (CIDR)                                         |**

**| ---------------------------------------------- | ------------------------------------------------------------------- |**

| Uses fixed classes (A, B, C)                   | No fixed classes                                                    |

| Uses default subnet masks                      | Uses variable prefix lengths                                        |

| Less efficient IP allocation                   | Efficient IP allocation                                             |

| It supports FLSM                          	 | Supports VLSM                                                       |

| Limited route summarization                    | Supports route summarization (aggregation)                          |

| Used by older classful protocols (e.g., RIPv1) | Used by modern classless protocols (OSPF, EIGRP, RIPv2, IS-IS, BGP) |

| ---------------------------------------------- | ------------------------------------------------------------------- |



***# Why was CIDR introduced?***

CIDR was introduced to overcome the limitations of classful addressing. Classful addressing wasted IP addresses because organizations had to use fixed-size address blocks. CIDR allows networks to be allocated according to actual requirements, supports VLSM, enables route summarization, and helps conserve IPv4 address space.





***# What problems did Classful Addressing have?***

* Fixed network sizes (/8, /16, /24).
* Significant IP address wastage.
* No support for VLSM.
* Routing updates did not carry subnet mask information (in classful protocols like RIPv1).
* Larger routing tables due to less efficient aggregation.

