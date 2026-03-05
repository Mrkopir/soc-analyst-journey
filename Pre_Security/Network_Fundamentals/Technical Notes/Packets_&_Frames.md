# Packets & Frames – TryHackMe

## 1. What are Packets and Frames

### What It Is

Packets: a piece of data from Layer 3 (Network Layer) of the OSI model, containing information such as an IP header and payload
Frames: used at Layer 2 (Data Link) of the OSI model, which, encapsulates the packet and adds additional information such as MAC addresses.

### How it works

Packets: A packet using this protocol will have a set of headers that contain additional pieces of information to the data that is being sent across a network.
1. A device wants to send data to another device.
2. It checks if the destination is in the same subnet.
3. If yes:
   - It uses ARP to resolve the IP address to a MAC address.
4. The packet is encapsulated into a frame.
5. The frame is transmitted over the physical medium.
6. The receiving device checks the FCS.
7. If valid, the frame is decapsulated and the packet moves up to Layer 3.

### Structures
Some notable headers (packets) include:

- Time to Live: This field sets an expiry timer for the packet to not clog up network if it never manages to reach a host or escape!
- Checksum: This field provides integrity checking for protocols such as TCP/IP. If any data is changed, this value will be different from what was expected and therefore corrupt.
- Source Address: The IP address of the device that the packet is being sent from so that data knows where to return to.
- Destination Address:	The device's IP address the packet is being sent to so that data knows where to travel next.

An Ethernet frame typically contains:
- Destination MAC Address: The physical address of the receiving device on the local network.
- Source MAC Address: The physical address of the sending device.
- EtherType: Identifies which protocol is encapsulated inside the frame (e.g., IPv4, IPv6, ARP).
- Payload: The encapsulated Layer 3 packet (such as an IP packet).
- Frame Check Sequence (FCS): Used for error detection. If the frame is corrupted during transmission, it will be discarded.


## 2. TCP/IP

### What It Is
This protocol is very similar to the OSI model. The TCP/IP protocol consists of four layers and is arguably just a summarised version of the OSI model.
Layers:
- Application
- Transport
- Internet
- Network Interface


### Headers of TCP
- Source Port: This value is the port opened by the sender to send the TCP packet from. This value is chosen randomly (out of the ports from 0-65535 that aren't already in use at the time).
- Destination Port: This value is the port number that an application or service is running on the remote host
- Source IP: This is the IP address of the device that is sending the packet.
- Destination IP: This is the IP address of the device that the packet is destined for.
- Sequence Number: When a connection occurs, the first piece of data transmitted is given a random number.
- Acknowledgement Number: After a piece of data has been given a sequence number, the number for the next piece of data will have the sequence number + 1.
- Checksum: This value is what gives TCP integrity. A mathematical calculation is made where the output is remembered. When the receiving device performs the mathematical calculation, the data must be corrupt if the output is different from what was sent.
- Data: This header is where the data, i.e. bytes of a file that is being transmitted, is stored.
- Flag: This header determines how the packet should be handled by either device during the handshake process. Specific flags will determine specific behaviours.

### Three-way handshake

1. SYN: A SYN message is the initial packet sent by a client during the handshake. This packet is used to initiate a connection and synchronise the two devices together (we'll explain this further later on).
2. SYN/ACK: This packet is sent by the receiving device (server) to acknowledge the synchronisation attempt from the client.
3. ACK: The acknowledgement packet can be used by either the client or server to acknowledge that a series of messages/packets have been successfully received.
4. DATA: Once a connection has been established, data (such as bytes of a file) is sent via the "DATA" message.
5. FIN: This packet is used to cleanly (properly) close the connection after it has been complete.
6. RST: This packet abruptly ends all communication. This is the last resort and indicates there was some problem during the process. For example, if the service or application is not working correctly, or the system has faults such as low resources. 

### Example, how it works (TCP OPEN CONNECTION)
1. SYN - Client: Here's my Initial Sequence Number(ISN) to SYNchronise with (0)
2. SYN/ACK - Server: Here's my Initial Sequence Number (ISN) to SYNchronise with (5,000), and I ACKnowledge your initial number sequence (0)
3. ACK - Client: I ACKnowledge your Initial Sequence Number (ISN) of (5,000), here is some data that is my ISN+1 (0 + 1)

### Example, how it works (TCP CLOSE CONNECTION)
1. FIN - Client
2. ACT - Server
3. FIN - Server
4. ACT - Client


## 3. UDP/IP

### Headers of UDP
- Time to Live (TTL): This field sets an expiry timer for the packet, so it doesn't clog up your network if it never manages to reach a host or escape
- Source Address: The IP address of the device that the packet is being sent from, so that data knows where to return to.
- Destination Address: The device's IP address the packet is being sent to so that data knows where to travel next.
- Source Port: This value is the port that is opened by the sender to send the UDP packet from. This value is randomly chosen (out of the ports from 0-65535 that aren't already in use at the time).
- Destination Port: This value is the port number that an application or service is running on the remote host (the one receiving the data); for example, a webserver running on port 80. Unlike the source port, this value is not chosen at random.
- Data: This header is where data, i.e. bytes of a file that is being transmitted, is stored.

## 4. Ports 101

### What It Is
Networking devices also use ports to enforce strict rules when communicating with one another. When a connection has been established (recalling from the OSI model's room), any data sent or received by a device will be sent through these ports.

Any port that is within 0 and 1024 (1,024) is known as a common port.

### COMMON PORTS

- 21 FTP: This protocol is used by a file-sharing application built on a client-server model, meaning you can download files from a central location.
- 22 SSH: This protocol is used to securely login to systems via a text-based interface for management.
- 80 HTTP: This protocol powers the World Wide Web (WWW)! Your browser uses this to download text, images and videos of web pages.
- 443 HTTPS: This protocol does the exact same as above; however, securely using encryption.
- 445 Server Message Block (SMB): This protocol is similar to the File Transfer Protocol (FTP); however, as well as files, SMB allows you to share devices like printers.
- 3389 Remote Desktop Protocol (RDP): This protocol is a secure means of logging in to a system using a visual desktop interface (as opposed to the text-based limitations of the SSH protocol).