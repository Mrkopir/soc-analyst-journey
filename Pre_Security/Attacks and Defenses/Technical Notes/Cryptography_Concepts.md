# Cryptography Concepts - TryHackMe

## 1. Symmetric Encryption

### How it works:

- Encryption process: plaintext + encryption algorithm + key  → ciphertext

- Decryption process: ciphertext + decryptiong algorithm + key   → plaintext

### Some of the benefits of using symmetric encryption are:

- It's fast. Symmetric algorithms can churn through huge amounts of data really quickly.
- It's efficient. Perfect for encrypting files, hard drives, and network traffic where speed matters.


### Some of the disadvantages of symmetric encryption are:

- Key distribution problem. The same secret key must be securely shared between parties before communication begins. If the key is intercepted during distribution, the attacker can decrypt all messages.

- Scalability issues. In systems with many users, a large number of keys must be managed. For example, in a network with many participants, each pair may need a separate shared key.

- Single point of compromise. If the secret key is leaked or stolen, all encrypted data protected with that key becomes readable to an attacker.

- No built-in authentication. Basic symmetric encryption does not verify who sent the message. Additional mechanisms (like MAC or authenticated encryption) are required to ensure integrity and authenticity.

- Key management complexity. Keys must be securely generated, stored, rotated, and revoked, which can be difficult in large systems.

## 2. Asymmetric Encryption

### How it works:

Asymmetric encryption uses two mathematically linked keys:

- A public key that anyone can know and use.
- A private key that only one person keeps secret.

If you encrypt something with someone's public key, only their private key can decrypt it.
If you encrypt something with your private key, anyone with your public key can decrypt it (this is primarily used for digital signatures, which we won't delve into here).

### Real use: HTTPS

1. Your browser requests the website's public key.
2. The website sends back its public key wrapped in a certificate (more on this shortly).
3. Your browser and the website use asymmetric encryption to agree on a shared secret (a symmetric key) without anyone else being able to see it.
4. From there on, they switch to fast symmetric encryption using that shared secret for the rest of the session.
5. This combo is sometimes called a hybrid approach:

Asymmetric encryption solves the problem of key distribution.
Symmetric encryption handles the heavy lifting because it's way faster.

## 3. Symmetric vs Asymmetric
1. Number of keys:
- Symmetric: One key for both encrypting and decrypting	
- Asymmetric: Two keys: public and private
2. Key sharing	
- Symmetric: One key for both encrypting and decrypting	
- Asymmetric: Both people need the same secret key	
- Public key can be shared openly
3. Speed	
- Symmetric: One key for both encrypting and decrypting	
- Asymmetric: Very fast	
- Slower (used for small amounts of data)
4. Main use	
- Symmetric: Encrypting bulk data (files, network traffic)	
- Asymmetric: Sharing keys, securely and digital certificates
5. Analogy	
- Symmetric: One key locks and unlocks a box	
- Asymmetric: A mailbox: anyone posts, only the owner retrieves