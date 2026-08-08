TCP uses a three-way handshake to establish a reliable connection before data transfer. In the first step, the client sends a SYN packet containing its initial sequence number. In the second step, the server responds with a SYN-ACK packet, acknowledging the client's sequence number and sending its own sequence number. Finally, the client sends an ACK acknowledging the server's sequence number. After these three steps, both sides enter the ESTABLISHED state and data transmission begins. The handshake ensures that both devices are reachable, synchronizes sequence numbers, and prepares resources for reliable communication.





**# Why do we need the Three-Way Handshake:**

TCP is a connection-oriented protocol.

Before transferring data, both the client and the server must



1. Verify that the other device is reachable.
2. Synchronize sequence numbers.
3. Allocate resources (buffers, connection state).
4. Establish a reliable connection.

This process is called the TCP Three-Way Handshake.



