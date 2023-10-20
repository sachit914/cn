# cn
https://www.youtube.com/watch?v=IPvYjXCsTg8&t=1550s

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

Certainly! HTTP stands for Hypertext Transfer Protocol. It's the foundation of any data exchange on the Web. Let's break it down in simple terms:

What is HTTP?

Think of HTTP as a language that computers use to communicate with each other on the internet. When you enter a URL in your browser or click on a link, your computer sends an HTTP request. The server, where the website is hosted, understands this request, processes it, and sends back an HTTP response containing the webpage you asked for.

HTTP Requests and HTTP Responses


### how data is transferred ip address 
An IP address (Internet Protocol address) is a unique identifier assigned to each device connected to a computer network that uses the Internet Protocol for communication

There are two versions of IP addresses:

IPv4 and IPv6 

### port number 
In computer networking, a port number is a 16-bit unsigned integer that helps identify a specific process to which data should be directed when it arrives at a computer. It acts as an endpoint in an operating system's IP address, allowing multiple network services to run on a single server without conflicts

reserved port numbers

1) Well-Known Ports (0-1023): Used by system processes that provide widely-used types of network services. For instance:
- Port 80: HTTP
- Port 443: HTTPS
- Port 22: SSH
- Port 21: FTP

2)Registered Ports (1024-49151): These can be registered for certain services with the IANA (Internet Assigned Numbers Authority). While they aren't used for system services like the well-known ports, many popular applications have conventionally associated ports in this range.

eg MongoDB, by default, uses port 27017. This falls within the range of "Registered Ports" (1024-49151).

3)Dynamic or Private Ports (49152-65535): These are not registered with IANA and are available for any application's use on an as-needed basis. They're sometimes used as ephemeral ports, which are temporary and assigned automatically by the operating system when needed.

eg testing port 

### lan man wan 

LAN (Local Area Network):

A WAN covers a broader area, connecting multiple LANs 

MAN (Metropolitan Area Network):

### modem and router 

modem:Purpose: It connects your local network to the internet. It's the gateway through which all traffic between the local devices and external servers passes.

router:Function: Routers are devices that forward data packets between computer networks. They guide the data sent over the internet to their destination.

Purpose: A router allows multiple devices in your home or office to connect to the internet at once. It assigns local IP addresses to each device and manages the traffic between them and the external internet.

### topologies

Bus 

ring 

star 

tree

mesh

# structure of network

## osi model     (concept model) 

            +-------------------------+  -----------
            | 7. Application Layer    |            |
            +-------------------------+            |   known as software layer
            | 6. Presentation Layer   |            |
            +-------------------------+            |
            | 5. Session Layer        |            |   
            +-------------------------+   ----------           
            | 4. Transport Layer      |                        heart of layer (passes data between top and bottom layer
            +-------------------------+  -----------         
            | 3. Network Layer        |            |
            +-------------------------+            |
            | 2. Data Link Layer      |            |    know as hardware layer
            +-------------------------+            |
            | 1. Physical Layer       |            |
            +-------------------------+   ----------

### Application layer

User Interface: The Application Layer provides a user interface where end-users can directly interact with software applications.

### Presentation layer

The Presentation Layer of the OSI model is responsible for translating, encrypting, and compressing data between the Application and Transport layers, ensuring that data is in a format both sender and receiver can understand.

### session layer

The Session Layer of the OSI model manages and controls the establishment, maintenance, and termination of communication sessions between two devices.

### Transport layer    (TCP AND UDP)
The Transport Layer of the OSI model ensures end-to-end communication, data flow control, error recovery, and segmentation of large data packets for efficient and reliable data transfer between devices.

### NetWork Layer

The Network Layer of the OSI model is responsible for determining the best path for data transmission, routing packets from the source to the destination across the network, and handling logical addressing, such as IP addresses.

### data link layer

The Data Link Layer of the OSI model is responsible for ensuring error-free data transfer between adjacent nodes on a network, framing data packets, and controlling access to the shared medium through mechanisms like MAC addressing.

### Physical Layer

The Physical Layer of the OSI model deals with the transmission and reception of raw data bits over a physical medium, such as cables or wireless, defining characteristics like voltage levels, physical connectors, and transmission rates.


## tcp ip model (this model is used)


            +-------------------------+
            | Application Layer       |
            +-------------------------+
            | Transport Layer         |
            +-------------------------+
            | Network Layer           |
            +-------------------------+
            | Data Link Layer         |
            +-------------------------+
            | Physical Layer          |
            +-------------------------+


- Application Layer: Represents high-level protocols, such as HTTP, FTP, and SMTP.
- Transport Layer: Deals with connection-oriented communication and connectionless communication, primarily with the TCP and UDP protocols, respectively.
- Network Layer: Also known as the Internet layer in the four-layer model, it manages logical addressing and packet routing, primarily with the IP protocol.
- Data Link Layer: Ensures direct point-to-point data transfer between two devices on the same network.
- Physical Layer: Deals with the physical transmission medium, defining how the bits are transmitted over cables, wireless, etc.





