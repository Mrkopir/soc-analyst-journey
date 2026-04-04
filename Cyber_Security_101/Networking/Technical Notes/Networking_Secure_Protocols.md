# Networking Secure Protocols - TryHackMe

## 1. TLS / SSL

TLS (Transport Layer Security) is a protocol that provides secure communication over a network. It ensures confidentiality and integrity of data.

History:
- SSL: deprecated  
- TLS: modern (current version: TLS 1.3)  

TLS operates at the Transport Layer and is used to secure other protocols.

Examples:
- HTTP: HTTPS  
- DNS: DoT  
- SMTP: SMTPS  

## 2. HTTPS (HTTP over TLS)

HTTPS is HTTP secured with TLS encryption.

Steps:
1. TCP handshake  
2. TLS handshake  
3. Encrypted HTTP communication  

Ports:
- HTTP: TCP 80  
- HTTPS: TCP 443  

Important:
- HTTP: plaintext (readable)  
- HTTPS: encrypted (only "Application Data" is visible)

## 3. TLS Certificates

TLS requires a digital certificate to verify identity.

Process:
1. Server creates a CSR (Certificate Signing Request)  
2. Sends it to a CA (Certificate Authority)  
3. CA signs the certificate  
4. Client verifies it  

Certificates act like a trusted digital identity.

## 4. Encrypted Traffic

Without TLS:
- Traffic is readable (credentials can be captured)

With TLS:
- Traffic is encrypted  
- Data appears as unreadable content  

## 5. Secure Protocols

Insecure protocols:
- HTTP: TCP 80  
- SMTP: TCP 25  
- POP3: TCP 110  
- IMAP: TCP 143  

Secure versions (using TLS):
- HTTPS: TCP 443  
- SMTPS: TCP 465 / 587  
- POP3S: TCP 995  
- IMAPS: TCP 993  

## 6. SSH

SSH (Secure Shell) is used for secure remote access.

Port:
- TCP 22  

Features:
- Encryption  
- Authentication (password or key-based)  
- Integrity  
- Tunneling  

Command:
- `ssh user@host`  

## 7. SFTP / FTPS

SFTP:
- Uses SSH  
- Port: TCP 22  
- Secure and simple  

FTPS:
- FTP secured with TLS  
- Port: TCP 990  
- Requires certificates  

## 8. VPN

VPN (Virtual Private Network) creates a secure tunnel over the Internet.

Purpose:
- Encrypt traffic  
- Hide real IP address  
- Access private networks  

How it works:
- Client encrypts data → sends through tunnel → server decrypts  

Effects:
- Appears as if accessing from another location  
- ISP sees only encrypted traffic  