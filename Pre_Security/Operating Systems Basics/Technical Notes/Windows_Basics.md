# Windows_Basics - TryHackMe

## 1. Logging in and Authentication

Before gaining access to the Windows Desktop, you must authenticate (prove your identity) to the system. The authentication process verifies your identity and determines the actions you're allowed to take once logged in.

- Guest: A restricted account intended for temporary access, with minimal permissions and no ability to change system settings
- Standard: A user account for everyday tasks, such as running applications and changing personal settings, without access to system-wide changes
- Administrator: A privileged account with full control over the system, including software installation, configuration changes, and user management

## 2. The Windows Desktop

It contains:
- Desktop: The main workspace where files, folders, and shortcuts live
- Taskbar: A control strip that provides access to applications, system tools, settings, and notifications

## 3. Built-in Tools and Apps

Beyond the wide range of settings available to manage your system, Windows also includes simple but powerful tools such as Notepad for editing text files and File Explorer for navigating and managing files. These tools are available immediately and form the foundation of everyday Windows usage. All of them can be accessed via the Start menu and search bar.


## 4. Windows Updates & Updating Applications

- Windows includes a built-in update tool called Windows Update, which keeps the OS and some native applications and security features up to date.

- Application updates work differently depending on how the software is installed.

    - Built-in applications may update automatically in the background
    - Third-party applications often include their own update mechanisms
    - Some applications will prompt you to update upon launch
    - Some require you to check for updates or download a new installer manually

## 5. Installing Applications & Uninstalling Applications
**Install:**
- Microsoft Store: Provides a curated and safe option for installing apps to Windows, although it is not available by default on Windows Server
- From the Internet: In many environments, apps are installed by downloading an installer directly from a trusted vendor's website. They usually come in an .exe or .msi file and guide the user through the installation process

**Uninstall:**
In a Windows environment, there are multiple ways to uninstall programs.

- Using the Microsoft Store for installed applications
- Add or remove programs feature in system settings
- Uninstall a program section of the Control Panel
- Using an application's built-in uninstaller

## 6. Diving Into Settings

**Windows Settings** and the **Control Panel** enable you to view and modify how your Windows system operates. From these two applications, you can manage system preferences, including display and audio settings, user accounts, apps, network options, accessibility features, and security configurations.

- Windows Settings: A modern, centralized location for configuring system, device, personalization, and security settings in Windows
- Control Panel: A legacy management interface that provides access to older system configuration tools still required for specific administrative tasks

## 7. The Task Manager

Task Manager is a built-in Windows tool that allows you to monitor what is happening on your system in real time. It allows you to view running applications and background processes, as well as check system performance, including CPU and memory usage. A shortcut to Task Manager has been placed on your workstation's Desktop.

Task Manager has five tabs:

- Processes: Currently running apps and background processes, and their resource usage
- Performance: Graphs and statistics for system resources such as CPU, memory, and network
- Users: Currently logged-in users and used resources 
- Details: A more technical view of running processes, including process IDs (PIDs)
- Services: Windows services and their current status (running or stopped)

# Native Windows Security

Windows offers built-in security tools designed to help protect your system from threats such as malware, insecure applications, and unauthorized network access.

## **Windows Security:**
The Windows Security application is your central dashboard for managing Windows' built-in protection measures. It is divided into four main sections, each focusing on a different area of system security.

- Virus & threat protection: Helps detect and remove malicious software using real-time protection and customizable scans
- Firewall & network protection: Controls incoming and outgoing network traffic to help prevent unauthorized access
- App & browser control: Protects users from potentially unsafe apps, files, and websites
- Device security: Provides hardware-based protections that help secure the system

## **Windows Defender Firewall:**
Windows Defender Firewall is a built-in firewall designed to help protect your computer from unauthorized network traffic. It monitors network connections and applies rules that determine whether the connections are allowed or denied. The firewall operates on different network profiles, allowing you to create custom rules or specify applications that are permitted.

- Domain: Used when a system is connected to an organization’s domain network
- Private: Intended for trusted networks, such as a home or lab environment 
- Public: Used for untrusted networks, such as public Wi-Fi