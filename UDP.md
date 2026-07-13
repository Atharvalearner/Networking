UDP is connectionless because it sends each datagram independently without first establishing a transport-layer connection. It does not perform a three-way handshake or provide built-in acknowledgements, retransmissions, ordering, flow control, or TCP-style connection state. This makes UDP simple and suitable for applications where low delay, independent messages, or application-controlled reliability are preferred, such as DNS, DHCP, and some real-time traffic.



|---------------------------------------------------------------------------------------|

| Feature                      | TCP                     | UDP                          |

| ---------------------------- | ----------------------- | ---------------------------- |

| Type                         | Connection-oriented     | Connectionless               |

| Handshake                    | Yes                     | No UDP handshake             |

| Header size                  | Minimum 20 bytes        | 8 bytes                      |

| Reliability                  | Built in                | Not built in                 |

| Acknowledgements             | Yes                     | No                           |

| Retransmissions              | Yes                     | No                           |

| Ordering                     | Yes                     | No                           |

| Duplicate handling           | Yes                     | No built-in guarantee        |

| Flow control                 | Yes                     | No                           |

| TCP-style congestion control | Yes                     | No                           |

| Data model                   | Byte stream             | Datagrams                    |

| Message boundaries           | Not preserved           | Preserved                    |

| Typical uses                 | Web, SSH, file transfer | DNS, DHCP, real-time traffic |

|---------------------------------------------------------------------------------------|





\# Does UDP guarantee delivery?

No. A UDP datagram may be delivered, lost, duplicated, or arrive out of order from the application's perspective.



\# If UDP is unreliable, how does DNS work?

The application protocol can use request IDs, timeouts, retries, alternate servers, or switch to another transport when needed. Reliability can be implemented above UDP.



\# Does UDP have a checksum?

Yes. UDP has a checksum for integrity checking, but corruption detection alone does not provide reliable delivery.



\# Does connectionless mean no sockets?

No. UDP applications still use sockets. UDP simply does not establish a TCP-style transport connection.

on a UDP socket, you are simply telling your own Operating System (OS): "I only want to talk to this specific IP and port."

You set the destination once. The OS remembers it. The OS automatically drops packets coming from any other IP.



\# If you are a Client talking to One Server   → Use Connected UDP.

\# If you are a Server talking to Many Clients → Use Unconnected UDP.





