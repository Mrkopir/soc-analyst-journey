# John the Ripper - TryHackMe

## Introduction

Password cracking is an important process in cybersecurity, particularly during penetration testing and security assessments. Many systems do not store passwords in plaintext form. Instead, they store hashed versions of passwords. If an attacker gains access to these hashes, they may attempt to recover the original passwords.

Hash cracking tools attempt to discover the original password by generating possible password guesses, hashing them with the same algorithm, and comparing the results with the target hash. If the hashes match, the correct password has been found.

One of the most widely used tools for this purpose is John the Ripper. It is a fast and flexible password cracking tool that supports many different hash types and attack methods. It is commonly used in penetration testing, red team operations, and cybersecurity training environments.

## Basic Terms

Hash functions are designed to be one-way functions. This means that it is easy to calculate the hash value of an input, but extremely difficult to determine the original input from the hash.

This concept is related to the well-known problem in computer science called P vs NP. These two classes describe the complexity of computational problems.

P (Polynomial Time) refers to problems that can be solved efficiently by an algorithm. The time required to solve the problem increases at a manageable rate as the size of the input increases.

NP (Non-deterministic Polynomial Time) refers to problems where verifying a solution is easy, but finding the solution itself may be extremely difficult.

Hash functions fit into this concept because calculating a hash is computationally simple, but reversing it would require solving a complex problem that is considered computationally infeasible.

Although hashes cannot normally be reversed, attackers can attempt to guess the original password. By hashing many possible passwords and comparing them with the target hash, it may be possible to discover the correct password. This method is commonly called a dictionary attack.

## Setting Up Your System

John the Ripper is available on many operating systems and is commonly included in penetration testing distributions such as Kali Linux.

The basic command syntax for John the Ripper is:

john [options] [file]

The command launches the tool, the options define how the cracking process will work, and the file contains the hashes that need to be cracked.

John can automatically detect some hash formats and apply the appropriate cracking method. In cases where the hash type cannot be automatically identified, the format may need to be specified manually.

## Cracking Basic Hashes

John the Ripper supports several modes for cracking hashes. One of the most common methods is using a wordlist attack. In this method, John attempts passwords from a predefined list and compares their hashes to the target hash.

If the hash format is known, it can be specified using the format option so that John applies the correct algorithm during the cracking process.

John also allows users to list all supported formats and select the most appropriate one for a particular hash type.

## Cracking Windows Authentication Hashes

Windows operating systems store password hashes using the NTHash format, commonly referred to as NTLM. These hashes represent user passwords and are stored in the Security Account Manager database.

In enterprise environments, password hashes can also be stored within the Active Directory database file called NTDS.dit.

Security professionals or attackers may obtain these hashes using specialized tools or by accessing system files with administrative privileges. Once obtained, the hashes may be cracked using password cracking tools.

However, in some cases attackers do not need to recover the original password. Techniques such as pass-the-hash allow authentication using the hash itself without knowing the plaintext password.

## Cracking /etc/shadow Hashes

In Linux systems, password hashes are stored in the /etc/shadow file. This file contains encrypted password hashes along with other account information such as password expiration details.

The /etc/shadow file is normally accessible only to the root user. Because of this restriction, administrative privileges are required to retrieve password hashes from the system.

To crack these hashes using John the Ripper, the /etc/shadow file must be combined with the /etc/passwd file. This is done using a tool called unshadow, which prepares the data in a format that John can process.

Once the files are combined, John can attempt to recover passwords using various cracking methods.

## Single Crack Mode

Single Crack Mode is a special attack method in John the Ripper that attempts to generate password guesses using information about the user account.

Instead of relying only on a predefined wordlist, John analyzes available information such as usernames and other account details to generate possible passwords.

This technique is known as word mangling. It modifies existing words by changing letter cases, adding numbers, or appending symbols.

Single Crack Mode can also use information from the GECOS field in Unix systems. This field may contain personal information such as the user's full name or other details that can help generate additional password guesses.

By using this contextual information, John can sometimes discover weak passwords more efficiently.

## Custom Rules

John the Ripper allows users to create custom password mutation rules that define how words should be modified during cracking attempts.

These rules are defined in the john.conf configuration file. Custom rules allow attackers or security professionals to generate password variations that follow common password creation patterns.

Many organizations enforce password complexity rules that require combinations of uppercase letters, lowercase letters, numbers, and symbols. However, users often create predictable patterns when constructing such passwords.

Custom rules can exploit these predictable patterns by automatically modifying words in a way that mimics typical user behavior.

This capability significantly increases the effectiveness of password cracking attacks.

## Cracking Password Protected Zip Files

John the Ripper can also be used to crack passwords protecting ZIP archives. Before the cracking process can begin, the archive must be converted into a hash format that John can understand.

This conversion is performed using a tool called zip2john. The tool extracts the necessary information from the archive and stores it in a format suitable for password cracking.

Once the hash has been extracted, John can attempt to recover the password using its normal cracking techniques.

## Cracking Password-Protected RAR Archives

The process of cracking RAR archive passwords is similar to cracking ZIP files. A tool called rar2john is used to extract the password hash from the RAR archive.

After the hash has been extracted, John the Ripper can attempt to crack the password using wordlists, rules, or other attack methods.

This technique is often used in security testing and capture-the-flag challenges when encrypted archive files are discovered during an investigation.

## Cracking SSH Keys with John

SSH private keys can be protected with a password to prevent unauthorized access. If an attacker obtains a password-protected private key file, they may attempt to recover the password.

Before cracking can begin, the SSH key must be converted into a format compatible with John the Ripper. This is done using a tool called ssh2john.

The tool extracts the hash associated with the key's password protection. Once the hash is obtained, John can attempt to crack the password using its standard cracking techniques.

If the password protecting the SSH key is weak, it may be recovered using dictionary attacks or rule-based attacks.