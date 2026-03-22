# Windows Fundamentals 3 - TryHackMe

## 1. Windows Updates

Windows Update is a service provided by Microsoft to provide security updates, feature enhancements, and patches for the Windows operating system and other Microsoft products, such as Microsoft Defender. 

Updates are typically released on the 2nd Tuesday of each month. This day is called Patch Tuesday. That doesn't necessarily mean that a critical update/patch has to wait for the next Patch Tuesday to be released. If the update is urgent, then Microsoft will push the update via the Windows Update service to the Windows devices.

**Tip: Another way to access Windows Update is from the Run dialog box, or CMD, by running the command `control /name Microsoft.WindowsUpdate`**

## 2. Windows Security

**Windows Security**: is your home to manage the tools that protect your device and your data.

**Windows Security** is available in **Settings**.

Protection areas:

- Virus & threat protection
- Firewall & network protection
- App & browser control
- Device security

Status icons:

- Green means that device is sufficiently protected, and there aren't any recommended actions.
- Yellow means there is a safety recommendation to review.
- Red is a warning that something needs immediate attention.

### 1. Virus & threat protection

Virus & threat protection is divided into two parts:

- Current threats
- Virus & threat protection settings

#### Current threats

Scan options:

- Quick scan - Checks folders in your system where threats are commonly found.
- Full scan - Checks all files and running programs on your hard disk. This scan could take longer than one hour.
- Custom scan - Choose which files and locations you want to check.

Threat history:

- Last scan - Windows Defender Antivirus automatically scans your device for viruses and other threats to help keep it safe.
- Quarantined threats - Quarantined threats have been isolated and prevented from running on your device. They will be periodically removed.
- Allowed threats - Allowed threats are items identified as threats, which you allowed to run on your device. 

#### Virus & threat protection settings

Manage settings:

- Real-time protection - Locates and stops malware from installing or running on your device.
- Cloud-delivered protection - Provides increased and faster protection with access to the latest protection data in the cloud.
- Automatic sample submission - Send sample files to Microsoft to help protect you and others from potential threats. 
- Controlled folder access - This feature, if enabled, protects files, folders, and memory areas on your device from unauthorized changes by malicious or unknown applications. If it is enabled, only approved and trusted apps would be allowed to modify the files in the protected folders. To enable this feature, click on the Manage controlled folder access button under Controlled Folder Access and turn it on. 
- Exclusions - Windows Defender Antivirus allows you to exclude any files or folders from the antivirus scanning. This is done to reduce the number of false positives. Administrators might not want the antivirus to scan specific files or folders. By adding them to the exclusions list, the antivirus would ignore them and scan all the other files and folders. To add any file or folder to the Windows Defender exclusion list, click on the Add or remove exclusions button under Exclusions and add as many exclusions as you want. 
- Notifications - Windows Defender Antivirus will send notifications with critical information about the health and security of your device. 

#### Virus & threat protection updates

Check for updates - Manually check for updates to update Windows Defender Antivirus definitions.  

#### Ransomware protection

Controlled folder access - Ransomware protection requires this feature to be enabled, which in turn requires Real-time protection to be enabled.

### 3. Firewall & Network protection

Firewall: Traffic flows into and out of devices via what we call ports. A firewall is what controls what is - and more importantly isn't - allowed to pass through those ports. You can think of it like a security guard standing at the door, checking the ID of everything that tries to enter or exit

Windows Firewall offers three firewall profiles:

- Domain - The domain profile applies to networks where the host system can authenticate to a domain controller. 
- Private - The private profile is a user-assigned profile and is used to designate private or home networks.
- Public - The default profile is the public profile, used to designate public networks such as Wi-Fi hotspots at coffee shops, airports, and other locations.

### 4. App & Browser control

**Microsoft Defender SmartScreen protects against phishing or malware websites and applications, and the downloading of potentially malicious files**

You can see the status of the smart screen set to Warn below. You can also change it to either Block or completely turned Off.

#### Check apps and files

Windows Defender SmartScreen helps protect your device by checking for unrecognized apps and files from the web. 

#### Exploit protection

Exploit protection is built into Windows 10 (and, in our case, Windows Server 2019) to help protect your device against attacks. 

### 5. Device Security

#### Core isolation

Memory Integrity: Prevents attacks from inserting malicious code into high-security processes.

#### What is the Trusted Platform Module (TPM)?

Per Microsoft, "Trusted Platform Module (TPM) technology is designed to provide hardware-based, security-related functions. A TPM chip is a secure crypto-processor that is designed to carry out cryptographic operations. The chip includes multiple physical security mechanisms to make it tamper-resistant, and malicious software is unable to tamper with the security functions of the TPM".

## 3. BitLocker

BitLocker Drive Encryption is a data protection feature that integrates with the operating system and addresses the threats of data theft or exposure from lost, stolen, or inappropriately decommissioned computers.

## 4. Volume Shadow Copy Service

Volume Shadow Copy Service (VSS) coordinates the required actions to create a consistent shadow copy (also known as a snapshot or a point-in-time copy) of the data that is to be backed up. 

Volume Shadow Copies are stored on the System Volume Information folder on each drive that has protection enabled.

If VSS is enabled (System Protection turned on), you can perform the following tasks from within advanced system settings. 

- Create a restore point
- Perform system restore
- Configure restore settings
- Delete restore points