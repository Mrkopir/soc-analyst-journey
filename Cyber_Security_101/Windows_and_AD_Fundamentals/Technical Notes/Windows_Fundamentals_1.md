# Windows Fundamentals 1 - TryHackMe

## 1. Windows Editions

The Windows operating system has a long history dating back to 1985, and currently, it is the dominant operating system in both home use and corporate networks. Because of this, Windows has always been targeted by hackers & malware writers.

Windows XP was a popular version of Windows and had a long-running. Microsoft announced Windows Vista , which was a complete overhaul of the Windows operating system. There were many issues with Windows Vista. It wasn't received well by Windows users, and it was quickly phased out.

When Microsoft announced the end-of-life date for Windows XP, many customers panicked. Corporations, hospitals, etc., scrambled and tested the next viable Windows  version , which was Windows 7, against many other hardware and devices. Vendors had to work against the clock to ensure their products worked with Windows 7 for their customers. If they couldn't, their customers had to break their agreement and find another vendor that upgraded their products to work with Windows 7. It was a nightmare for many, and Microsoft took note of it.

Windows 7, as quickly as it was released soon after, was marked with an end of support date.  Windows 8.x came and left and it was short-lived, like Vista.

Then arrived Windows 10 followed by Windows 11(opens in new tab), which is the current Windows operating system version for desktop computers.

Windows 11 comes in 2 flavors, Home and Pro.

## 2. Windows GUI

Windows GUI (Graphical User Interface) is the visual interface of the Windows operating system that allows users to interact with the system using graphical elements instead of command-line instructions.

It includes components such as:
- **Desktop** – the main workspace where icons and windows are displayed
- **Taskbar** – provides access to running applications and system features
- **Start Menu** – allows users to launch programs and access system settings
- **Windows** – interactive areas where applications run
- **Icons** – graphical representations of files, folders, and applications

The Windows GUI makes it easier for users to navigate the system, manage files, and perform tasks without needing advanced technical knowledge.

## 3. File System

The file system used in modern versions of  Windows  is the New Technology File System or simply  **NTFS** (opens in new tab). Before **NTFS**, there was  **FAT16/FAT32** (File Allocation Table) and **HPFS** (High Performance File System). **NTFS** is known as a journaling file system. In case of a failure, the file system can automatically repair the folders/files on disk using information stored in a log file. This function is not possible with **FAT**.

### NTFS addresses many of the limitations of the previous file systems; such as:
- Supports files larger than 4GB
- Set specific permissions on folders and files
- Folder and file compression
- Encryption ( Encryption File System (opens in new tab)or EFS )

### The permissions are of NTFS:
- Full control
- Modify
- Read & Execute
- List folder contents
- Read
- Write

### How can you view the permissions for a file or folder:

- Right-click the file or folder you want to check for permissions.
- From the context menu, select Properties .
- Within Properties, click on the Security tab.
- In the Group or user names list, select the user, computer, or group whose permissions you want to view.


### NTFS ADS (Alternate Data Streams)

ADS (Alternate Data Streams) is a feature of the NTFS file system that allows storing additional hidden data inside a file.

For example:
file.txt:hidden.txt

This creates a hidden stream attached to `file.txt` that is not visible in standard file browsing.

ADS can be used to store metadata, but it may also be abused to hide malicious files or scripts.

In simple terms:
ADS = hidden data inside a file.


## 4. Windows/System32 Folders

### `C:\Windows`

The Windows folder ( `C:\Windows` ) is traditionally known as the folder which contains the Windows operating system. 

The folder doesn't have to reside in the C drive necessarily. It can reside in any other drive and technically can reside in a different folder.

This is where environment variables, more specifically system environment variables, come into play.  Even though not discussed yet, the system  environment variable for the Windows directory is `%windir%`.

Per Microsoft (opens in new tab), " Environment variables store information about the operating system environment. This information includes details such as the operating system path, the number of processors used by the operating system, and the location of temporary folders.

### `C:\Windows\System32`

The System32 folder holds the important files that are critical for the operating system.

## 5. Users & Profiles & Permissions

User accounts can be one of two types on a typical local Windows system:
- Administrator
- Standard User

- An Administrator can make changes to the system: add users, delete users, modify groups, modify settings on the system, etc. 
- A Standard User can only make changes to folders/files attributed to the user & can't perform system-level changes, such as install programs.

When a user account is created, a profile is created for the user. The location for each user profile folder will fall under is `C:\Users`.

### Local User and Group Management

**Win + R >> lusrmgr.msc**


## 6. User Account Control

To protect the local user with such privileges, Microsoft introduced **User Account Control (UAC)**. This concept was first introduced with the short-lived Windows Vista (opens in new tab) and continued with versions of Windows that followed.

### How does UAC work?

When a user with an account type of administrator logs into a system, the current session doesn't run with elevated permissions. When an operation requiring higher-level privileges needs to execute, the user will be prompted to confirm if they permit the operation to run. 


## 7. Task Manager

The Task Manager provides information about the applications and processes currently running on the system. Other information is also available, such as how much CPU and RAM are being utilized, which falls under **Performance**. 

To open Task Manager use: **ctrl + shift + esc**