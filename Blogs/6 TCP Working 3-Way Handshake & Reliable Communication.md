---
tags:
  - Blogs
---

Transmission Control Protocol (TCP) is a reliable protocol which governs the transfer of data over the internet. It is needed as without a concrete set of rules different types of devices running different software between them wont be able to interact with each other. And the whole internet as we know now wont be possible.

**Problems TCP solves**
- Lack of standardization
- Un-reliable data transfer over the internet
- Error Detection
- Ordered delivery of package

**Three way handshake** is a mechanism that TCP uses to ensure that a reliable connection between the server and the client. 


![[5.jpeg]]

In the beginning the client sends a Synchronization Request, the server sends back New Synchronization Request plus an Acknowledgement and finally the client sends an Acknowledgement. The 3-way handshake happens at the start of every connection and a 4-way handshake is used to terminate a connection. 

The main selling point of TCP is its reliableness and correctness. TCP ensure this by the following ways:
- Three way handshake
- Each data segment sent by the sender needs to be replied with an Acknowledgement
- Each data packed it sequenced with numbers
- Checksums are used to check for corruptions

**Closing of TCP Connection**

TCP connection is closed using a 4 way handshake
![[Pasted image 20260128181638.png]]

Starting with a Fin request from the side that want to close the connection lets say its the client. After receiving the Fin request the server sends an ACK along with a FIN Request of its own. The client sends back an Ack at the end leading to the termination of the connection.