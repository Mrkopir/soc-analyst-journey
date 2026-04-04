# Networking Fundamentals – Final Reflection (TryHackMe)

## Overview

During the *Networking Fundamentals* learning path, I gained a comprehensive understanding of how computer networks operate, how data is transmitted, and how different protocols interact with each other. I explored core networking models, protocols, and tools used for communication, monitoring, and security analysis.

This knowledge is essential in cybersecurity, as networks are the primary medium through which attacks occur, and understanding them allows effective detection, analysis, and response.

## Technical Understanding

I began by studying the OSI model, which consists of seven layers that describe how data moves through a network, from physical transmission to application-level interaction. I also explored the TCP/IP model, which simplifies these layers into four main categories and is used in real-world networking.

I learned about IP addressing and subnetting, including the structure of IPv4 addresses and private address ranges defined by RFC 1918. This knowledge is crucial for identifying internal networks and understanding how devices communicate.

Transport protocols were another important topic. I studied TCP, which is connection-oriented and ensures reliable data delivery, and UDP, which is faster but does not guarantee delivery. Understanding their differences is essential when analyzing network traffic.

Encapsulation was introduced as the process of wrapping data with headers at each layer, forming segments, packets, and frames. This concept is critical for understanding how data travels across networks.

I explored core network protocols such as DNS, HTTP/HTTPS, FTP, SMTP, POP3, and IMAP. These protocols define how data is exchanged between systems and operate on specific ports. I also learned how tools like `nslookup` and `whois` are used for information gathering.

In networking essentials, I studied DHCP and its DORA process, ARP for resolving IP to MAC addresses, ICMP for diagnostics using tools like `ping` and `traceroute`, and NAT for enabling multiple devices to share a single public IP address.

Security-focused topics included TLS and HTTPS, which provide encryption and secure communication. I learned how TLS certificates work and how secure protocols replace insecure ones to protect data in transit.

I also explored SSH for secure remote access, SFTP and FTPS for secure file transfer, and VPNs for creating encrypted tunnels over the internet.

A significant part of the course focused on network scanning and analysis using Nmap. I learned different scan types such as SYN scan (`-sS`), TCP connect scan (`-sT`), and UDP scan (`-sU`), as well as techniques for detecting operating systems, services, and versions.

Traffic analysis tools were also covered. Tcpdump allows capturing and filtering packets using advanced expressions and logical operators, while Wireshark provides a graphical interface for deep packet inspection, protocol analysis, and stream reconstruction.

## Security Perspective

From a security perspective, networking knowledge is fundamental. Understanding how protocols work allows detection of anomalies, misconfigurations, and malicious activity.

Tools like Nmap can be used to identify open ports and services, which helps in both penetration testing and defensive assessments. Packet analysis tools like tcpdump and Wireshark enable detailed inspection of traffic, allowing analysts to detect suspicious behavior, data exfiltration, or protocol misuse.

Encryption protocols such as TLS protect sensitive data, but also require understanding to identify potential weaknesses or misconfigurations. Similarly, protocols like ARP and ICMP can be abused in attacks such as spoofing or network reconnaissance.

Overall, networking forms the backbone of cybersecurity operations, especially in SOC environments where monitoring and analyzing traffic is a daily task.

## Conclusion

This learning path provided a strong foundation in networking concepts, protocols, and tools. I developed practical skills in understanding network communication, analyzing traffic, and using tools for scanning and troubleshooting.

These skills are essential for cybersecurity professionals, particularly SOC analysts, where network visibility, threat detection, and incident response are critical.

Overall, this course significantly improved my understanding of networking and prepared me for more advanced topics in cybersecurity.