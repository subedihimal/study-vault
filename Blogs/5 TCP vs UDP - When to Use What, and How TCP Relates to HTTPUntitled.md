---
tags:
  - Blogs
---
### TCP
Transmission Control Protocol is basically rules that govern the transfer of packages or data over the internet. It is a reliable protocol which ensures that the data packet is transferred to the required destination and even if the data packet failed to transfer, the sender gets to know as it wont receive a acknowledgement. Here data is converted into smaller chunks called segments

### UDP
User Datagram Protocol is another type of rules that govern the transfer of packages or data over the internet. It is unreliable compared to TCP but is a lot more lightweight and fast. Data is converted int small chunks called datagrams

**Key differences between tcp and udp**

| TCP                                                 | UDP                                                 |
| --------------------------------------------------- | --------------------------------------------------- |
| It is a Reliable Protocol                           | It is a unreliable Protocol                         |
| Uses 3 way handshake                                | Doesn't use any handshake mechanism                 |
| Slow compared to udp                                | Fast compared to tcp                                |
| Data is converted into small chunks called segments | Data is converted into small chunks called datagram |
| Resends lost packets                                | No resending                                        |
You should use tcp where the data is very important and the sequence of the data is also very important. 
Some use case of TCP are :
- Messages/ Emails
- Banking Transactions
- Sending Images
- Software/ Application download
In other hand you should use UDP when the sequence of data or the data packet it self is less important then fast delivery.
Some use case of UDP are
- Video/Audio Call
- Live Board-casting
- Gaming

### HTTP
HTTP stands for Hyper-Text Transfer Protocol. It is a set of rules that govern the transfer of data between the server and the client that may include html, css, images, videos, javascript, browser resources which are used by your web applications to display an interactive webpage.
Http uses TCP in the transport layer, making it a reliable protocol. Http works on top of Tcp and tcp ensures that the packages of http is delivered.