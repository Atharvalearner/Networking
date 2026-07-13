TCP is reliable because it assigns sequence numbers to the byte stream, uses acknowledgements to confirm received data, retransmits missing data, uses a checksum to detect corruption, reorders out-of-order data, and prevents duplicate delivery. It also uses flow control to avoid overwhelming the receiver and congestion control to adapt to network conditions. TCP therefore provides reliable, ordered byte-stream delivery over the best-effort IP network.



***Flow Diagram:***

Application Data

&#x20;     │

&#x20;     ▼

TCP assigns sequence numbers

&#x20;     │

&#x20;     ▼

TCP calculates checksum

&#x20;     │

&#x20;     ▼

Data transmitted

&#x20;     │

&#x20;     ▼

Receiver checks integrity

&#x20;     │

&#x20;     ├── Corrupted → Not accepted as valid data

&#x20;     │

&#x20;     └── Valid

&#x20;           │

&#x20;           ▼

&#x20;    Check sequence numbers

&#x20;           │

&#x20;      ┌────┼────┐

&#x20;      │    │    │

&#x20;    Correct Missing Duplicate

&#x20;      │    │    │

&#x20;      ▼    ▼    ▼

&#x20;   Accept  Wait/ Discard

&#x20;           recover

&#x20;      │

&#x20;      ▼

Send acknowledgements

&#x20;      │

&#x20;      ▼

Sender retransmits missing data when required





***# Why is TCP called reliable?***

TCP uses sequence numbers, acknowledgements, checksums, retransmissions, ordering, duplicate handling, and flow control to provide reliable byte-stream delivery.



***# How does TCP handle out-of-order data?***

It uses sequence numbers to identify byte positions and delivers the byte stream to the application in the correct order.



***# How does TCP detect duplicate data?***

By examining sequence numbers and already-received byte ranges.



***# What happens if an ACK is lost?***

The sender may retransmit data after its recovery logic determines acknowledgement is missing. The receiver recognizes duplicate bytes through sequence numbers and does not deliver them twice to the application





