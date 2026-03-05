# Extending Your Network – TryHackMe

## 1. Port Forwarding

### What is it
A router configuration that enables external devices on the internet to access specific services, devices, or servers within a private local network.

### How it works
Mapping a public IP address and specific port number to a private IP and port, bypassing the default NAT block to reach internal servers, gaming consoles, or cameras

## 2. Firewall

### What is it
A firewall is a device within a network responsible for determining what traffic is allowed to enter and exit. Think of a firewall as border security for a network. An administrator can configure a firewall to permit or deny traffic from entering or exiting a network

### Types of Firewall

1. Stateless Firewall: This firewall type uses a static set of rules to determine whether or not individual packets are acceptable or not. For example, a device sending a bad packet will not necessarily mean that the entire device is then blocked.

Whilst these firewalls use much fewer resources than alternatives, they are much dumber. For example, these firewalls are only effective as the rules that are defined within them. If a rule is not exactly matched, it is effectively useless.

However, these firewalls are great when receiving large amounts of traffic from a set of hosts (such as a Distributed Denial-of-Service attack)

2. Stateful Firewall: This type of firewall uses the entire information from a connection; rather than inspecting an individual packet, this firewall determines the behaviour of a device based upon the entire connection.

This firewall type consumes many resources in comparison to stateless firewalls as the decision making is dynamic. For example, a firewall could allow the first parts of a TCP handshake that would later fail.

If a connection from a host is bad, it will block the entire device.

## 3. VPN (Virtual Private Network)

### What is it
A technology that allows devices on separate networks to communicate securely by creating a dedicated path between each other over the Internet (known as a tunnel).

## Some benefits
- Allows networks in different geographical locations to be connected.
- Offers privacy.
- Offers anonymity.

## VPN technologies

- PPP: This technology is used by PPTP (explained below) to allow for authentication and provide encryption of data. VPNs work by using a private key and public certificate (similar to SSH). A private key & certificate must match for you to connect.
- PPTP (Point-to-Point Tunneling Protocol): is the technology that allows the data from PPP to travel and leave a network. 
- IPSec (Internet Protocol Security): encrypts data using the existing Internet Protocol (IP) framework.