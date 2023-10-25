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



## web protocol

tcp/ip:

- HTTP
- DHCP
- FTP
- SMTP
- POP3
- IMAP
- SSH

TELNET

UDP  (stateless connection)

sockets

ports

#  HTTP (Hypertext Transfer Protocol)

HTTP is the foundation of data communication on the World Wide Web. It's an application protocol that runs on top of the TCP/IP suite of protocols. 


HTTP (is application layer protocol)

http uses tcp

is stateless protocol

##### Basics:
- Client-server model:
            - The client sends a request to a server, and the server sends back a response.
- Stateless:
            - Each request from a client to a server must contain all the information needed to understand and process the request. The server does not retain any session information between requests.
- Request-response mechanism:
            -  A client sends an HTTP request and waits for an HTTP response from the server.
- Uniform Resource Locators (URLs):
            -  HTTP uses URLs to identify resources.

##### HTTP Methods:

-GET
- POST
- PUT
- DELETE
- HEAD: Similar to GET but only retrieves headers, not the body of the resource.

##### Status Codes

- 200 OK: The request was successful.
- 404 Not Found: The requested resource was not found.
- 500 Internal Server Error: There was a server-side error processing the 

##### Headers:

They provide meta-information about the request or response. Examples:

##### Content-Type:
Describes the type of the data in the body (like text/html or application/json).
- User-Agent: Information about the client (like browser or device type).
- Cache-Control: Directives for caching the resource.
- Body: Contains the actual data of the message. In a request, it might be data being sent to the server (like form data). In a response, it might be the content of a web page or API data.
  

                Client                              Server
                  |                                   |
                  |---(1) HTTP Request-------------->|
                  |                                   |
                  |<--(2) HTTP Response--------------|
                  |                                   |
            
#### Evolution:
- HTTP/1.0: The first documented version. It opened a new TCP connection for every HTTP request/response pair.
- HTTP/1.1: Introduced in 1997, it brought performance improvements, such as the ability to reuse TCP connections for multiple requests.
- HTTP/2: Introduced in 2015, it provided major enhancements in performance (e.g., multiplexing multiple requests over a single connection) and efficiency.
- HTTP/3: Building on HTTP/2 but replacing TCP with the more efficient QUIC protocol.


#### Working
            
                Client (Browser)                     Server (Web/HTTP server)
                  |                                   |
                  |---(1) HTTP Request-------------->|
                  |   (Method, URL, Headers, Body)    |
                  |                                   |
                  |<--(2) HTTP Response--------------|
                  |   (Status, Headers, Body)         |
                  |                                   |



            Client (Browser)           Server
                 |                       |
                 |  GET /index.html      |
                 |  Host: www.example.com|
                 |---------------------->|
                 |                       |
                 |                       |
                 |  HTTP/1.1 200 OK      |
                 |  Content-Type: text/html|
                 |                       |
                 |  <html>...Content...</html>|
                 |<----------------------|
                 |                       |
            
- The client wants to access index.html from www.example.com.
- The client sends an HTTP GET request.
- The server processes the request and responds with a 200 OK status, indicating a successful request. It also specifies that the content type is text/html.
- The server then sends the content of index.html as the body of the response.



# cokies (unique string)

A cookie is a small piece of data that a server sends to the user's web browser. The browser may store it and send it back with later requests to the same server. This helps the server identify the user, remember user preferences, maintain user sessions, or track user behaviors.


#### Primary Uses:
- Session Management: Cookies can keep users logged in as they navigate through different pages of a website.
- Personalization: Websites can remember user preferences, such as themes, language settings, or even previously viewed content.
- Tracking: Cookies can track user behavior, such as the pages they've visited or the links they've clicked. This is often used for analytics and advertising.


#### Cookie Attributes:
- Name and Value: A unique name and its associated value.
- Domain and Path: Define the scope of the cookie – which URLs it is valid for.
- Expires: The expiration date. If not set, the cookie will expire at the end of the session (i.e., when the browser closes).
- Secure: If present, the cookie will be sent only over secure (HTTPS) connections.
- HttpOnly: If present, JavaScript cannot access this cookie, which provides some protection against cross-site scripting (XSS) attacks.

#### Working

            1. User accesses a website for the first time:
            
            User's Browser                 Server (e.g., www.example.com)
                  |                                  |
                  |---(1) HTTP Request-------------->|
                  |                                  |
                  |<--(2) HTTP Response with "Set-Cookie" Header |
                  |   (Contains cookie: session_id=1234)         |
                  |                                  |
            
            2. User makes subsequent requests to the same server:
            
            User's Browser                 Server
                  |                                  |
                  |---(3) HTTP Request with "Cookie" Header--->
                  |   (Contains cookie: session_id=1234)        |
                  |                                  |
                  |<--(4) HTTP Response -------------|
                  |                                  |



#### Security and Privacy Concerns:
Third-party cookies: These cookies are set by domains other than the one the user is visiting. They are mainly used for tracking and online-advertising purposes. Many modern browsers offer ways to block third-party cookies due to privacy concerns.



# DNS

The Domain Name System (DNS) is a decentralized and hierarchical system that translates human-friendly domain names, like www.example.com, into IP addresses that computers use to identify each other on the network.

#### The Basics of DNS

At a high level, when you want to visit a website, your computer needs to know the IP address of that website's server. But humans are not good at remembering IP addresses, so we use domain names. DNS is the system that performs the translation between domain names and IP addresses.


#### Key Components of DNS:
- Domain Name: A human-readable address (like www.openai.com).
- Resolver (or DNS Client): The tool your computer uses to ask the DNS system for an IP address.
- Root Servers: The top-level of the DNS hierarchy that can direct queries toward the servers responsible for specific top-level domains (like .com or .net).
- TLD (Top-Level Domain) Servers: Responsible for top-level domains like .com, .org, etc.
- Authoritative DNS Servers: Provide the actual IP address mapping for a domain. They have the final authority over a domain and its associated resources.


#### working

            User's Browser            Resolver                 Root Server
                  |                     |                          |
                  |---(1) www.example.com? --->|                  |
                  |                     |                          |
                  |                     |---(2) Where's .com? --->|
                  |                     |                          |
                  |                     |<--(3) TLD Server for .com|
                  |                     |                          |
            
                                  TLD Server                  Authoritative Server
                                       |                          |
                  |                     |---(4) Where's example.com? --->|
                  |                     |                          |
                  |                     |<----(5) IP for example.com ----|
                  |                     |                          |
            
            User's Browser            Resolver
                  |                     |
                  |<---(6) IP Address ---|
                  |                     |



(1) Domain Request: You type www.example.com in your browser. The browser asks the Resolver for the IP address.
(2) Ask the Root: The Resolver doesn't know the IP, so it asks a Root Server.
(3) Root's Response: The Root Server responds with the address of the TLD Server responsible for .com domains.
(4) Ask the TLD Server: The Resolver then asks the .com TLD Server about www.example.com.
(5) TLD's Response: The TLD Server responds with the IP address of the Authoritative Server for example.com.
(6) IP Address Returned: Finally, the Resolver asks the Authoritative Server for the IP address of www.example.com and then returns this IP address to your browser.

Your browser can now use this IP address to connect directly to the web server hosting www.example.com and request the web page content.

#### Caching
For efficiency, at every step of this process, the results can be cached. This means that frequently accessed domain names don't need to go through this full process every time they are requested. For instance, if someone else on your network recently visited www.example.com, the Resolver might have its IP address cached and can return it immediately without querying the Root or TLD servers.

