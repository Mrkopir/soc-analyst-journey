# Network Fundamentals – TryHackMe

## 1. What is Networking

## 1.1 What is the Internet

### What It Is

The Internet is a global network that connects many smaller networks together.  
It allows devices worldwide to communicate using standardized protocols.

The first version of the modern Internet originated from ARPANET in the late 1960s.

A network can be:
- A private network (e.g., home or corporate LAN)
- A public network (the Internet)

### How It Works

- Devices communicate using IP addresses.
- Data is broken into packets.
- Routers forward packets between networks.
- Communication follows TCP/IP protocol rules.

### Why It Matters for Security

Because the Internet connects systems globally:
- Devices are exposed to remote attacks.
- Attackers can scan public IP ranges.
- Misconfigured services may be publicly accessible.

### Blue Team Perspective

Defenders must:
- Monitor incoming and outgoing traffic.
- Protect public-facing services.
- Use firewalls and IDS/IPS.
- Detect abnormal external connections.

## 1.2 Identifying Devices on a Network

Devices use two main identifiers: IP address and MAC address.

### IP Address (Internet Protocol)

#### What It Is

An IP address identifies a device on a network.

- IPv4 = 32-bit (2^32 ≈ 4.29 billion addresses)
- IPv6 = 128-bit (2^128 addresses)

Public IP → assigned by ISP  
Private IP → used inside local networks (e.g., 192.168.x.x)

IP addresses can be:
- Static (fixed)
- Dynamic (changes over time via DHCP)

#### How It Works

- Operates at Layer 3 (Network Layer).
- Allows routing between networks.
- Used to send packets from source to destination.

#### Why It Matters for Security

Attackers use IP addresses to:
- Scan networks
- Identify open ports
- Perform brute-force attacks
- Launch DDoS attacks

IP addresses can be monitored or blocked.

#### Blue Team Perspective

Look for:
- Multiple failed logins from a single IP
- Port scanning behavior
- Traffic from known malicious IP addresses

Useful log sources:
- Firewall logs
- Web server logs
- Authentication logs

### MAC Address (Media Access Control)

#### What It Is

A MAC address is a unique hardware identifier assigned to a network interface card (NIC).

- Operates at Layer 2 (Data Link Layer)
- Usually factory-assigned

#### Why It Matters for Security

MAC addresses are used:
- For communication within local networks
- For device identification in LAN environments

Risks:
- MAC spoofing allows device impersonation
- Can bypass weak network filtering

#### Blue Team Perspective

Monitor:
- Duplicate MAC addresses
- Unknown devices in the network
- Unexpected MAC address changes

Relevant sources:
- Switch logs
- ARP tables
- Network monitoring tools

## 1.3 Ping and ICMP

### What It Is

ICMP (Internet Control Message Protocol) is used for diagnostics and error reporting.

Ping uses:
- ICMP Echo Request
- ICMP Echo Reply

Command:

```bash
ping <IP address or domain>
## 2. Intro to LAN: