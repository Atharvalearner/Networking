***# Subnetting Techniques:***

1. FLSM
2. VLSM



***# Interview Explanation:***

* FLSM and VLSM are two subnetting techniques used to divide a larger network into smaller subnets.
* The main purpose of subnetting is to reduce broadcast domains, improve security and network management, and utilize IP addresses more efficiently.



* In FLSM (Fixed Length Subnet Mask): every subnet uses the same subnet mask, so all subnets are equal in size. For example, if I divide a /24 network into four subnets, all four subnets might use a /26 mask, giving each subnet the same number of host addresses. *FLSM is simple to design and manage, but it often wastes IP addresses because every subnet receives the same number of addresses, even if different departments have different requirements.*



* VLSM (Variable Length Subnet Mask): solves this problem by allowing different subnet masks for different subnets. Larger departments can receive larger subnets, while smaller departments receive smaller ones. This *minimizes IP address wastage, improves scalability, and makes much more efficient use of the available address space.*



* Modern networks generally use VLSM because it is flexible and is supported by classless routing protocols such as OSPF, EIGRP, RIPv2, IS-IS, and BGP.



***# FLSM Example:***

Suppose you have: 192.168.10.0/24

Need: 4 departments



Using FLSM: /24 >> /26 >> Four equal subnets

Results:

| Subnet  | Network Address   | Hosts |

| ------- | ----------------- | ----: |

| HR      | 192.168.10.0/26   |    62 |

| Finance | 192.168.10.64/26  |    62 |

| IT      | 192.168.10.128/26 |    62 |

| Sales   | 192.168.10.192/26 |    62 |



Notice that:

Every subnet has: /26

Every subnet has: 62 usable hosts Everything is equal.



***# VLSM Example:***

Same Problem Solve Using VLSM by:

| Department | Needed | Allocated by Subnet Mask |

| ---------- | -----: | ------------------------ |

| IT         |    100 |       126 by /25 	 |

| Finance    |     40 |        62 by /26 	 |

| HR         |     20 |        30 by /27 	 |

| Sales      |     10 |        14 by /28 	 |



Much less waste than FLSM Subnetting Allocations.



Notice:

Subnet sizes are different.

That is why it is called: Variable Length Subnet Mast





***# Why doesn't RIPv1 support VLSM?***

Because RIPv1 is a classful routing protocol.

It does not include subnet mask information in routing updates, so routers assume the default classful mask (Class A, B, or C) based on IP address (eg. 80.30.10.3 is from Class A, 153.8.30.4 is from Class B).

Without mask information, routers cannot distinguish subnets of different sizes.





***# Very Short and Simple Answer:***

FLSM uses a fixed subnet mask for all subnets, so every subnet is the same size. VLSM uses different subnet masks, allowing subnets of different sizes based on actual host requirements. FLSM is simple but wastes IP addresses, whereas VLSM is more efficient, scalable, and widely used in modern networks.





| Feature         | FLSM                     | VLSM                        |

| --------------- | ------------------------ | --------------------------- |

| Full Form       | Fixed Length Subnet Mask | Variable Length Subnet Mask |

| Subnet Size     | Same                     | Different                   |

| Subnet Mask     | Same                     | Different                   |

| IP Utilization  | Poor                     | Excellent                   |

| Wastage         | High                     | Low                         |

| Flexibility     | Low                      | High                        |

| Scalability     | Poor                     | Good                        |

| Modern Networks | Rare                     | Standard                    |

