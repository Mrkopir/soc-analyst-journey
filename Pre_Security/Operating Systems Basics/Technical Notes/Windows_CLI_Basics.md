# Windows CLI Basics - TryHackMe

## 1. Command Prompt

The Command Prompt (often referred to as CMD) is a text-based interface for interacting with the Windows operating system. Instead of clicking folders and menus, you type commands to tell the system exactly what you want to do, such as listing files, moving between folders, or checking system information. It might look simple, but it's a powerful and widely used tool.

## 2. Basic Command Prompt commands

## Work with files:

### Command `cd`
It is needed for walk through the file system. To go back use `cd ..`. Like in linux terminal

### Command `dir`
It stands for "print working directory", which basically means "show me the folder I'm currently in". Flag `/a` shows hiden files. Flag `/s <file-name>` find files on disk.

### Command `type`
It is needed to read file.

## Work with users:

### Command `whoami`
This prints your current username (which user account you’re using).

### Command `hostname`
This prints name of PC

### Command `systeminfo`
It shows our PC details

### Command `ipconfig`
This shows the machine's network configuration.