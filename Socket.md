***Socket (IP + Port + TCP/UDP Connection) :***

* An **operating-system communication endpoint**. 
* Created and managed by the OS.
* Used by an application to communicate, **send and receive network data**.
* It is associated with a **transport protocol** and may be bound to an IP address and port.
* An IP address identifies the host, while a port identifies the application or service endpoint. 
* For example, a client at 192.168.1.10:51000 can connect to a web server at 10.0.0.50:443. A TCP connection is uniquely identified by the source IP, source port, destination IP, and destination port, known as the **4-tuple**.
* ***Applications request socket creation through the operating system's socket API, and the OS kernel manages them.***
* **Both TCP and UDP applications use sockets**, but UDP does not establish a TCP-style connection.



* Eg. 192.168.1.10:50000 is a socket, It is commonly called a socket endpoint or socket address. Technically, the socket itself is the OS object used by the application.





***# Socket vs connection***

A socket is the endpoint/API object used for communication. 

A TCP connection is the communication relationship between two endpoints.



Socket A             	                Socket B

192.168.1.10:51000  <==============>  10.0.0.50:443

&#x20;                    TCP Connection

