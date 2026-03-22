# Linux Fundamentals Part 2 - TryHackMe

## 1. SSH

Secure Shell or SSH simply is a protocol between devices in an encrypted form. Using cryptography, any input we send in a human-readable format is encrypted for travelling over a network where it is then unencrypted once it reaches the remote machine, such as in the diagram below.

The syntax to use SSH is very simple. We only need to provide two things:

1. The IP address of the remote machine

2. Correct credentials to a valid account to login with on the remote machine

## 2. Flags and Switches

A majority of commands allow for arguments to be provided. These arguments are identified by a hyphen and a certain keyword known as flags or switches. Using our `ls` example, `ls` informs us that there is only one folder named "folder1" as highlighted in the screenshot below. However, after using the `-a` argument (short for `--all`), we now suddenly have an output with a few more files and folders. Files and folders with "." are hidden files.

Commands that accept these will also have a `--help` option. This option will list the possible options that the command accepts

Command `man` - To access this documentation, we can use the man command and then provide the command we want to read the documentation for.

## 3. Interacting With the Filesystem commands (CONTINUED)

- `touch` - create file
- `mkdir` (make directory) - create a folder
- `cp` (copy) - copy a file or folder
- `mv` (move) - Move a file or folder
- `rm` (remove) - Remove file or directory but need Flag `-R`
- `file` - Determine the type of a file 

## 4. Permissions 101

We can use flag `-l` or `-lh` for `ls` command to check permissions.

A file or folder can have a couple of characteristics that determine both what actions are allowed and what user or group has the ability to perform the given action -- such as the following:

- Read
- Write
- Execute

### The Differences Between Users & Groups

The great thing about Linux is that permissions can be so granular, that whilst a user technically owns a file, if the permissions have been set, then a group of users can also have either the same or a different set of permissions to the exact same file without affecting the file owner itself.

### Switching Between Users

Switching between users on a Linux install is easy work thanks to the `su` command. Unless you are the root user (or using root permissions through sudo), then you are required to know two things to facilitate this transition of user accounts:

- The user we wish to switch to
- The user's password

### File Permissions in Numeric Format

In Linux, every file and directory has a set of permissions that control who can read, write, or execute it. These permissions are often displayed in symbolic format, such as: `rwxrwxrwx`

1. First three - owner
2. Secound three - Group
3. Last 3 - Others

Converting Symbolic Permissions to Numbers:
r - 4
w - 3
x - 1

## 5. Common Directories

### `/etc`

This root directory is one of the most important root directories on system. The etc folder (short for etcetera) is a commonplace location to store system files that are used by operating system. 

For example, the `sudoers` file contains a list of the users & groups that have permission to run sudo or a set of commands as the root user.

Also highlighted below are the "passwd" and "shadow" files. These two files are special for Linux as they show how system stores the passwords for each user in encrypted formatting called sha512.

### `/var`
The `/var` directory, with `var` being short for variable data, is one of the main root folders found on a Linux install. This folder stores data that is frequently accessed or written by services or applications running on the system. For example, log files from running services and applications are written here (/var/log), or other data that is not necessarily associated with a specific user (i.e., databases and the like).

### `/root`
Unlike the `/home` directory, the `/root` folder is actually the home for the "root" system user. There isn't anything more to this folder other than just understanding that this is the home directory for the root user. But, it is worth a mention as the logical presumption is that this user would have their data in a directory such as `/home/root` by default.  

### `/tmp`
This is a unique root directory found on a Linux install. Short for "temporary", the /tmp directory is volatile and is used to store data that is only needed to be accessed once or twice. Similar to the memory on your computer, once the computer is restarted, the contents of this folder are cleared out.