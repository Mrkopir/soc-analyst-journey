# Windows PowerShell - TryHackMe

## 1. What Is PowerShell

**PowerShell** is a cross-platform task automation solution made up of a command-line shell, a scripting language, and a configuration management framework. PowerShell is a powerful tool from Microsoft designed for task automation and configuration management. It combines a command-line interface and a scripting language built on the .NET framework. Unlike older text-based command-line tools, PowerShell is object-oriented, which means it can handle complex data types and interact with system components more effectively. Initially exclusive to Windows, PowerShell has lately expanded to support macOS and Linux, making it a versatile option for IT professionals across different operating systems.

### A Brief History of PowerShell

PowerShell was developed to overcome the limitations of existing command-line tools and scripting environments in Windows. In the early 2000s, as Windows was increasingly used in complex enterprise environments, traditional tools like cmd.exe and batch files fell short in automating and managing these systems.

Jeffrey Snover, a Microsoft engineer, realised that Windows and Unix handled system operations differently—Windows used structured data and APIs, while Unix treated everything as text files. This difference made porting Unix tools to Windows impractical. Snover’s solution was to develop an object-oriented approach, combining scripting simplicity with the power of the .NET framework. Released in 2006, PowerShell allowed administrators to automate tasks more effectively by manipulating objects, offering deeper integration with Windows systems.

As IT environments evolved to include various operating systems, the need for a versatile automation tool grew. In 2016, Microsoft responded by releasing PowerShell Core, an open-source and cross-platform version that runs on Windows, macOS, and Linux.

### The Power in PowerShell

To fully grasp the power of PowerShell, we first need to understand what an object is in this context.

In programming, an object represents an item with properties (characteristics) and methods (actions). For example, a car object might have properties like Color, Model, and FuelLevel, and methods like Drive(), HonkHorn(), and Refuel().

Similarly, in PowerShell, objects are fundamental units that encapsulate data and functionality, making it easier to manage and manipulate information. An object in PowerShell can contain file names, usernames or sizes as data (properties), and carry functions (methods) such as copying a file or stopping a process.

The traditional Command Shell’s basic commands are text-based, meaning they process and output data as plain text. Instead, when a cmdlet (pronounced command-let) is run in PowerShell, it returns objects that retain their properties and methods. This allows for more powerful and flexible data manipulation since these objects do not require additional parsing of text.


## 2. PowerShell Basics

### Launching PowerShell:

PowerShell can be launched in several ways, depending on your needs and environment. If you are working on a Windows system from the graphical interface (GUI), these are some of the possible ways to launch it:

- Start Menu: Type powershell in the Windows Start Menu search bar, then click on Windows PowerShell or PowerShell from the results.
- Run Dialog: Press Win + R to open the Run dialog, type powershell, and hit Enter.
- File Explorer: Navigate to any folder, then type powershell in the address bar, and press Enter. This opens PowerShell in that specific directory.
- Task Manager: Open the Task Manager, go to File > Run new task, type powershell, and press Enter.

### Basic Syntax: Verb-Noun

`cmdlets (pronounced command-lets)`: They are much more powerful than the traditional Windows commands and allow for more advanced data manipulation.

Cmdlets follow a consistent `Verb-Noun` naming convention. The Verb describes the action, and the Noun specifies the object on which action is performed. 
For example:

- `Get-Content`: Retrieves (gets) the content of a file and displays it in the console.
- `Set-Location`: Changes (sets) the current working directory.

### Basic Cmdlets:

- `Get-Command`: to list all available cmdlets, functions, aliases, and scripts that can be executed in the current PowerShell session. If we want to display only the available commands of type “function”, we can use -CommandType "Function".

- `Get-Help`: it provides detailed information about cmdlets, including usage, parameters, and examples. For example, by appending `-examples` to the command displayed above, we will be shown a list of common ways in which the chosen cmdlet can be used.

- `Get-Alias`: lists all aliases available.

### Where to Find and Download Cmdlets:

- `Find-Module`: To search for modules (collections of cmdlets) in online repositories like the PowerShell Gallery. We can achieve this by filtering the `Name` property and appending a wildcard (`*`) to the module’s partial name, using the following standard PowerShell syntax: `Cmdlet -Property "pattern"`.

- `Install-Module`:  to download modules from the repository.

## 3. Navigating the File System and Working with Files

- `Get-ChildItem`: lists the files and directories in a location specified with the -Path parameter. It can be used to explore directories and view their contents. If no Path is specified, the cmdlet will display the content of the current working directory.

- `Set-Location`: It changes the current directory. Example: `Set-Location -Path ".\Documents"`.

- `New-Item`: to create an item. Example: `New-Item -Path ".\captain-cabin\captain-wardrobe" -ItemType "Directory"`.

