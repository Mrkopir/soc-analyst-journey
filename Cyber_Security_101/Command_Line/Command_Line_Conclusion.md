# Linux Shells, Windows Command Line & PowerShell – Final Reflection (TryHackMe)

## Overview

During this learning path, I explored different command-line environments across Linux and Windows systems. I learned about Linux shells such as Bash, Zsh, and Fish, as well as Windows Command Line and PowerShell. These tools provide direct interaction with the operating system and are essential for automation, system management, and cybersecurity tasks.

Understanding CLI environments is critical in cybersecurity, as they allow efficient system control, scripting, and analysis without relying on graphical interfaces.

## Technical Understanding

In the Linux section, I learned about various shells and their features. Bash is the default shell in most distributions and provides scripting, command history, and tab completion. Zsh offers enhanced customization and advanced completion, while Fish focuses on usability with syntax highlighting and auto-correction.

I also learned how to configure shells and switch between them using commands such as `chsh`. Shell scripting was an important part of this section, where I learned how to create scripts using a shebang (`#!/bin/bash`), assign execution permissions with `chmod +x`, and execute scripts.

Additionally, I practiced working with variables using `read`, loops using `for`, and conditional statements using `if`, which are fundamental for automation and scripting.

In the Windows Command Line section, I explored system and network management tools. Commands such as `systeminfo`, `ver`, and `set` provide system information, while `ipconfig`, `ping`, `tracert`, and `nslookup` are used for network troubleshooting.

I also learned file and directory management using commands like `cd`, `dir`, `mkdir`, `move`, and `del`. Process management commands such as `tasklist` and `taskkill` allow monitoring and controlling running processes. Tools like `chkdsk` and `sfc /scannow` help detect and repair system issues.

An important addition was learning PowerShell, which is a modern, object-oriented command-line shell and scripting language. :contentReference[oaicite:0]{index=0} Unlike traditional CLI tools that work with plain text, PowerShell works with objects, allowing more advanced data manipulation.

I learned that PowerShell uses a consistent `Verb-Noun` syntax for its cmdlets, such as `Get-Content` and `Set-Location`. I also explored commands like `Get-Command`, `Get-Help`, and `Get-Alias`, which help discover and understand available functionality.

PowerShell allows efficient file and system management using commands such as `Get-ChildItem`, `New-Item`, `Copy-Item`, `Move-Item`, and `Remove-Item`. One of the most powerful features is piping (`|`), which allows passing objects between commands for filtering and sorting using tools like `Where-Object` and `Sort-Object`.

I also explored system and network monitoring using commands such as `Get-Process`, `Get-Service`, and `Get-NetTCPConnection`. These tools provide detailed insights into system activity, which is essential for troubleshooting and security analysis.

## Security Perspective

From a security perspective, command-line tools are essential for both defensive and offensive operations. Shell scripting in Linux and PowerShell scripting in Windows allow automation of tasks such as log analysis, system monitoring, and detection of anomalies.

PowerShell is especially powerful in cybersecurity because it can interact deeply with system components and automate complex tasks. However, this also makes it a common tool used by attackers, which means security professionals must understand it well to detect and respond to threats.

Commands like `netstat`, `Get-Process`, and `Get-Service` help identify suspicious activity, while scripting can automate incident response and monitoring tasks.

Understanding CLI environments across multiple operating systems allows security professionals to work efficiently in different environments and respond to incidents effectively.

## Conclusion

This learning path provided a strong foundation in working with command-line environments across Linux and Windows systems. I learned how to use different shells, write scripts, manage files and processes, troubleshoot networks, and analyze system behavior.

The addition of PowerShell significantly enhanced my understanding of automation and system interaction, especially in Windows environments.

These skills are essential for cybersecurity professionals, particularly in SOC analyst roles, where automation, investigation, and system visibility are critical.

Overall, this course improved my confidence in using CLI tools and prepared me for more advanced topics in cybersecurity and system administration.