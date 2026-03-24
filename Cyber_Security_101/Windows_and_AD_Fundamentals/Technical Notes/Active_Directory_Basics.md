# Active Directory Basics - TryHackMe

## 1. Windows Domain

**Windows domain** is a group of users and computers under the administration of a given business. The main idea behind a domain is to centralise the administration of common components of a Windows computer network in a single repository called **Active Directory (AD)**. The server that runs the Active Directory services is known as a **Domain Controller (DC)**.

The main advantages of having a configured Windows domain are:

- Centralised identity management: All users across the network can be configured from Active Directory with minimum effort.
- Managing security policies: You can configure security policies directly from Active Directory and apply them to users and computers across the network as needed.

## 2. AD

The core of any Windows Domain is the Active Directory Domain Service (AD DS). This service acts as a catalogue that holds the information of all of the "objects" that exist on your network. Amongst the many objects supported by AD, we have users, groups, machines, printers, shares and many others. Let's look at some of them:

### Users
Users are one of the most common object types in Active Directory. Users are one of the objects known as security principals, meaning that they can be authenticated by the domain and can be assigned privileges over resources like files or printers. You could say that a security principal is an object that can act upon resources in the network.

Users can be used to represent two types of entities:

People: users will generally represent persons in your organisation that need to access the network, like employees.
Services: you can also define users to be used by services like IIS or MSSQL. Every single service requires a user to run, but service users are different from regular users as they will only have the privileges needed to run their specific service.

### Machines

Machines are another type of object within Active Directory; for every computer that joins the Active Directory domain, a machine object will be created. Machines are also considered "security principals" and are assigned an account just as any regular user. This account has somewhat limited rights within the domain itself.

The machine accounts themselves are local administrators on the assigned computer, they are generally not supposed to be accessed by anyone except the computer itself, but as with any other account, if you have the password, you can use it to log in.

Note: Machine Account passwords are automatically rotated out and are generally comprised of 120 random characters.

Identifying machine accounts is relatively easy. They follow a specific naming scheme. The machine account name is the computer's name followed by a dollar sign. For example, a machine named DC01 will have a machine account called DC01$.

### Security Groups

If you are familiar with Windows, you probably know that you can define user groups to assign access rights to files or other resources to entire groups instead of single users. This allows for better manageability as you can add users to an existing group, and they will automatically inherit all of the group's privileges. Security groups are also considered security principals and, therefore, can have privileges over resources on the network.

Groups can have both users and machines as members. If needed, groups can include other groups as well.

Several groups are created by default in a domain that can be used to grant specific privileges to users. As an example, here are some of the most important groups in a domain:

- Domain Admins: Users of this group have administrative privileges over the entire domain. By default, they can administer any computer on the domain, including the DCs.
- Server Operators: Users in this group can administer Domain Controllers. They cannot change any administrative group memberships.
- Backup Operators: Users in this group are allowed to access any file, ignoring their permissions. They are used to perform backups of data on computers.
- Account Operators: Users in this group can create or modify other accounts in the domain.
- Domain Users: Includes all existing user accounts in the domain.
- Domain Computers: Includes all existing computers in the domain.
- Domain Controllers: Includes all existing DCs on the domain.

### Active Directory Users and Computers

To configure users, groups or machines in Active Directory, we need to log in to the Domain Controller and run "Active Directory Users and Computers"

This will open up a window where you can see the hierarchy of users, computers and groups that exist in the domain. These objects are organised in Organizational Units (OUs) which are container objects that allow you to classify users and machines. OUs are mainly used to define sets of users with similar policing requirements.

### Security Groups vs OUs

OUs are handy for applying policies to users and computers, which include specific configurations that pertain to sets of users depending on their particular role in the enterprise.

Security Groups, on the other hand, are used to grant permissions over resources.


## 3. Managing Users in AD

### Delete OU:
To delete the OU, we need to enable the Advanced Features. `View => Advanced Features`: This will show some additional containers and enable to disable the accidental deletion protection. So now `right-click => Properties => Object => disable the protection`.

### Delegation:
**Delegation**: allows you to grant users specific privileges to perform advanced tasks on OUs without needing a Domain Administrator to step in. To give Delegation control `right-click => Delegate Control => Add => Enter name => Okey => Select options => Next => Finish`

## 4. Managing Computer in AD

There is no golden rule on how to organise machines, an excellent starting point is segregating devices according to their use.

1. Workstations: Workstations are one of the most common devices within an Active Directory domain. Each user in the domain will likely be logging into a workstation. This is the device they will use to do their work or normal browsing activities. These devices should never have a privileged user signed into them.

2. Servers: Servers are the second most common device within an Active Directory domain. Servers are generally used to provide services to users or other servers.

