# Linux Fundamentals Part 1 - TryHackMe

## 1. Background on Linux

Linux is a lot more intimidating to approach than Operating System's (OSs) such as Windows.

Linux powers things such as:
- Websites that you visit
- Car entertainment/control panels
- Point of Sale (PoS) systems such as checkout tills and registers in shops
- Critical infrastructures such as traffic light controllers or industrial sensors

The name "Linux" is actually an umbrella term for multiple OS's that are based on UNIX (another operating system). Thanks to Linux being open-source, variants of Linux come in all shapes and sizes - suited best for what the system is being used for.

## 2. Basic output text and current user commands

- `echo` - 	Output any text that we provide
- `whoami` - Find out what user we're currently logged in as!

## 3. Interacting With the Filesystem commands

- `ls` - listing, shows what exists in the first place.
- `cd` - change directory
- `cat` - concatenate
- `pwd` - print working directory

## 4. Searching Files commands

- `find` - This command helps locate files and directories in a system. For example, `find -name passwords.txt` searches for a file named passwords.txt. 
Also search for all files with a specific extension, such as `.txt`. Example:  `find -name "*.txt"`.

- `grep` - command allows us to search the contents of files for specific values that we are looking for. Example: we want to see everything that the IP address "81.143.211.90" has visited `grep "81.143.211.90" access.log`. 
Also we can use param `-R` to search recursively through all files and subdirectories. Example: `grep -R "PRETTY_NAME" /etc/`

## 5. Basic Shell Operators

Symbols/Operator:

- & - This operator allows you to run commands in the background of your terminal.
- && - This operator allows you to combine multiple commands together in one line of your terminal. 
- \> - This operator is a redirector - meaning that we can take the output from a command (such as using cat to output a file) and direct it elsewhere.
- \>> - This operator does the same function of the > operator but appends the output rather than replacing (meaning nothing is overwritten).