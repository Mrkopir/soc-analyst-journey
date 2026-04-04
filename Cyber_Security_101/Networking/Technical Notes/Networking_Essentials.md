# Networking Essentials - TryHackMe

## 1. DHCP

DHCP is an application-level protocol that relies on UDP; the server listens on UDP port 67, and the client sends from UDP port 68.

DHCP follows four steps: Discover, Offer, Request, and Acknowledge (DORA):

1. DHCP Discover: The client broadcasts a DHCPDISCOVER message seeking the local DHCP server if one exists.
2. DHCP Offer: The server responds with a DHCPOFFER message with an IP address available for the client to accept.
3. DHCP Request: The client responds with a DHCPREQUEST message to indicate that it has accepted the offered IP.
4. DHCP Acknowledge: The server responds with a DHCPACK message to confirm that the offered IP address is now assigned to this client.

## 2. ARP

Address Resolution Protocol (ARP) makes it possible to find the MAC address of another device on the Ethernet.
An ARP Request or ARP Reply is not encapsulated within a UDP or even IP packet; it is encapsulated directly within an Ethernet frame.
ARP is considered layer 2 because it deals with MAC addresses. Others would argue that it is part of layer 3 because it supports IP operations. What is essential to know is that ARP allows the translation from layer 3 addressing to layer 2 addressing.

## 3. ICMP

Internet Control Message Protocol (ICMP) is mainly used for network diagnostics and error reporting. Two popular commands rely on ICMP, and they are instrumental in network troubleshooting and network security.

The commands are:

- `ping`: This command uses ICMP to test connectivity to a target system and measures the round-trip time (RTT). In other words, it can be used to learn that the target is alive and that its reply can reach our system.
- `traceroute`: This command is called traceroute on Linux and UNIX-like systems and tracert on MS Windows systems. It uses ICMP to discover the route from your host to the target.

## 4. NAT

The idea behind NAT lies in using one public IP address to provide Internet access to many private IP addresses. In other words, if you are connecting a company with twenty computers, you can provide Internet access to all twenty computers by using a single public IP address instead of twenty public IP addresses.
