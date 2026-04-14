# Cryptography, Hashing & Password Attacks – Final Reflection (TryHackMe)

## Overview

During this learning path, I explored the fundamental concepts of cryptography, hashing, and password security. I learned how data is protected in modern systems, how encryption ensures confidentiality, and how hashing is used for integrity and authentication.

This knowledge is essential in cybersecurity because almost every system relies on cryptographic mechanisms — from secure web connections to password storage and secure communication protocols.

Understanding these concepts gives a strong foundation for both defensive security (protecting systems) and offensive security (identifying weaknesses).

## Technical Understanding

One of the key concepts I learned is the difference between symmetric and asymmetric encryption.

Symmetric encryption uses a single key for both encryption and decryption, which makes it fast but introduces challenges in secure key distribution. Algorithms like AES are widely used in real-world systems.

Asymmetric encryption uses a pair of keys (public and private), solving the key distribution problem. I learned about RSA and Diffie-Hellman, which are used for secure key exchange and communication. However, they are slower, so they are typically used only during the initial handshake, after which symmetric encryption is used.

I also understood how protocols like SSH and TLS combine both approaches to achieve security and performance.

Another important topic was hashing. Unlike encryption, hashing is one-way and cannot be reversed. I learned the properties of secure hash functions, such as determinism, fixed output length, and resistance to collisions.

I explored different hashing algorithms like MD5, SHA-1, and SHA-256, and understood why older algorithms are no longer secure.

A key practical concept was secure password storage. Instead of storing passwords directly, systems store hashes combined with salts. I learned how salting prevents rainbow table attacks and why modern algorithms like bcrypt, scrypt, and Argon2 are preferred.

I also studied how hashes are stored in Linux (`/etc/shadow`) and Windows (SAM database), which is important for both system administration and penetration testing.

Another major part was password cracking. I learned how tools like John the Ripper and Hashcat work by generating candidate passwords and comparing hashes.

Different attack methods include:
- dictionary attacks  
- brute force attacks  
- rule-based attacks  
- hybrid attacks  

I also learned about optimizations such as GPU acceleration and word mangling techniques.

Additionally, I explored how tools like `unshadow`, `zip2john`, `rar2john`, and `ssh2john` are used to extract hashes from different sources.

## Security Perspective

From a security perspective, this learning path clearly shows how critical proper implementation of cryptography is.

Weak hashing algorithms, lack of salting, or poor password policies can lead to serious breaches. Even if encryption is used, incorrect implementation can completely break security.

I also understood that attackers do not usually "decrypt" passwords — they crack them by guessing and comparing hashes. This highlights the importance of strong passwords and computationally expensive hashing algorithms.

Another important insight is that cryptography is not only about confidentiality, but also about integrity and authenticity. Digital signatures and certificates ensure that data is not modified and that communication is trusted.

Tools like John the Ripper demonstrate how attackers think, which is extremely useful for building defensive strategies.

## Conclusion

This learning path significantly improved my understanding of how data is protected and attacked in real-world systems.

I now understand how encryption works, how keys are exchanged, how passwords should be stored securely, and how attackers attempt to break weak implementations.

These concepts are directly relevant to cybersecurity roles, especially in SOC analysis, penetration testing, and incident response.

Overall, this course gave me both theoretical knowledge and practical insight into cryptography and password security, which are fundamental skills for any cybersecurity specialist.