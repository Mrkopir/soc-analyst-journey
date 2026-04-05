# Hashing Basics - TryHackMe

## Introduction

Hashing is a cryptographic technique used to transform data of any size into a fixed-size value called a **hash** or **digest**. It is widely used in cybersecurity for protecting data integrity and supporting authentication systems.

Unlike encryption, hashing is designed to be **one-way**. This means that it should be computationally infeasible to determine the original input from the hash value.

Hashing is commonly used in many security mechanisms such as password verification, file integrity checking, and message authentication.

## Hash Functions

A **hash function** is an algorithm that takes input data of any size and produces a fixed-length output.

Key characteristics of hash functions:

- deterministic (the same input always produces the same hash)
- fixed-length output
- fast to compute
- difficult to reverse
- small changes in input produce large changes in output (avalanche effect)
- resistant to collisions

Common hashing algorithms include:

- MD5
- SHA-1
- SHA-256
- SHA-512

Hash outputs are typically encoded using:

- hexadecimal
- base64

A **hash collision** occurs when two different inputs produce the same hash output. Because the number of possible inputs is extremely large while the number of hash outputs is limited, collisions are theoretically unavoidable. Secure hashing algorithms are designed to make finding collisions extremely difficult.

Older algorithms such as **MD5** and **SHA-1** are now considered insecure because practical collision attacks have been demonstrated.

## Insecure Password Storage for Authentication

Poor password storage practices can lead to major security breaches.

Common insecure methods include:

Storing passwords in plaintext

- passwords are stored directly in the database
- if the database is leaked, attackers immediately obtain user passwords

Using deprecated encryption

- passwords are stored using reversible encryption
- if the encryption key is compromised, attackers can decrypt all stored passwords

Using insecure hashing algorithms

- weak algorithms such as SHA-1 or MD5
- lack of additional protections like salting
- easier for attackers to crack using precomputed databases

Real-world breaches have occurred due to these insecure practices, exposing millions of user passwords.

## Using Hashing for Secure Password Storage

Secure password storage relies on strong hashing algorithms combined with **salting**.

A **salt** is a randomly generated value added to a password before hashing.

Secure password storage process:

1. Generate a unique random salt.
2. Combine the password with the salt.
3. Compute the hash using a secure hashing algorithm.
4. Store both the hash and the salt in the database.

Benefits of salting:

- prevents rainbow table attacks
- identical passwords generate different hashes
- increases difficulty of password cracking

Recommended password hashing algorithms include:

- Argon2
- bcrypt
- scrypt
- PBKDF2

These algorithms are designed to be computationally expensive, which slows down brute-force attacks.

## Recognising Password Hashes

In cybersecurity and penetration testing, it is often necessary to identify the type of hash being used.

Hash identification can be based on:

- hash length
- encoding format
- known prefixes
- context of the application

Automated tools can help identify hash types, but they are not always reliable.

Examples of identification tools:

- hashID
- Hashcat example hash database

On Linux systems, password hashes are stored in:

/etc/shadow

Each entry contains several fields separated by colons. The password field usually has the format:

$prefix$options$salt$hash

Common prefixes include:

- $y$ — yescrypt
- $7$ — scrypt
- $2b$ — bcrypt
- $6$ — SHA-512 crypt
- $1$ — MD5 crypt

On Windows systems, password hashes are stored in the **Security Accounts Manager (SAM)** database.

Common Windows hash types include:

- LM hash
- NT hash (NTLM)

## Password Cracking

Password cracking involves attempting to determine the original password by generating hashes from candidate inputs and comparing them to a target hash.

This process does not decrypt the hash but instead searches for matching inputs.

Common password cracking techniques:

- dictionary attacks
- brute force attacks
- rule-based attacks
- hybrid attacks

Common password cracking tools:

- Hashcat
- John the Ripper

Wordlists are frequently used during cracking attempts. One of the most common wordlists is:

rockyou.txt

Modern GPUs significantly accelerate password cracking because they can perform many hashing operations in parallel.

Some hashing algorithms are intentionally designed to resist GPU-based attacks by requiring high computational resources.

## Hashing for Integrity Checking

Hashing is widely used to verify that data has not been modified.

If the same input data is processed through a hash function, it will always produce the same output hash. Even a single bit change in the input results in a completely different hash.

Integrity verification process:

1. Calculate the hash of the original file.
2. Publish the hash alongside the file.
3. After downloading, compute the hash again.
4. Compare both hash values.

If the hashes match, the file is considered unchanged and authentic.

Hashing can also be used to detect duplicate files since identical files produce identical hash values.

A related concept is **HMAC (Hash-based Message Authentication Code)**.

HMAC combines a cryptographic hash function with a secret key to ensure both:

- data integrity
- message authenticity

It allows the receiver to verify that the message was created by someone who possesses the secret key and that the data has not been altered.
