**Ethernet :**

* standard technology for connecting devices in a wired Local Area Network (LAN).
* uses physical cables (often twisted-pair copper or fiber optic) to transmit data between devices. 
* operates at the physical and data link layers of the OSI model
* utilizing structured data "frames" to ensure information reaches the correct destination.



**Ethernet IEEE standard - *802.3***

**Wi-Fi IEEE standard    - *802.11***



**T**: Twisted-Pair Copper Cables

**SR**: Short Range

**LR**: Long Range



**BASE (Baseband Transmission): eg. Ethernet**

* The entire cable carries only one signal at a time.
* The cable/channel is used to carry one digital Ethernet communication system rather than dividing the medium into multiple frequency channels for different services.



&#x20;                      ***ETHERNET***

&#x20;                         │

&#x20;         ┌─────────────--┼─────────────┐

&#x20;         │               │             │

&#x20;       ***SPEED           MEDIUM        DUPLEX***

&#x20;         │               │             │

&#x20;  10 Mbps Standard     Copper       Half Duplex

&#x20;  100 Mbps Fast        Fiber        Full Duplex

&#x20;  1 Gbps Gigabit

&#x20;  10 Gbps 10-Gigabit

&#x20;  40/100/400/800 Gbps



|------------------------------------------------------------------------------------------------------------------------------------------------------|

**| Ethernet Type            | Standard/Example   |        Speed | Medium       | Typical Cable         | Typical Distance | Common Use                  |**

| ------------------------ | ------------------ | ------------ | ------------ | --------------------- | ---------------: | --------------------------- |

| Standard Ethernet        | 10 BASE-T          |      10 Mbps | Copper       | Cat3/Cat5             |            100 m | Old LANs                    |

| Fast Ethernet            | 100 BASE-TX        |     100 Mbps | Copper       | Cat5                  |            100 m | Older office LANs           |

| Gigabit Ethernet         | 1000 BASE-T        |       1 Gbps | Copper       | Cat5e/Cat6            |            100 m | Modern PCs and office LANs  |

| Gigabit Fiber            | 1000 BASE-SX       |       1 Gbps | Fiber        | Multimode Fiber       |   Short distance | Switch uplinks              |

| Gigabit Fiber            | 1000 BASE-LX       |       1 Gbps | Fiber        | Single-mode/Multimode |  Longer distance | Building links              |

| 10 Gigabit Ethernet      | 10 GBASE-T         |      10 Gbps | Copper       | Cat6a                 |            100 m | Servers and high-speed LANs |

| 10 Gigabit Fiber         | 10 GBASE-SR        |      10 Gbps | Fiber        | Multimode Fiber       |   Short distance | Data centers                |

| 10 Gigabit Fiber         | 10 GBASE-LR        |      10 Gbps | Fiber        | Single-mode Fiber     |    Long distance | Campus/ISP links            |

| 40 Gigabit Ethernet      | 40 GbE             |      40 Gbps | Mainly Fiber | Fiber/DAC             |          Depends | Data centers                |

| 100 Gigabit Ethernet     | 100 GbE            |     100 Gbps | Mainly Fiber | Fiber/DAC             |          Depends | Core/data centers           |

| 400/800 Gigabit Ethernet | 400 GbE / 800GbE   | 400–800 Gbps | Mainly Fiber | Fiber                 |          Depends | Hyperscale data centers     |

|------------------------------------------------------------------------------------------------------------------------------------------------------|



***Simple to Understand:***

**Type:**       Standard Ethernet 	<    Fast Ethernet   <   Gigbit Ethernet/Fibre  <    10-Gigbit Ethernet/Fibre   <    40/100/400/800 Gigbit Ethernet

**Speed:** 		(10 MB)			(100 MB)	      (1 GB)			(10 GB)				(40/100/400/800 GB)

**Medium:** 	(Copper)	     	(Copper)	      (Copper / Fibre)		(Copper / Fibre)		(Mainly Fibre)

**Cable:**		(cat-3/cat-5)		(cat-5)		      (cat-5e/cat-6/		(cat-6a/Single-mode		(Fibre/DAC)

&#x09;						   single-mode/multi-mode)	  multi-mode fibre)



***# Copper Cables (Typical Distance: 100 Metre)***: cat1, cat2, cat3, cat5, cat5e, cat6, etc

***# Fibre Cables (Typical Diastance: Short/Long/Depends)***<i>:</i>  Single-Mode Fibre, Multi-Mode Fibre, Fibre / DAC



***# Speed Analogy:***

10 Mbps   → Standard Ethernet

100 Mbps  → Fast Ethernet

1 Gbps    → Gigabit Ethernet

10 Gbps   → 10 Gigabit Ethernet



***# Copper Vs Fibre Ethernet:***

***----------------------------------------------------------------------------------***

**| Feature          | Copper Ethernet     | Fiber Ethernet                        |**

| ---------------- | ------------------- | ------------------------------------- |

| Signal           | Electrical          | Light                                 |

| Cable            | Cat5e, Cat6, Cat6a  | Fiber optic                           |

| Connector        | RJ45                | LC/SC with transceiver                |

| Distance         | Usually up to 100 m | Hundreds of meters to many kilometers |

| Cost             | Lower               | Higher                                |

| EMI Interference | Can be affected     | Resistant                             |

| Typical Use      | PC → Switch         | Switch → Switch                       |

| Best For         | End devices         | Backbone and uplinks                  |

\----------------------------------------------------------------------------------



***# Duplex Modes:***

**|------------------------------------------------------------------------------------------------------------------------------------------------------|**

**| Feature                 | Simplex                          | Half Duplex                 | Full Duplex                                               |**

**| ----------------------- | -------------------------------- | --------------------------- | --------------------------------------------------------- |**

| Communication direction | One-way                          | Two-way                     | Two-way                                                   |

| Same-time transmission  | No                               | No                          | Yes                                                       |

| Collision issue         | Not applicable in the same sense | Possible on shared Ethernet | No collision domain contention on the point-to-point link |

| CSMA/CD in Ethernet     | No                               | Yes, historically           | No                                                        |

| Example analogy         | Radio                            | Walkie-talkie               | Phone call                                                |

| Modern Ethernet         | No                               | Rare                        | Standard                                                  |

|------------------------------------------------------------------------------------------------------------------------------------------------------|



**# Uplink:**

It is a connection from a lower-level network device toward a higher-level or upstream device.

eg. PC -> Access Switch, Access Switch -> Core/Main Switch, Core Switch -> Router

