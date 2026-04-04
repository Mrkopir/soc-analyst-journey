# Tcpdump: The Basics - TryHackMe

## 1. Packet Length Filtering

You can filter packets based on their size:

- `greater LENGTH` → packets ≥ specified length  
- `less LENGTH` → packets ≤ specified length  

## 2. Binary Operations

Binary operations work with bits (0 and 1).

### AND (&)

Returns 1 only if both bits are 1:

| Input1 | Input2 | Result |
|--------|--------|--------|
| 0      | 0      | 0      |
| 0      | 1      | 0      |
| 1      | 0      | 0      |
| 1      | 1      | 1      |

### OR (|)

Returns 1 if at least one bit is 1:

| Input1 | Input2 | Result |
|--------|--------|--------|
| 0      | 0      | 0      |
| 0      | 1      | 1      |
| 1      | 0      | 1      |
| 1      | 1      | 1      |

### NOT (!)

Inverts the bit:

| Input | Result |
|------|--------|
| 0    | 1      |
| 1    | 0      |

## 3. Header Byte Filtering

Syntax:

- `proto[expr:size]`

Where:
- `proto` → protocol (arp, ether, ip, tcp, udp)  
- `expr` → byte offset (0 = first byte)  
- `size` → number of bytes (default = 1)  

Examples:

- `ether[0] & 1 != 0` → multicast packets  
- `ip[0] & 0xf != 5` → IP packets with options  

## 4. TCP Flags Filtering

Use:

- `tcp[tcpflags]`

Available flags:

- `tcp-syn` → SYN  
- `tcp-ack` → ACK  
- `tcp-fin` → FIN  
- `tcp-rst` → RST  
- `tcp-push` → PUSH  

## 5. Examples

- Only SYN packets:
  - `tcpdump "tcp[tcpflags] == tcp-syn"`

- SYN flag present:
  - `tcpdump "tcp[tcpflags] & tcp-syn != 0"`

- SYN or ACK:
  - `tcpdump "tcp[tcpflags] & (tcp-syn|tcp-ack) != 0"`

## 6. Tcpdump Basics

- `-i INTERFACE` → choose interface  
- `-w FILE` → save packets  
- `-r FILE` → read from file  
- `-c COUNT` → limit number of packets  
- `-n` → no DNS resolution  
- `-nn` → no DNS and port resolution  
- `-v / -vv / -vvv` → verbosity levels :contentReference[oaicite:0]{index=0}  

## 7. Filtering Types

### By Host

- `host IP`  
- `src host IP`  
- `dst host IP`  

### By Port

- `port PORT`  
- `src port PORT`  
- `dst port PORT`  

### By Protocol

- `tcp`  
- `udp`  
- `icmp`  

## 8. Logical Operators

- `and` → both conditions  
- `or` → at least one  
- `not` → exclude condition  

Examples:

- `host 1.1.1.1 and tcp`  
- `udp or icmp`  
- `not tcp` :contentReference[oaicite:1]{index=1}  

## 9. Output Options

- `-q` → brief output  
- `-e` → show MAC addresses  
- `-A` → ASCII output  
- `-xx` → hex output  
- `-X` → hex + ASCII :contentReference[oaicite:2]{index=2}  