# Public Key Cryptography Basics - TryHackMe

# Cryptography – TryHackMe

## 1. Introduction

Cryptography is the practice of securing communication and protecting data in the presence of adversaries. Its primary goals are confidentiality, integrity, and authenticity.

It ensures that sensitive information cannot be read or modified by unauthorized parties. Cryptography is widely used in modern digital systems, including secure web connections, authentication systems, encrypted communication channels, and data protection.

Modern cryptographic systems rely on mathematical algorithms and cryptographic keys to encrypt and decrypt data securely.

## 2. Common Use of Asymmetric Encryption

Asymmetric encryption is commonly used to securely exchange symmetric encryption keys.

Since asymmetric algorithms are computationally slower, they are typically used only during the initial communication phase. After securely exchanging a symmetric key, the communication continues using faster symmetric encryption.

This approach combines the security benefits of asymmetric cryptography with the efficiency of symmetric encryption and is widely used in secure protocols such as TLS.

## 3. RSA

RSA is a widely used public-key cryptographic algorithm designed to enable secure communication over insecure networks.

It relies on two keys:
- a public key used for encryption
- a private key used for decryption

The security of RSA is based on the mathematical difficulty of factoring very large numbers that are the product of two prime numbers. While multiplying large primes is computationally easy, determining the original prime numbers from their product is extremely difficult.

Because of this property, RSA can safely expose the public key while keeping the private key secret.

RSA is commonly used for secure key exchange, digital signatures, and secure communication protocols.

## 4. Diffie-Hellman Key Exchange

Diffie-Hellman is a cryptographic method used to securely establish a shared secret between two parties over an insecure communication channel.

It allows both parties to generate a common encryption key without directly transmitting that key across the network. Even if an attacker observes the communication, they cannot derive the shared secret.

The generated shared secret is typically used as a symmetric encryption key for securing further communication.

Diffie-Hellman is widely used in secure protocols such as TLS, SSH, and VPN technologies.

## 5. SSH

SSH (Secure Shell) is a cryptographic network protocol used for secure remote access to systems.

It provides encrypted communication between a client and a server, protecting authentication credentials and session data from interception.

SSH supports multiple authentication methods, including password authentication and public-key authentication. Public-key authentication is considered more secure because it uses asymmetric cryptography instead of transmitting passwords.

In addition to remote shell access, SSH can also be used for secure file transfers and encrypted tunneling.

## 6. Digital Signatures and Certificates

Digital signatures are cryptographic mechanisms used to verify the authenticity and integrity of data.

They are created using a private key and can be verified using the corresponding public key. If the signature is valid, it proves that the data has not been altered and confirms the identity of the sender.

Digital certificates are used to associate a public key with the identity of an organization or individual. Certificates are issued and verified by trusted Certificate Authorities (CAs).

Certificates play a crucial role in secure communication protocols such as HTTPS, where they allow users to verify that they are communicating with legitimate servers.

## 7. PGP and GPG

PGP (Pretty Good Privacy) is a cryptographic system used to encrypt and sign data, primarily for securing email communication.

It combines symmetric encryption, asymmetric encryption, and hashing to provide confidentiality, integrity, and authentication.

GPG (GNU Privacy Guard) is an open-source implementation of the OpenPGP standard and provides similar functionality to PGP.

These tools allow users to encrypt files, secure emails, and digitally sign messages to verify authenticity.