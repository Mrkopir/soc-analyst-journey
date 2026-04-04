# Nmap: Port Scanning & Detection - TryHackMe

## 1. Network Services

A network service is any process listening on a TCP or UDP port.

Common services:
- HTTP → TCP 80, 443  
- DNS → UDP/TCP 53  

Both TCP and UDP have **65,535 ports**.

## 2. TCP Scanning

### Connect Scan (-sT)

- Completes full TCP three-way handshake  
- Similar to telnet  

- Open port → connection established then closed (RST)  
- Closed port → RST response  

### SYN Scan (-sS)

- Sends only SYN packet  
- Does NOT complete handshake  

- Open port → SYN-ACK → Nmap sends RST  
- Closed port → RST  

- More stealthy (less logging)

## 3. UDP Scanning

UDP is connectionless (no handshake).

Common UDP services:
- DNS  
- DHCP  
- NTP  
- SNMP  
- VoIP  

Behavior:
- Closed port → ICMP "port unreachable"  
- Open port → often no response  

Option:
- `-sU`

## 4. Port Range Control

Default:
- Nmap scans 1000 most common ports  

Options:

- `-F` → fast scan (100 ports)  
- `-p1-1023` → well-known ports  
- `-p10-1024` → custom range  
- `-p-` → all ports (1–65535)  

## 5. OS Detection

Detects operating system based on network behavior.

Option:
- `-O`

Example:
- Linux 4.x / 5.x  

## 6. Service & Version Detection

Detects:
- service type  
- version  

Option:
- `-sV`

Example:
- OpenSSH 8.9p1  

## 7. Aggressive Scan

Combines multiple features:

- OS detection  
- Version detection  
- traceroute  

Option:
- `-A`

## 8. Force Scan

Skips host discovery.

- Scans hosts even if they don’t respond  

Option:
- `-Pn`

## 9. Timing Control

Controls scan speed:

- `-T0` → paranoid (very slow)  
- `-T1` → sneaky  
- `-T2` → polite  
- `-T3` → normal (default)  
- `-T4` → aggressive  
- `-T5` → insane  

## 10. Performance Options

- `--min-parallelism`  
- `--max-parallelism`  
- `--min-rate`  
- `--max-rate`  
- `--host-timeout`  

## 11. Verbosity & Debugging

- `-v` → verbose  
- `-vv / -v4` → more details  
- `-d` → debug  
- `-d9` → max debug  

## 12. Saving Results

- `-oN FILE` → normal output  
- `-oX FILE` → XML  
- `-oG FILE` → grepable  
- `-oA NAME` → all formats  