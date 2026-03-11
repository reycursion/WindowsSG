## Table of Contents 
1. LDAP
2. Active Directory
3. Commands CLI & PowerShell

### 1. LDAP 

**LDAP (Lightweight Directory Access Protocol)** is a software protocol designed for accessing and managing directory services over a network.

LDAP Ports
* **Port 389**: This is the default port for non-secure LDAP communication, typically used for unencrypted LDAP traffic.
* **Port 636**: This port is used for Secure LDAP (LDAPS), which encrypts traffic using SSL/TLS, providing an additional layer of security when transmitting sensitive information, such as passwords.

The Naming Model explains how entries are organized and identified within the LDAP directory. Entries are arranged in a hierarchical, tree-like structure known as the **Directory Information Tree (DIT)**. This tree allows for logical grouping and identification of objects.

Each entry in the DIT is uniquely identified by a Distinguished Name (DN), which is a string that uniquely identifies an object within the directory.

Two Types of Names in LDAP:

* Distinguished Name (DN)
  *   Full path of an object within the LDAP directory.
  *   Includes Relative Distinguished Name (RDN) + Directory Location.
  *   Example: CN=Peter Parker, OU=S6, DC=army, DC=com
* Relative Distinguished Name (RDN)
  *   Unique identifier at each directory level.
  *   Does not include full directory structure.
  *   Example: OU=S6
  
LDAP Session Connection:

* Session Connection – User connects to the server via an LDAP port
  *   Port 389: Unencrypted LDAP
  *   Port 636: Encrypted LDAP (SSL/TLS)
  *   (Custom ports can be configured)
* Request – User submits a query (e.g., email lookup) to the server
* Response – LDAP queries the directory and returns requested information
* Completion – User disconnects from the LDAP port

### 2. Active Directory

Active Directory (AD) is a directory service developed by Microsoft, designed to manage and organize network resources in a centralized and hierarchical manner. A directory is essentially a structured database that stores and organizes information about various objects on the network. These objects could include users, groups, computers, printers, and other resources.

The GUI we will use for Active Directory is **Server Manager**
To open Server Manager - navigate to your AD deployment and connect to the DC (Domain Controller). Once it loads, Server Manager should be the first thing to appear. 

> If you happen to close out of Server Manager you can type servermanager.exe in your cmd and press enter to get it back.
> If you happen to close both Server Manager and cmd you should stop closing things and think about a reclass. Just kidding! It happens. Press ctrl+alt+delete to get your task manager, then select "run new task" then type cmd.exe or servermanager.exe depending on what you need.

Inside Server Manager: 
In the top right corner you will see "Tools" - Here is where you can find a lot of the GUIs we previously discussed, along with PowerShell, and a few extras.
For this practical we want to use "Active Directory Users and Computers"
> Make sure you go to View and turn on Advanced Features to ensure you can see everything.

We are going to focus on Users - go to this folder.
Double click a user you want to open. "cvte"
Here you can see a lot of information about this specific user. One portion we talked about earlier was Distinguished Names. To find this, make sure you are in the Attribute Editor tab and scroll down a little bit. 

Creating a new user.
You can do this by right-clicking in the white space next to the existing users, click new, then click user.
Here is where you can create a user account with a logon name so if you want to connect to your Windows 11 client that is attached to this AD deployment you can. (You can still log in as cvte too, just switch user if needed)

### 3. Commands 

There are commands used to navigate/edit objects in Active Directory. Note these will only work in your AD deployment. 

CLI Directory Service Commands

|Command               |          Description                |
|:------------------------------------------|:-----------------------------------------------------------------------------|
|`Dsadd` |  Adds objects to the directory|
|`Dsquery` | Queries Active Directory based on criteria|
|`Dsmod` | Modifies existing directory objects|
|`Dsmove` | Moves or renames objects in the directory|
|`LDP` | Performs LDAP operations like bind, search, modify, and delete|

Network Commands

|Command               |          Description                |
|:------------------------------------------|:-----------------------------------------------------------------------------|
|`Net computer` | Adds or removes a computer from a domain|
|`Net group` | Manages global groups in a domain|
|`Net user` | Adds, modifies, or displays user accounts|


Active Directory PowerShell User & Group Management Commands:


|Command               |          Description                |
|:------------------------------------------|:-----------------------------------------------------------------------------|
|`Add-ADGroupMember` | Adds members to an AD group|
|`Enable/Disable-ADAccount` | Enables or disables an AD account|
|`Get-ADUser` | Retrieves one or more AD users|
|`Get-ADGroup` | Retrieves one or more AD groups|
|`Get-ADGroupMember` | Retrieves members of an AD group|

Computer & Domain Management

|Command               |          Description                |
|:------------------------------------------|:-----------------------------------------------------------------------------|
|`Get-ADComputer` | Retrieves one or more AD computers|
|`Get-ADDomain` | Retrieves AD domain details|
|`Get-ADDomainController` | Retrieves AD domain controllers|
|`Get-ADForest` | Retrieves the AD forest|
|`Get-ADOrganizationalUnit` | Retrieves one or more AD OUs|

> If you use these commands it may prompt you for a filter. If you input "*" it will show you all of them.
