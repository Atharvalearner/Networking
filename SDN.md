Software-Defined Networking, or SDN, is an architecture that separates network control from packet forwarding and makes the network programmable through software. It has three main layers: the application layer, which defines policies; the control layer, containing the SDN controller; and the infrastructure layer, containing physical or virtual forwarding devices. Applications communicate with the controller through northbound APIs, while the controller communicates with devices through southbound APIs. The main benefits are centralized policy, automation, programmability, and a broader view of the network.



***Simply:*** 

SDN Separate the control plane from individual network devices(Router/Switch/Other Forwarding Devices) and manage network behavior centrally through software.



**# SDN:**

It is a network architecture that separates network control from packet forwarding and makes the network centrally programmable through software.



* Application → What do I want?
* Controller  → How should the network do it?
* Devices     → Forward the traffic



&#x20;                ADMINISTRATOR

&#x20;                      ▼

&#x20;             ┌─────────────┐

&#x20;             │  APPLICATIONS   │

&#x20;             │                 │

&#x20;             │ Security        │

&#x20;             │ QoS             │

&#x20;             │ Automation      │

&#x20;             │ Analytics       │

&#x20;             └──────┬──────┘

&#x20;                NORTHBOUND API

&#x20;                      ▼

&#x20;             ┌─────────────┐

&#x20;             │ SDN CONTROLLER  │

&#x20;             │                 │

&#x20;             │ Network View    │

&#x20;             │ Policy          │

&#x20;             │ Path Decisions  │

&#x20;             │ Automation      │

&#x20;             └──────┬──────┘

&#x20;                SOUTHBOUND API

&#x20;          ┌────────┼─────────┐

&#x20;          ▼          ▼           ▼

&#x20;       SWITCH 1    SWITCH 2    SWITCH 3

&#x20;       Data Plane  Data Plane  Data Plane

&#x20;          └────────┼─────────┘

&#x20;                      ▼

&#x20;                 USER TRAFFIC





**# What is the main difference between traditional networking and SDN?**

Traditional networks usually distribute control logic across individual devices

while SDN logically centralizes control and programs network behavior through a controller.



**| Traditional Networking                | SDN                                          |**

**| ------------------------------------- | -------------------------------------------- |**

| Control distributed across devices    | Control logically centralized                |

| Device-by-device configuration common | Centralized policy/automation                |

| CLI-heavy management                  | API and software-driven management           |

| Limited global visibility per device  | Controller can maintain broader network view |

| Manual changes common                 | Automation is a core goal                    |

| Hardware and control tightly coupled  | Control and forwarding are more separated    |





**# What are the three layers of SDN?**

Application layer: contains software that defines network requirements or policies.

Control/Controller layer: brain of the SDN network that controls network devices and apply policies on them.

Infrastructure layer: Switches, Routers, Other Forwarding devices: It Forward the traffic



**# SDN/controller-based approach:**

*Administrator*

&#x20;     *↓*

*Define policy once*

&#x20;     *↓*

*Controller*

&#x20;     *↓*

*Push/coordinate policy across network*





**# SDN-style network:**

*Controller understands network state*

&#x20;         *↓*

*Controller programs forwarding behavior*

&#x20;         *↓*

*Device stores forwarding rules*

&#x20;         *↓*

*Packet arrives*

&#x20;         *↓*

*Device matches existing rule*

&#x20;         *↓*

*Packet forwarded*



**# What is an SDN controller?**

Logically centralized control component 

that maintains network state, interprets policies, makes control decisions, and programs or coordinates network devices.



**# Why "North" and "South"?**

&#x20;            APPLICATIONS

&#x20;                 ▲

&#x20;                 │ NORTH

&#x20;            CONTROLLER

&#x20;                 │ SOUTH

&#x20;                 ▼

&#x20;              DEVICES



**# Northbound API:**

It connects applications and automation systems with the SDN controller.



**# Southbound API:**

It connects the controller with network infrastructure and allows the controller to program or manage devices.



**# Is OpenFlow the same as SDN?**

No. OpenFlow is one possible southbound protocol used in some SDN architectures. SDN is the broader architecture.



**# Does every packet go to the controller?**

No. Normally, devices forward packets locally using already installed forwarding rules. Only specific traffic or new flows may involve the controller, depending on the design.



**# What is the difference between proactive and reactive flow installation?**

In proactive mode, rules are installed before traffic arrives. In reactive mode, a new flow may trigger a controller decision and rule installation.



**# Is the SDN controller a single point of failure?**

It could be if poorly designed, but production controllers are commonly deployed as clusters. Therefore, the controller is logically centralized but can be physically distributed.



**# Does SDN remove the control plane completely from routers and switches?**

No. SDN logically separates and centralizes major control functions, but real devices may still retain local control and management capabilities.



**# Where is SDN used?**

Data centers

Cloud networks

Campus networks

WAN / SD-WAN

Telecom networks

Network security

Large-scale automation

