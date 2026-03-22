# Windows Fundamentals 2 - TryHackMe

## 1. System Configuration & Advanced System Settings

### System Configuration

The **System Configuration utility** (`MSConfig`) is for advanced troubleshooting, and its main purpose is to help diagnose startup issues.

The utility has five tabs across the top:

- General: use to select what devices and services for Windows to load upon boot. The options are: Normal, Diagnostic, or Selective. 

- Boot: use to define various boot options for the Operating System

- Services:  tab lists all services configured for the system regardless of their state (running or stopped). A service is a special type of application that runs in the background.  

- Startup: allows users to manage which programs start automatically when the system boots.

- Tools: list of various utilities (tools) in the Tools tab here that we can run to configure the operating system further. There is a brief description of each tool to provide some insight into what the tool is for. 

### Advanced System Settings

Windows gives you some additional configuration settings as well, which you can use to control the performance behavior and system recovery. To access this option, you can search for View advanced system settings in your search bar and open it.

Windows uses a page file as an extra virtual memory space when the physical RAM becomes full. This helps to prevent slowdowns or application crashes when the system runs out of memory. You can view or modify the page file by navigating to the Advanced option at the top and clicking **Settings** under the **Performance** tab.

Startup and Recovery:  Windows can create a crash dump file whenever it encounters a critical error, such as a Blue Screen of Death.

## 2. UAC Settings

The UAC settings can be changed or even turned off entirely. There the slider to see how the setting will change the UAC settings and Microsoft's stance on the setting.

This slider has four security levels, each of which controls how Windows alerts you when apps or users try to make changes at the system level. They fall into four standard categories as explained below:

- Always notify: This is the highest security. Windows notifies you whenever any apps or you yourself try to make changes, and the desktop dims.

- Notify for apps: Windows notifies only when apps try to make changes, but not when you change Windows settings. This option is enabled by default.

- Notify without dimming: Same as above (Notify for apps), but this time the screen does not dim. 

- Never notify: Notifications are turned off. Windows won’t warn you about any changes made by you or any apps. 

## 3. Computer Management (tool from System Configuration)

The Computer Management (`compmgmt`) utility has three primary sections: System Tools, Storage, and Services and Applications.

### System Tools

- Task Scheduler: with Task Scheduler, we can create and manage common tasks that our computer will carry out automatically at the times we specify.

- Event Viewer: allows us to view events that have occurred on the computer. These records of events can be seen as an audit trail that can be used to understand the activity of the computer system. This information is often used to diagnose problems and investigate actions executed on the system. 

- Shared Folders: is where you will see a complete list of shares and folders shared that others can connect to. 

- Local Users and Groups: section you should be familiar with `lusrmgr.msc`

- Performance Monitor: Perfmon is used to view performance data either in real-time or from a log file. This utility is useful for troubleshooting performance issues on a computer system, whether local or remote. 

- Device Manager: allows us to view and configure the hardware, such as disabling any hardware attached to the computer.

- Disk Management: is a system utility in Windows that enables you to perform advanced storage tasks. It allows tasks: Set up a new drive; Extend a partition; Shrink a partition; Assign or change a drive letter (ex. E:) 

- Services and Applications: a service is a special type of application that runs in the background

- WMI Control configures and controls the Windows Management Instrumentation (WMI) service: WMI allows scripting languages (such as VBScript or Windows PowerShell) to manage Microsoft Windows personal computers and servers, both locally and remotely. Microsoft also provides a command-line interface to WMI called Windows Management Instrumentation Command-line (WMIC)

Note: The WMIC tool is deprecated in Windows 10, version 21H1. Windows PowerShell supersedes this tool for WMI.

## 4. System Information

`msinfo32`: Windows includes a tool called Microsoft System Information. This tool gathers information about your computer and displays a comprehensive view of your hardware, system components, and software environment, which you can use to diagnose computer issues.

The  information in **System Summary** (System Summary will display general technical specifications for the computer, such as processor brand and model.) is divided into three sections:

- Hardware Resources: are the assignable, addressable bus paths that allow peripheral devices and system processors to communicate with each other. Hardware resources typically include I/O port addresses, interrupt vectors, and blocks of bus-relative memory addresses.

- Components: specific information about the hardware devices installed on the computer. Some sections don't show any information, but some sections do, such as Display and Input.

- Software Environment: information about software baked into the operating system and software you have installed. Other details are visible in this section as well, such as the Environment Variables and Network Connections. 

## 5. Resource Monitor

`resmon`:  displays per-process and aggregate CPU, memory, disk, and network usage information, in addition to providing details about which processes are using individual file handles and modules. Advanced filtering allows users to isolate the data related to one or more processes (either applications or services), start, stop, pause, and resume services, and close unresponsive applications from the user interface. It also includes a process analysis feature that can help identify deadlocked processes and file locking conflicts so that the user can attempt to resolve the conflict instead of closing an application and potentially losing data.


## 6. Registry Editor

The **Windows Registry** (per Microsoft) is a central hierarchical database used to store information necessary to configure the system for one or more users, applications, and hardware devices.

The registry contains information that Windows continually references during operation, such as:

- Profiles for each user
- Applications installed on the computer and the types of documents that each can create
- Property sheet settings for folders and application icons
- What hardware exists on the system
- The ports that are being used.