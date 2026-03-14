# Become a Hacker - TryHackMe

## What is it?
Offensive Security focuses on proactively testing systems by attempting to break into them, with the goal of identifying weaknesses before real attackers can exploit them.

The purpose isn’t to cause damage; it’s to test the strength of security controls and defenses, uncover gaps, and help teams improve their overall security posture.

## Core Offensive Security Terms
- Red Teaming: A structured, authorized attack methodology that simulates a real adversary to test the effectiveness of defenses and find vulnerabilities within a defined scope
- Penetration Test: A structured security assessment where an authorized tester attempts to identify and exploit vulnerabilities within a defined scope to understand real-world risk
- Vulnerability: A weakness or flaw in a system, application, or configuration that an attacker could abuse
- Exploit: A technique or method used to take advantage of a vulnerability to achieve a specific outcome, such as accessing restricted functionality or data
- Scope: The boundaries of what is allowed to be tested during an engagement. Scope defines which systems, applications, and actions are permitted, and what is off-limits

# Finding Weaknesses:

## Using Automated Tool to find Weaknesses (Gobuster)

Example:
`gobuster dir --url http://www.onlineshop.thm/ -w /usr/share/wordlists/dirbuster/directory-list.txt`

The command above is made up of the following parts:

- `gobuster` - The command-line tool used to perform the discovery of web content
- `dir` - Specifies the directory and file enumeration mode, which attempts to discover hidden directories and files on a web server
- `--url`- http://www.onlineshop.thm/ Sets the target website that Gobuster will scan
- `-w` - /usr/share/wordlists/dirbuster/directory-list.txt Specifies the wordlist Gobuster will use to guess directory and file names

# Exploiting Weaknesses:

Part of ethical hacking involves learning how to chain weaknesses together. A single weakness may not seem like a critical issue on its own, but when combined with other weaknesses, it can lead to serious consequences.

## Think Like a Hacker
To become a hacker, you must think like one. Hackers look beyond whether something works as intended and ask how it might be misused, combined with other behavior, or used for unauthorized access. This means thinking creatively and testing new ideas. Ethical hackers adopt this same mindset, but in a safe and authorized way. They find and prove risks before real attackers can.

Here are some key points to keep in mind as you continue your ethical hacking journey.

- Ask questions: Don't assume a feature works as intended. Instead, ask “What if it doesn't?”
- Test the unexpected: Try actions and inputs that the developers didn't consider
- Chain small weaknesses: A tiny flaw may be harmless alone, but could be connected to create a bigger impact
- Think like an adversary: Think “How would a malicious actor approach this target?”

## A Valuable Target

Attackers are often interested in gaining valid credentials, such as usernames and passwords, because gaining access can unlock private areas of an application and increase their capabilities.

- Sensitive functionality: Features that perform essential actions, such as modifying data, viewing restricted content, or triggering processes that should only be available to authorized users
- User data: Personal or private information belonging to users, such as names, email addresses, or account details, which attackers may steal, abuse, or sell
- Administrative features: High-privilege functionality that allows attackers to manage users, change settings, or gain full control of the application if accessed
- Further attack opportunities: Authenticated access can expose other vulnerabilities, allowing attackers to expand their access or move deeper into the application

## Using Automated Tool to exploit weaknesses (hydra)

Example:
`hydra -l admin -P passlist.txt www.onlineshop.thm http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect" -V`

- `hydra` - The command-line tool used to perform the dictionary attack
- `-l admin` - Attempts to log in using the username admin
- `-P passlist.txt` - Specifies the password list to try
- `www.onlineshop.thm` - Sets the target website
- `http-post-form` - Indicates that this is an HTTP POST request form
- `"/login:username=^USER^&password=^PASS^:F=incorrect"` - Specifies how the login request is sent and how Hydra determines whether a login attempt has failed
- `-V` Enables verbose output, which displays each username and password attempted