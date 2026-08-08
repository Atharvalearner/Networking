IS-IS (Intermediate System to Intermediate System) is a Link-State Interior Gateway Protocol used to exchange routing information within a single Autonomous System. It uses Dijkstra's Shortest Path First algorithm and calculates routes based on cost. Similar to OSPF, routers exchange topology information, build a Link-State Database, and independently compute the best path. IS-IS organizes networks into Level 1 and Level 2 instead of OSPF Areas, with Level 2 acting as the backbone. Due to its excellent scalability and stability, IS-IS is commonly used by Internet Service Providers and large service provider networks.



**# Why do we need IS-IS?**

Suppose an ISP has: 20,000 Routers

Running OSPF on such a huge network can become complex because of: Many areas, Large LSDBs, More LSA processing

IS-IS was designed to scale efficiently for very large networks.



**# Why is it called IS-IS?**

Originally, IS-IS was developed for the OSI protocol suite, where:

Intermediate System (IS) = Router

End System (ES) = Host (PC, Server)

Even though it was originally built for OSI networking, today it is widely used for IP routing.



**# Working:**

* Each router:

&#x09;Discovers neighbors.

&#x09;Exchanges Link-State Packets (LSPs).

&#x09;Builds the Link-State Database (LSDB).

&#x09;Runs Dijkstra's SPF algorithm.

&#x09;Builds the routing table.

* This is very similar to OSPF.





**# Advantages:**

Very scalable.

Fast convergence.

Efficient in ISP networks.

Supports IPv4 and IPv6.

Simple hierarchy.

Less affected by IP addressing changes because IS-IS runs directly over Layer 2.



**# Disadvantages:**

More difficult to learn.

Less common in enterprise LANs.

Fewer engineers have hands-on experience.



| Feature     | OSPF           | IS-IS                             |

| ----------- | -------------- | --------------------------------- |

| Type        | Link State     | Link State                        |

| Algorithm   | Dijkstra       | Dijkstra                          |

| Hierarchy   | Areas          | Levels                            |

| Backbone    | Area 0         | Level 2                           |

| Transport   | IP Protocol 89 | Runs directly over Layer 2 (CLNS) |

| Scalability | High           | Very High                         |

| Common Use  | Enterprise     | ISPs \& Service Providers          |



**# What is the difference between OSPF Areas and IS-IS Levels?**

OSPF divides the network into Areas with Area 0 as the backbone, while IS-IS uses Level 1 for intra-area routing and Level 2 as the backbone connecting different areas.



**# Where is IS-IS commonly used?**

IS-IS is widely used by Internet Service Providers (ISPs), telecom operators, and large service provider networks because of its scalability and stability.



**# Why do many ISPs prefer IS-IS over OSPF?**

IS-IS scales very well in large networks, has a simpler hierarchy, runs independently of IP, and is highly stable in service provider environments.



**# Does IS-IS support IPv6?**

Yes. IS-IS supports both IPv4 and IPv6.

