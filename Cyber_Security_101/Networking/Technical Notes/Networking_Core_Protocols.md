# Networking Core Protocols - TryHackMe

## 1. DNS

Domain Name System (DNS) is responsible for mapping domain names to IP addresses. It works at the Application Layer (Layer 7 of the OSI model).

DNS uses:
- UDP port 53 (default)
- TCP port 53 (fallback)

Common DNS records:

- **A Record**: Maps a domain to an IPv4 address  
- **AAAA Record**: Maps a domain to an IPv6 address  
- **CNAME Record**: Maps one domain to another domain  
- **MX Record**: Specifies the mail server for a domain  

Tools:
- `nslookup` – used to resolve domain names to IP addresses

## 2. WHOIS

WHOIS provides information about the owner of a domain.

It includes:
- Name
- Email
- Phone number
- Address
- Registration and update dates

This information is public unless privacy protection is enabled.

Command:
- `whois domain.com`

## 3. HTTP / HTTPS

HTTP (Hypertext Transfer Protocol) is used for communication between a client (browser) and a web server.

HTTPS is the secure version of HTTP.

Ports:
- HTTP: TCP 80  
- HTTPS: TCP 443  

Common methods:

- **GET** – retrieve data  
- **POST** – send data  
- **PUT** – update or create data  
- **DELETE** – remove data  

## 4. FTP

File Transfer Protocol (FTP) is used to transfer files between client and server.

Port:
- TCP 21  

Common commands:

- `USER` – username  
- `PASS` – password  
- `RETR` – download file  
- `STOR` – upload file  

FTP uses a separate connection for data transfer.

## 5. SMTP

Simple Mail Transfer Protocol (SMTP) is used to send emails.

Port:
- TCP 25  

Common commands:

- `HELO / EHLO` – start session  
- `MAIL FROM` – sender  
- `RCPT TO` – recipient  
- `DATA` – message content  

## 6. POP3

Post Office Protocol v3 (POP3) is used to retrieve emails from a server.

Port:
- TCP 110  

Common commands:

- `USER` – username  
- `PASS` – password  
- `STAT` – message count  
- `LIST` – list messages  
- `RETR` – retrieve message  
- `DELE` – delete message  

POP3 downloads emails and often removes them from the server.

## 7. IMAP

Internet Message Access Protocol (IMAP) is used to access and synchronize emails across multiple devices.

Port:
- TCP 143  

Features:

- Keeps emails on the server  
- Synchronizes across devices  
- Supports folders and message management  

Common commands:

- `LOGIN` – authenticate  
- `SELECT` – choose mailbox  
- `FETCH` – retrieve message  
- `MOVE` / `COPY` – manage messages  
- `LOGOUT` – end session  