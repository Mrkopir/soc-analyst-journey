# Intro_to_LAN – TryHackMe

## 1. LAN Topologies

### What is it:
    A Local Area Network (LAN) is a private, high-speed network that connects computers, servers, printers, and other devices within a limited physical area, such as a home, office, or building

### Topologies:
    - Star Topology: devices are individually connected via a central networking device such as a switch or hub.
    - Bus Topology: every device connected by the main cable to other device. When one device isn't runing devices will be connected normaly 
    - Ring Topology: devices are connected directly to each other to form a loop, meaning that there is little cabling required andless dependence on dedicated hardware such as within a star topology.

## 2. Hub vs Switch vs Router 

### **Hub**:
- Broadcasts traffic to all devices
- Less secure
- No traffic filtering

### **Switch**:
- Sends traffic only to intended device
- More efficient
- Reduces sniffing risk

### **Router**:
- Sends traffic bettwen networks

## 3 Subnetting

### What is it:

Subnetting is the process of dividing a large network into smaller logical networks (subnets).

### **It improves:**
- Network organization
- Performance
- Security
- Traffic management

### **Subnets use IP addresses in three different ways:**
- Identify the network address
- Identify the host address
- Identify the default gateway

## 3.1 Subnet Mask

A subnet mask defines how many bits belong to the network.

### **Example:**

IP:        192.168.1.10  
Mask:      255.255.255.0  
CIDR:      /24

255.255.255.0 = 24 network bits

### **Common subnet masks:**

- /8  → 255.0.0.0
- /16 → 255.255.0.0
- /24 → 255.255.255.0
- /25 → 255.255.255.128
- /26 → 255.255.255.192
- /27 → 255.255.255.224
- /28 → 255.255.255.240

## 4. ARP (Address Resolution Protocol)

### What is it:

ARP allows a device to associate its MAC address with an IP address on the network. Each device on a network will keep a log of the MAC addresses associated with other devices.
When devices wish to communicate with another, they will send a broadcast to the entire network searching for the specific device. Devices can use ARP to find the MAC address (and therefore the physical identifier) of a device for communication.

### How does ARP Work:
Each device within a network has a ledger to store information on, which is called a cache. In the context of ARP, this cache stores the identifiers of other devices on the network. When an ARP request is sent, a message is broadcasted on the network to other devices asking, "What is the mac address that owns this IP address?" When the other devices receive that message, they will only respond if they own that IP address and will send an ARP reply with its MAC address. The requesting device can now remember this mapping and store it in its ARP cache for future use.
- ARP REQUEST
- ARP REPLY

## 5. DHCP (Dynamic Host Configuration Protocol)

### What is it:

IP addresses can be assigned either manually, by entering them physically into a device, or automatically and most commonly by using a DHCP

### How does DHCP Work:
When a device connects to a network, if it has not already been manually assigned an IP address, it sends out a request (DHCP Discover) to see if any DHCP servers are on the network. The DHCP server then replies back with an IP address the device could use (DHCP Offer). The device then sends a reply confirming it wants the offered IP Address (DHCP Request), and then lastly, the DHCP server sends a reply acknowledging this has been completed, and the device can start using the IP Address (DHCP ACK).