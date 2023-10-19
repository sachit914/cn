# cn


# client server


            http request and response
+---------+       +---------+      +---------+
| Client1 |<----->|         |      |         |
+---------+       |         |      | Server2 |
                  | Network |<---> |         |
+---------+       |         |      |         |
| Client2 |<----->|         |      +---------+
+---------+       +---------+


## protocols

 protocols are set of rules

### TCP

TCP (Transmission Control Protocol)          three-way handshake

1) Connection-Oriented:Before data can be sent, the two devices must establish a connection with each other. This is done using a process called the "three-way handshake."
2) Reliable:TCP ensures that all data sent is received correctly by the other side. If any data is lost during transmission, TCP will resend it.
3) Ordered:If packets (chunks of data) are sent out of order, TCP will rearrange them back into the correct order when they arrive at their destination.
4) Flow Control:TCP can control the rate of data transmission between two devices to ensure that a fast sender doesn't overwhelm a slow receiver.
5) Error Checking:TCP uses a mechanism called "checksum" to check for errors in the data. If there's an error, the corrupted data is retransmitted.
6) End-to-End Communication:TCP allows for direct communication between the source and destination. Both the sender and the receiver maintain a "socket", which is a combination of an IP address and port number, to ensure data is delivered to the right application.


### UDP 

UDP (User Datagram Protocol)

1) Connectionless:Unlike TCP, UDP doesn't establish a connection before sending data. You just send the data (often referred to as "datagrams") without any initial setup.
2) Unreliable:UDP doesn't guarantee that your data will reach its destination. If a datagram gets lost in transit, UDP doesn't know or care.
3) No Ordering:If you send multiple datagrams, they might arrive in a different order than they were sent. UDP doesn't reorganize them.
4) No Flow Control:UDP doesn't manage the speed of data transmission, so a fast sender could potentially overwhelm a slow receiver.
5) Lightweight:Without the need for acknowledgments, connections, and other features that TCP has, UDP is simpler and faster in situations where those features aren't necessary.
6) Checksum Optional:UDP can check for some basic errors in the data (using a checksum), but this is optional and not as rigorous as TCP.

When is UDP Used?

Streaming Media: Like online videos or radio where if you miss a few packets, it's better to continue playing than to pause and wait for retransmission.
Online Gaming: Where real-time speed is more important than absolute accuracy.
DNS Queries: When you enter a website name and your computer looks up its IP address.
VOIP (Voice Over IP): Such as Skype or Zoom, where a dropped packet might result in a momentary glitch in conversation but retransmitting it would be more disruptive.

### HTTP 

### how data is transferred ip address 

