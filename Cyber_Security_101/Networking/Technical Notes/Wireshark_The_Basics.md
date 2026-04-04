# Wireshark: The Basics - TryHackMe

## 1. Use Cases

Wireshark is a traffic analyser used for:

- Detecting and troubleshooting network problems (failures, congestion)
- Detecting security anomalies (rogue hosts, abnormal ports, suspicious traffic)
- Investigating protocols (response codes, payloads)

Note:
- Not an IDS
- Does not modify packets
- Only reads traffic

## 2. GUI Overview

Main sections:

- **Toolbar** - menus for sniffing, filtering, exporting, merging  
- **Display Filter Bar** - main filtering/query section  
- **Recent Files** - previously opened pcaps  
- **Capture Interfaces** - network interfaces (lo, eth0, ens33)  
- **Status Bar** - tool status and packet info  

## 3. Loading PCAP Files

Ways to load:
- File menu  
- Drag & drop  
- Double-click  

## 4. Packet View (3 Panes)

- **Packet List Pane**: summary (source, destination, protocol)  
- **Packet Details Pane**: protocol breakdown  
- **Packet Bytes Pane**: hex + ASCII view  

## 5. Packet Colouring

Types:
- Temporary: session only  
- Permanent: saved in profile  

Used to:
- Identify protocols quickly  
- Spot anomalies  

## 6. Traffic Sniffing

- Blue button → start  
- Red button → stop  
- Green button → restart  

## 7. Merge PCAP Files

- File: Merge  
- Combines multiple pcaps into one  

## 8. File Details

Available info:
- File hash  
- Capture time  
- Interface  
- Statistics  

Path:
- Statistics: Capture File Properties  

## 9. Packet Dissection

Wireshark breaks packets into layers:

- Frame (Layer 1)  
- MAC (Layer 2)  
- IP (Layer 3)  
- Transport (Layer 4)  
- Protocol errors  
- Application protocol (Layer 5)  
- Application data  

## 10. Packet Navigation

- Packet numbers → unique IDs  
- Go to packet → navigate quickly  
- Find packet → search by:
  - Display filter  
  - Hex  
  - String  
  - Regex :contentReference[oaicite:0]{index=0}  

## 11. Packet Tools

- Mark packets: highlight packets  
- Packet comments: add notes  
- Export packets: save selected packets  
- Export objects: extract files (HTTP, SMB, etc.)  

## 12. Time Format

Default:
- Seconds since capture  

Can change to:
- UTC time 

## 13. Expert Info

Severity levels:

- Blue: chat  
- Cyan: note  
- Yellow: warning  
- Red: error  

Examples:
- Malformed packets  
- Checksum errors :contentReference[oaicite:1]{index=1}  

## 14. Filtering

Types:
- Capture filters  
- Display filters  

Basic filters:

- Protocol:
  - `http`
  - `dns`

- Port:
  - `tcp.port == 80`

- IP:
  - `ip.addr == 192.168.1.1` :contentReference[oaicite:2]{index=2}  

## 15. Filtering Features

- Apply as Filter  
- Conversation Filter  
- Colourise Conversation  
- Prepare as Filter  
- Apply as Column  

## 16. Streams

- Follow TCP/UDP/HTTP Stream  
- Shows full communication  
- Client: red  
- Server: blue  