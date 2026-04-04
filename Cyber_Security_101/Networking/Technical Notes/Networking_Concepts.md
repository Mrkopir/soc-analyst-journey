# Networking Concepts - TryHackMe

## 1. OSI

The OSI (Open Systems Interconnection) model is a conceptual model developed by the International Organization for Standardization (ISO) that describes how communications should occur in a computer network.

The OSI model is composed of seven layers (Please Do Not Throw Spinach Pizza Away):

1. Physical Layer: deals with the physical connection between devices.
2. Data Link Layer: represents the protocol that enables data transfer between nodes on the same network segment.
3. Network Layer: is concerned with sending data between different networks.
4. Transport Layer: enables end-to-end communication between running applications on different hosts.
5. Session Layer: responsible for establishing, maintaining, and synchronising communication between applications running on different hosts.
6. Presentation Layer: ensures the data is delivered in a form the application layer can understand.
7. Application Layer: provides network services directly to end-user applications.

## 2. TCP/IP Model

Transmission Control Protocol/Internet Protocol and was developed in the 1970s by the Department of Defense (DoD). One of the strengths of this model is that it allows a network to continue to function as parts of it are out of service, for instance, due to a military attack.

1. Application Layer: The OSI model application, presentation and session layers, i.e., layers 5, 6, and 7, are grouped into the application layer in the TCP/IP model.
2. Transport Layer: This is layer 4.
3. Internet Layer: This is layer 3. The OSI model’s network layer is called the Internet layer in the TCP/IP model.
4. Link Layer: This is layer 2.

## 3. IP Addresses and Subnets

An IP address comprises four octets, i.e., 32 bits. Being 8 bits, an octet allows us to represent a decimal number between 0 and 255.

There are two types of IP addresses:

- Public IP addresses
- Private IP addresses

RFC 1918 defines the following three ranges of private IP addresses:

- 10.0.0.0 - 10.255.255.255 (10/8)
- 172.16.0.0 - 172.31.255.255 (172.16/12)
- 192.168.0.0 - 192.168.255.255 (192.168/16)

## 4. UDP and TCP

UDP (User Datagram Protocol) allows us to reach a specific process on this target host. UDP is a simple connectionless protocol that operates at the transport layer, i.e., layer 4. Being connectionless means that it does not need to establish a connection. UDP does not even provide a mechanism to know that the packet has been delivered.

TCP (Transmission Control Protocol) is a connection-oriented transport protocol. It uses various mechanisms to ensure reliable data delivery sent by the different processes on the networked hosts. Like UDP, it is a layer 4 protocol. Being connection-oriented, it requires the establishment of a TCP connection before any data can be sent.

## 5. Encapsulation

Encapsulation is an essential concept as it allows each layer to focus on its intended function. In the image below, we have the following four steps:

1. Application data: It all starts when the user inputs the data they want to send into the application. For example, you write an email or an instant message and hit the send button. The application formats this data and starts sending it according to the application protocol used, using the layer below it, the transport layer.
2. Transport protocol segment or datagram: The transport layer, such as TCP or UDP, adds the proper header information and creates the TCP segment (or UDP datagram). This segment is sent to the layer below it, the network layer.
3. Network packet: The network layer, i.e. the Internet layer, adds an IP header to the received TCP segment or UDP datagram. Then, this IP packet is sent to the layer below it, the data link layer.
4. Data link frame: The Ethernet or WiFi receives the IP packet and adds the proper header and trailer, creating a frame.