# Operating Systems: Introduction - TryHackMe

## 1. Operating System or OS

Operating System (OS) is the core software that coordinates everything happening on a computer. It sits between the user, applications, and the system’s physical hardware, acting as the invisible manager that keeps the entire machine running as one unified system.

## 2. System Privilege Layers

Inside a modern computer, different parts of the system operate at various permission levels. Some components can communicate directly with the hardware, while regular applications run in a safer, restricted environment. This separation is intentional and helps prevent conflicts and security issues.

- Kernel space: The privileged, locked-down core of the OS. This is where the kernel, the part of the operating system that directly manages hardware and system resources, runs. It has unrestricted access to the CPU, memory, storage, and all hardware components.
- User space: Where all standard applications run. Applications in the user space are deliberately prevented from accessing hardware directly. Whenever they need to open or save a file, play a sound, or connect to Wi-Fi, they must make a system call and request that the kernel act on their behalf.


## 3. Operating System Duties

- Process Management: Creates, schedules, prioritizes, and terminates running programs. The OS decides how much CPU time each process gets, making multitasking feel seamless
- Memory Management: Allocates RAM to processes, protects the app's memory from other processes, and reclaims memory when apps are closed. When RAM runs low, the OS uses virtual memory to keep your system stable
- File System Management: Organizes files into directories, handles naming, paths, permissions, metadata (name, size, type, timestamps)
- User Management: Handles multiple user accounts, authentication, and permissions to determine who can access what
- Device Management: Loads drivers and provides a universal interface (hardware abstraction layer), so apps can say “print this” or “play this sound”

## 4. Operating System Security

- Authentication: Verifies who you are through login passwords and biometrics
- Permissions: Controls exactly what each user and app is allowed to read, write, or execute
- Isolation: Keeps every process in its own protected box (kernel/user space separation)
- System Protection: Safeguards critical system files and settings from unauthorized changes

## 5. OS Interfaces

- Graphical User Interface (GUI) - it provides a graphical representation of all the information you want to access on your computer.

- Command-line Interface (CLI) - where you enter specific text-based commands to retrieve or manipulate information.

## 6. The Operating System Landscape

- Desktop: Personal computers, daily work, gaming, content creation
- Server: Web hosting, databases, cloud services, back-end
- Mobile: Smartphones and tablets
- Embedded: Appliances, cars, IoT devices, smart TVs, routers
- Virtual/Cloud: Virtual machines, containers, cloud instances


## 7. Real World Operating Systems

- Desktop
    - Windows: The most widely used operating system on personal computers
    - Windows 10 (end-of-life), Windows 11
    - macOS: Apple's desktop OS, known for its polished GUI and integration with other Apple devices
    - Sonoma (14), Sequoia (15), Tahoe (26)
    - Linux: Not a single OS but a family of open-source operating systems called distributions
    - Ubuntu, Debian, Fedora

- Server
    - Windows: Used in large networks, data centers, and corporate environments
    - Server 2016, 2019, 2022, 2025
    - Linux: The vast majority of web servers, trusted for its reliability and open-source nature
    - Ubuntu Server, Debian, CentOS, Red Hat
    - Unix: Large enterprises, finance, telecom, government
    - IBM AIX, Oracle Solaris

- Mobile
    - Android: The most widely used mobile OS, which runs on phones, tablets, and smart devices
    - Android 14 - 16, Manufacturer versions
    - iOS: Apple's mobile OS running on iPhones, iPads, and other devices
    - iOS 17, 18, 26

- Embedded and IoT Devices
    - Embedded Linux: Specialized OS built into devices with dedicated functions
    - OpenWrt, Ubuntu Core, Yocto Project
    - Real-Time OS: Designed for apps where tasks need guaranteed response times (aircraft controls)
    - FreeRTOS, VxWorks, QNX
    - Virtual and Cloud

- Cloud/VM: Massive data centers that host websites, apps, and streaming services
    - Ubuntu LTS, Amazon Linux, Rocky Linux
    - Container-optimized: Lightweight alternatives to VMs that package just the app and its dependencies
    - Alpine Linux, Bottlerocket AWS, Flatcar Linux