3. Domain Controllers: Domain Controllers are the third most common device within an Active Directory domain. Domain Controllers allow you to manage the Active Directory Domain. These devices are often deemed the most sensitive devices within the network as they contain hashed passwords for all user accounts within the environment.


## 5. Group Policies

Windows manages such policies through **Group Policy Objects (GPO)**. **GPOs** are simply a collection of settings that can be applied to OUs. GPOs can contain policies aimed at either users or computers, allowing you to set a baseline on specific machines and identities. To configure GPOs, you can use the Group Policy Management tool.

### Selections GPO:

- Scope: is where the GPO is linked in the AD. Also we can apply **Security Filtering** that they are only applied to specific users/computers under an OU.
- Settings: includes the actual contents of the GPO and lets us know what specific configurations it applies.

To change the Policy: `right-click => Edit`. For Exapmle to change the minimum password length `Computer Configurations -> Policies -> Windows Setting -> Security Settings -> Account Policies -> Password Policy`


### GPO distribution:

GPOs are distributed to the network via a network share called SYSVOL, which is stored in the DC.

Once a change has been made to any GPOs, it might take up to 2 hours for computers to catch up. If you want to force any particular computer to sync its GPOs immediately, we can always run the following command on the desired computer: `gpupdate /force`.

### 6. Authentication Methods

When using Windows domains, all credentials are stored in the Domain Controllers. Whenever a user tries to authenticate to a service using domain credentials, the service will need to ask the Domain Controller to verify if they are correct. Two protocols can be used for network authentication in windows domains:

- Kerberos: Used by any recent version of Windows. This is the default protocol in any recent domain.
- NetNTLM: Legacy authentication protocol kept for compatibility purposes.


### Kerberos

Kerberos authentication is the default authentication protocol for any recent version of Windows. Users who log into a service using Kerberos will be assigned tickets. Users with tickets can present them to a service to demonstrate they have already authenticated into the network before and are therefore enabled to use it.

#### When Kerberos is used for authentication, the following process happens:

The user sends their username and a timestamp encrypted using a key derived from their password to the Key Distribution Center (KDC), a service usually installed on the Domain Controller in charge of creating Kerberos tickets on the network.

The KDC will create and send back a Ticket Granting Ticket (TGT), which will allow the user to request additional tickets to access specific services. The need for a ticket to get more tickets may sound a bit weird, but it allows users to request service tickets without passing their credentials every time they want to connect to a service. Along with the TGT, a Session Key is given to the user, which they will need to generate the following requests.

Notice the TGT is encrypted using the krbtgt account's password hash, and therefore the user can't access its contents. It is essential to know that the encrypted TGT includes a copy of the Session Key as part of its contents, and the KDC has no need to store the Session Key as it can recover a copy by decrypting the TGT if needed.

When a user wants to connect to a service on the network like a share, website or database, they will use their TGT to ask the KDC for a Ticket Granting Service (TGS). TGS are tickets that allow connection only to the specific service they were created for. To request a TGS, the user will send their username and a timestamp encrypted using the Session Key, along with the TGT and a Service Principal Name (SPN), which indicates the service and server name we intend to access.

As a result, the KDC will send us a TGS along with a Service Session Key, which we will need to authenticate to the service we want to access. The TGS is encrypted using a key derived from the Service Owner Hash. The Service Owner is the user or machine account that the service runs under. The TGS contains a copy of the Service Session Key on its encrypted contents so that the Service Owner can access it by decrypting the TGS.

The TGS can then be sent to the desired service to authenticate and establish a connection. The service will use its configured account's password hash to decrypt the TGS and validate the Service Session Key.


### NetNTLM Authentication

NetNTLM works using a challenge-response mechanism. The entire process is as follows:

1. The client sends an authentication request to the server they want to access.
2. The server generates a random number and sends it as a challenge to the client.
3. The client combines their NTLM password hash with the challenge (and other known data) to generate a response to the challenge and sends it back to the server for verification.
4. The server forwards the challenge and the response to the Domain Controller for verification.
5. The domain controller uses the challenge to recalculate the response and compares it to the original response sent by the client. If they both match, the client is authenticated; otherwise, access is denied. The authentication result is sent back to the server.
6. The server forwards the authentication result to the client.

## 6. Trees, Forests and Trusts

As companies grow, so do their networks. Having a single domain for a company is good enough to start, but in time some additional needs might push you into having more than one.

### Trees

Active Directory supports integrating multiple domains so that you can partition your network into units that can be managed independently

### Forests

The union of several trees with different namespaces into the same network is known as a forest.

### Trust Relationships

Having a trust relationship between domains.

The simplest trust relationship that can be established is a one-way trust relationship. In a one-way trust, if Domain AAA trusts Domain BBB, this means that a user on BBB can be authorised to access resources on AAA