TCP uses a sliding window so the sender can transmit multiple bytes or segments without waiting for an acknowledgement after every segment. This improves link utilization, especially on high-latency networks. As data is acknowledged, the window slides forward and allows new data to be sent. The sender is constrained by the receiver window for flow control and the congestion window for network congestion control.





As earlier data is acknowledged, the allowed sequence-number range/window moves forward, permitting new data to be sent.



***rwnd (receive window): manage flow control by receiver***

The receive window advertised by the receiver. It helps prevent the sender from overwhelming the receiver's buffer.



***cwnd (congestion window): manage congestion control by sender***

The congestion window maintained by the sender's TCP congestion-control logic. It limits data in flight based on network conditions.



**zero window:**

It means the receiver currently has no available receive-buffer space and asks the sender to stop normal data transmission temporarily.

