An Access Control List (ACL) is a set of ordered filtering rules configured on a router or Layer 3 switch to permit or deny network traffic. ACLs are used to improve security, restrict access to network resources, and control traffic flow. The router evaluates ACL entries from top to bottom, and the first matching rule is applied. If no rule matches, an implicit deny any blocks the packet. There are two main types of ACLs: Standard ACLs, which filter only by source IP address, and Extended ACLs, which can filter by source and destination IP addresses, protocols, and port numbers. Standard ACLs are generally placed near the destination, while Extended ACLs are placed near the source to stop unwanted traffic as early as possible.





| Standard ACL                    | Extended ACL                           |

| ------------------------------- | -------------------------------------- |

| Source IP only                  | Source + Destination + Protocol + Port |

| Simpler                         | More flexible                          |

| ACL Number: 1–99, 1300–1999     | ACL Number: 100–199, 2000–2699         |

| Usually placed near destination | Usually placed near source             |





**# Where are ACLs Applied?**

ACLs are applied: On router interfaces or On Layer 3 switches

Direction: Inbound, Outbound



**# What is the difference between Standard and Extended ACL?**

Standard ACL filters only on the source IP address, while Extended ACL can filter based on source and destination IP addresses, protocols, and port numbers.

