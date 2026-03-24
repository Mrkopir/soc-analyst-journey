# Windows Command Line - TryHackMe


## 1. Advantages to useing CLI

### Lower resource usage: CLIs require fewer system resources than graphics-intensive GUIs. In other words, you can run your CLI system on older hardware or systems with limited memory. If you are using cloud computing, your system will require lower resources, which in turn will lower your bill.
### Automation: While you can automate GUI tasks, creating a batch file or script with the commands you need to repeat is much easier.
### Remote management: CLI makes it very convenient to use SSH to manage a remote system such as a server, router, or an IoT device. This approach works well on slow network speeds and systems with limited resources.

## 2. How to find Basic System Info

- `set`: to check a path from the command line.

- `ver`: command to determine the operating system (OS) version. 

- `systeminfo`: command to list various information about the system such as OS information, system details, processor and memory.

## 3. Network Troubleshooting

### `ipconfig`: 
to check the network information. Flag `/all` output more info.

### `ping`: 
send a specific ICMP packet and listen for a response. If a response is received, we know that we can reach the target and that the target can reach us.

### `tracert`: 
traces the network route traversed to reach the target.

### `nslookup`:
It looks up a host or domain and returns its IP address.

### `netstat`:
command displays current network connections and listening ports. 
Flags: 
- `-a` displays all established connections and listening ports; 
- `-b` shows the program associated with each listening port and established connection; 
- `-o` reveals the process ID (PID) associated with the connection; 
- `-n` uses a numerical form for addresses and port numbers; 
- `-h` displays the help page.

To combine flags use: `netstat -abon`

## 4. File and Disk Management

### `cd`:
It is needed for walk through the file system. To go back use `cd ..`. Like in linux terminal

### `dir`:
It stands for "print working directory", which basically means "show me the folder I'm currently in". Flag `/a` shows hiden files. Flag `/s <file-name>` find files on disk.

### `tree`:
To visually represent the child directories and subdirectories.

### `mkdir`:
Stands for make directory

### `type`:
It is needed to read file.

### `move`:
To Move files.

### `del` or `erase`:
To Delete a File

## 5. Task and Process Management

### `tasklist`:
To print list the running processes. Flag `/FI` used to set the filter image name equal.

### `taskkill /PID target_pid`:
To terminate any task.

### `chkdsk`: 
Checks the file system and disk volumes for errors and bad sectors.

### `driverquery`: 
Displays a list of installed device drivers.

### `sfc /scannow`: 
scans system files for corruption and repairs them if possible.