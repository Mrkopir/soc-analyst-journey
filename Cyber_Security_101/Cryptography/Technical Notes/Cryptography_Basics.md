# Cryptography Basics - TryHackMe

## 1. Introduction  

Cryptography is the practice and study of techniques used to secure communication in the presence of adversaries. Its main goals are confidentiality, integrity, and authenticity of data.

It is widely used in everyday scenarios such as logging into websites, SSH connections, online banking, and verifying file integrity using hashes.

Organizations handling sensitive data must follow standards such as PCI DSS, HIPAA, GDPR, and others, which require encryption both at rest and in transit.

## 2. Importance of Cryptography  

Cryptography ensures that attackers cannot read or modify data during transmission or storage.

Examples:
- Secure login credentials transmission  
- Encrypted communication (SSH, HTTPS)  
- Certificate validation for identity verification  
- File integrity verification using hash functions  

It is essential in protecting sensitive data like financial and medical records.

## 3. Plaintext to Ciphertext  

Plaintext is the original readable data.

Ciphertext is the encrypted unreadable version of that data.

A cipher is an algorithm used to convert plaintext into ciphertext.

A key is a secret value used in encryption and decryption.

Encryption converts plaintext into ciphertext using a key and cipher.

Decryption converts ciphertext back into plaintext using the same or corresponding key.

Without the key, recovering plaintext should be infeasible.

## 4. Historical Ciphers  

One of the simplest historical ciphers is the Caesar Cipher.

It works by shifting letters by a fixed number.

Example:
- Plaintext: TRYHACKME  
- Key: 3  
- Ciphertext: WUBKDFNPH  

It is insecure because there are only 25 possible keys, making brute force trivial.

## 5. Types of Encryption  

### Symmetric Encryption  

Uses the same key for encryption and decryption.

Problems:
- Key distribution is difficult  
- Requires secure channel  

Examples:
- DES (56-bit, insecure)  
- 3DES (deprecated)  
- AES (modern standard, 128/192/256-bit)  

### Asymmetric Encryption  

Uses two keys:
- Public key (encryption)  
- Private key (decryption)  

Advantages:
- No need to share secret key  

Disadvantages:
- Slower than symmetric  

Examples:
- RSA  
- Diffie-Hellman  
- ECC  

## 6. Basic Math  

### XOR Operation  

XOR compares two bits:
- Same → 0  
- Different → 1  

Properties:
- A ⊕ A = 0  
- A ⊕ 0 = A  
- Commutative and associative  

Used in simple encryption:
- C = P ⊕ K  
- P = C ⊕ K  

### Modulo Operation  

Modulo (%) returns the remainder of division.

Examples:
- 25 % 5 = 0  
- 23 % 6 = 5  
- 23 % 7 = 2  

Important:
- Result is always between 0 and n-1  
- Not reversible (many values satisfy same result)  

Used in cryptographic algorithms with large numbers.