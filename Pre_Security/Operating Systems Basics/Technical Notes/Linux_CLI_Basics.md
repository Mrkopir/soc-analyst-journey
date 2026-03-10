# Linux CLI Basics - TryHackMe

## 1. Terminal

The terminal is a text-based interface for controlling a Linux system.

Benefits:

- It's faster than clicking around
- It gives more control
- Many security tools only run in the terminal


## 2. Basic linux terminal commands

## Work with files:

### Command `pwd`
It stands for "print working directory", which basically means "show me the folder I'm currently in". 

### Command `ls`
It shows folders or files in current directory. Flag `-l` shows more details. Flag `-al` hiden files.

### Command `cd`
It is needed for walk through the file system. To go back use `cd ..`

### Command `find`
This is built-in utility is used to locate files within the file system.

### Command `cat`
This is used to read the content of the file. 

## Work with users:

### Command `whoami`

This prints your current username.

### Command `uname`

This prints name of OS. Flag `-a` shows more details.

### Command `df`

This prints information about disks. Flag `-h` shows human readable format