# Operating System Security - TryHackMe

## 1. Authentication and Weak Passwords

Authentication is the act of verifying your identity, be it a local or a remote system. Authentication can be achieved via three main ways:

- Something you know, such as a password or a PIN code. (Passwords are the most common form of authentication, they are also the most attacked.)
- Something you are, such as a fingerprint.
- Something you have, such as a phone number via which you can receive an SMS message.


## 2. Weak File Permissions
Proper security dictates the principle of least privilege. In a work environment, you want any file accessible only by those who need to access it to get work done. Weak file permissions make it easy for the adversary to attack confidentiality and integrity. They can attack confidentiality as weak permissions allow them to access files they should not be able to access. Moreover, they can attack integrity as they might modify files that they should not be able to edit.

## 3. Access to Malicious Programs
Some types of malicious programs, such as Trojan horses, give the attacker access to your system. Consequently, the attacker would be able to read your files or even modify them. Some types of malicious programs attack availability. One such example is ransomware. Ransomware is a malicious program that encrypts the user's files. Encryption makes the file(s) unreadable without knowing the encryption password; in other words, the files become gibberish without decryption (reversing the encryption). The attacker offers the user the ability to restore availability, i.e., regain access to their original files: they would give them the encryption password if the user is willing to pay the “ransom.”