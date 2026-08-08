IGRP (Interior Gateway Routing Protocol) is a Cisco proprietary Distance Vector routing protocol designed to improve on RIP by supporting a larger hop count and using a composite metric based on bandwidth, delay, reliability, load, and MTU instead of just hop count. It supports a maximum hop count of 255 and sends routing updates every 90 seconds. However, IGRP is a classful protocol that does not support VLSM or CIDR, converges slowly, and has been declared obsolete. Cisco replaced it with EIGRP, which provides faster convergence, supports classless routing, and uses the DUAL algorithm.





**# Why was IGRP Developed?**

* RIP had several problems:

&#x09;Maximum 15 hops.

&#x09;Slow convergence.

&#x09;Uses only hop count.

&#x09;Not suitable for medium or large networks.

* Cisco introduced IGRP to address these limitations.



**# IGRP:**

IGRP is a Cisco proprietary Distance Vector Interior Gateway Protocol that uses a composite metric(Same as EIGRP) instead of simple hop count.



| Protocol | Maximum Hop Count |

| -------- | ----------------- |

| RIP      |                15 |

| IGRP     | 255 (default 100) |





**# Timers:**

| Timer     | Default |

| --------- | ------- |

| Update    | 90 sec  |

| Invalid   | 270 sec |

| Hold-down | 280 sec |

| Flush     | 630 sec |



**# IGRP vs EIGRP:**

| Feature       | IGRP                                   | EIGRP                                                  |

| ------------- | -------------------------------------- | ------------------------------------------------------ |

| Type          | Distance Vector                        | Advanced Distance Vector                               |

| Algorithm     | Bellman-Ford                           | DUAL                                                   |

| Metric        | Bandwidth + Delay + Reliability + Load | Same composite metric (bandwidth and delay by default) |

| Convergence   | Slow                                   | Very Fast                                              |

| Updates       | Periodic                               | Triggered Incremental                                  |

| Backup Routes | No                                     | Yes (Feasible Successor)                               |

| VLSM          | No                                     | Yes                                                    |

| Status        | Obsolete                               | Still used in Cisco environments                       |



**# If IGRP exists, why was EIGRP Introduced ?**

Because EIGRP provides much faster convergence using the DUAL algorithm, supports classless routing (VLSM/CIDR), sends only incremental updates instead of periodic full updates, maintains loop-free backup routes, and scales much better than IGRP.