- `Remove-Item`: removes both directories and files Example: `Remove-Item -Path ".\captain-cabin\captain-wardrobe\captain-boots.txt"`.

- `Copy-Item`: copy files. Example: `Copy-Item -Path .\captain-cabin\captain-hat.txt -Destination .\captain-cabin\captain-hat2.txt`.

- `Move-Item`: Move files. Example: `Move-Item -Path .\captain-cabin\captain-hat.txt -Destination .\captain-cabin\captain-hat2.txt`

- `Get-Content`: to read and display the contents of a file. Example: `Get-Content -Path ".\captain-hat.txt"`


## 4. Piping, Filtering, and Sorting Data

Piping is a technique used in command-line environments that allows the output of one command to be used as the input for another. This creates a sequence of operations where the data flows from one command to the next. Represented by the | symbol, piping is widely used in the Windows CLI, as introduced earlier in this module, as well as in Unix-based shells.

In PowerShell, piping is even more powerful because it passes objects rather than just text. These objects carry not only the data but also the properties and methods that describe and interact with the data.

For example, if you want to get a list of files in a directory and then sort them by size, you could use the following command in PowerShell: `Get-ChildItem | Sort-Object Length`

Next Example: `Get-ChildItem | Where-Object -Property "Extension" -eq ".txt"`. The operator -eq (i.e. "equal to") is part of a set of comparison operators that are shared with other scripting languages (e.g. Bash, Python). To show the potentiality of the PowerShell's filtering, we have selected some of the most useful operators from that list:

- `-ne`: "not equal". This operator can be used to exclude objects from the results based on specified criteria.
- `-gt`: "greater than". This operator will filter only objects which exceed a specified value. It is important to note that this is a strict comparison, meaning that objects that are equal to the specified value will be excluded from the results.
- `-ge`: "greater than or equal to". This is the non-strict version of the previous operator. A combination of -gt and -eq.
- `-lt`: "less than". Like its counterpart, "greater than", this is a strict operator. It will include only objects which are strictly below a certain value.
- `-le`: "less than or equal to". Just like its counterpart -ge, this is the non-strict version of the previous operator. A combination of -lt and -eq.
Below, another example shows that objects can also be filtered by selecting properties that match (-like) a specified patter.

`Select-Object`: is used to select specific properties from objects or limit the number of objects returned. It’s useful for refining the output to show only the details one needs.

`Select-String`: this advanced feature allows for complex pattern matching within files, making it a powerful tool for searching and analysing text data.

## 5. System and Network Information

- `Get-ComputerInfo`: retrieves comprehensive system information, including operating system information, hardware specifications, BIOS details, and more.

- `Get-LocalUser`: lists all the local user accounts on the system.

- `Get-NetIPConfiguration`: provides detailed information about the network interfaces on the system, including IP addresses, DNS servers, and gateway configurations.

- `Get-NetIPAddress`: show details for all IP addresses configured on the system, including those that are not currently active.

## 6. Real-Time System Analysis

- `Get-Process`: provides a detailed view of all currently running processes, including CPU and memory usage, making it a powerful tool for monitoring and troubleshooting.

- `Get-Service`: allows the retrieval of information about the status of services on the machine, such as which services are running, stopped, or paused.

- `Get-NetTCPConnection`:  displays current TCP connections, giving insights into both local and remote endpoints.

- `Get-FileHash`: generating file hashes.

- `Get-Item -Path "Path" -Stream *`: view the Alternate Data Streams (ADS) attached to a file.

## 7. Scripting

Scripting is the process of writing and executing a series of commands contained in a text file, known as a script, to automate tasks that one would generally perform manually in a shell, like PowerShell.

Learning scripting with PowerShell goes beyond the scope of this room. Nonetheless, we must understand that its power makes it a crucial skill across all cyber security roles.

- For blue team professionals such as incident responders, malware analysts, and threat hunters, PowerShell scripts can automate many different tasks, including log analysis, detecting anomalies, and extracting indicators of compromise (IOCs). These scripts can also be used to reverse-engineer malicious code (malware) or automate the scanning of systems for signs of intrusion.

- For the red team, including penetration testers and ethical hackers, PowerShell scripts can automate tasks like system enumeration, executing remote commands, and crafting obfuscated scripts to bypass defences. Its deep integration with all types of systems makes it a powerful tool for simulating attacks and testing systems’ resilience against real-world threats.

- Staying in the context of cyber security, system administrators benefit from PowerShell scripting for automating integrity checks, managing system configurations, and securing networks, especially in remote or large-scale environments. PowerShell scripts can be designed to enforce security policies, monitor systems health, and respond automatically to security incidents, thus enhancing the overall security posture.

`Invoke-Command`: enables efficient remote management and—combining it with scripting—automation of tasks across multiple machines