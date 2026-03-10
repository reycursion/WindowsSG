## Table of Contents 
1. NetBIOS
2. nbtstat
3. net commands
4. Control Panel

### 1. NetBIOS

NetBIOS (Network Basic Input/Output System) is an Application Programming Interface (API) that enables communication between applications running on different computers within a local area network (LAN).

NetBIOS uses specific ports for its operations:

* **Name Service (TCP Port 137):**
* **Session Service (TCP Port 139):**
* **Datagram Service (UDP Port 138):**

### 2. nbtstat command

NetBIOS communication can be monitored and troubleshooted using several tools, with the nbtstat command being one of the most commonly used for **diagnostic** purposes. This command allows administrators to view and troubleshoot NetBIOS over TCP/IP issues.


|Command               |          Description                | Other Examples
|:------------------------------------------|:---------------------------------|:----------------------------|
|`nbtstat -n `   |  This command lists the local NetBIOS names registered on the system. It provides details about the names and their associated network addresses, which can help diagnose naming issues or conflicts on the network. |        |
|`nbtstat -a [IP Address]`   | This command queries remote machines for their NetBIOS names and associated network information by providing either the IP address or NetBIOS name. This is useful for identifying devices on the network and checking for connectivity issues with a specific machine. |  `nbtstat -a 192.168.1.10`|
|`nbtstat -r` |  This command displays the NetBIOS name resolution cache, which shows how the system has resolved names in the past, including entries that are no longer active. |      |
|`nbtstat -S`  |  This displays the active NetBIOS sessions (connections) that the local machine is maintaining, along with session statuses, helping to diagnose issues related to active connections between devices.|      |

### 3. net commands extened version

#### Common Net.exe Commands
Here’s a breakdown of some essential commands available through Net.exe and their functions:

|Command               |          Description                | Other Examples
|:------------------------------------------|:---------------------------------|:----------------------------|
|`net /?`   |  Displays the help page for the Net.exe command, listing all available commands and their syntax.  |   |
|`net user`  | Manages user accounts on the local machine or a domain. Administrators can add, delete, modify, or display user account information. | <ul><li>Add a new user: `net user JohnDoe P@ssw0rd /add` (Creates a new user "JohnDoe" with password "P@ssw0rd")</li><li>Delete a user: `net user JohnDoe /delete` (Removes the user "JohnDoe")</li><li>Display all users: `net user` (Lists all user accounts on the machine)</li></ul>  |
|`net localgroup` | Manages local groups and their members. Allows adding or removing users from groups and viewing group membership.  |  <ul><li>Add a user to a group: `net localgroup administrators JohnDoe /add` (Adds "JohnDoe" to the "Administrators" group)</li><li>Remove a user from a group: `net localgroup administrators JohnDoe /delete` (Removes "JohnDoe" from the "Administrators" group)</li></ul> |
|`net share` | Manages shared network resources such as folders, printers, and devices. Displays shared resources or configures new shares. |<ul><li>Create a shared folder: `net share Documents=C:\Users\JohnDoe\Documents` (Shares the "Documents" folder)</li><li>List all shared resources: `net share`</li><li>Remove a shared folder: `net share Documents /delete` (Removes the shared "Documents" folder)</li></ul> |
|`net start` | Starts services on the local machine. This is useful for managing background services like networking, file sharing, or system processes.| `net start spooler` (Starts the Print Spooler service)  |
|`net stop` |  Stops services on the local machine. This is useful for managing background services like networking, file sharing, or system processes. | `net stop spooler` (Stops the Print Spooler service)  |
|`net use`  | Connects to or disconnects from a shared resource on the network. It can also display information about currently mapped network drives and connections. |<ul><li>`net use Z: \\Server01\Documents` (Maps the shared folder "Documents" on "Server01" to the Z: drive) </li><li>Disconnect a network drive: `net use Z: /delete` (Disconnects the Z: network drive) </li><li>Display all mapped network drives: `net use` (Lists all currently mapped network drives and connections)</li></ul> |
|`net session` | Displays information about the sessions that are currently open on the machine. This can be useful for monitoring active connections and troubleshooting network issues. | View active sessions: `net session` (Lists all active network sessions on the local machine) |
|`net time` | Synchronizes the system time with a network time server, ensuring that the machine's clock is accurate and synchronized with a trusted source.  | Synchronize time with a time server: `net time \\time.windows.com /set` (Synchronizes the local computer's time with "time.windows.com")
|`net file` | Manages open files on the network, including displaying a list of files currently being accessed and the ability to close them. | <ul><li>View open files: `net file` (Lists all open files on the local machine or server) </li><li>Close an open file: `net file 123 /close` (Closes the file with ID 123)</li></ul> |

### netstat
Usage: used for network diagnostics and troubleshooting. It provides information about active network connections, open ports, and listening services on the system. It's a useful tool for analyzing network traffic and detecting any unusual activity.
Analyze network traffic for potential issues.

#### Syntax:
* `netstat` — Displays active connections, ports, and other network statistics.
* `netstat -a` — Shows all active connections and listening ports.
* `netstat -n` — Displays network addresses in numeric form (IP address and port number).
* `netstat -o` — Displays active connections and the process ID (PID) using the connection.
* `netstat -b` — Displays the executable involved in creating each connection or listening port.

>Note: Options can be combined. Example: `netstat -ano`

### 4. Control Panel

Open the Control Panel by searching "Control Panel in the search bar
Once open, you can select "category" dropsown and then "small icons". This way you can see a lot more icons.

#### **Network and Sharing Center**
* The Network and Sharing Center is the centralized hub in Windows for managing all network-related settings and configurations. It provides a unified interface where users can view and modify network connections, enable or disable sharing features, and troubleshoot network problems.

Inside the **Network and Sharing Center** you can select **File and Printer Sharing** and **Network Discovery** by clicking "Change advanced sharing settings".
* File and Printer Sharing in Windows enables seamless sharing of files, folders, and printers between computers on the same network.
  *   File Sharing: Users can share folders or individual files, allowing others on the network to read, write, or modify them, based on the set permissions.
  *   Printer Sharing: A printer connected to one computer can be shared with other users on the network, eliminating the need for each user to have a dedicated printer.
* Network Discovery enables your computer to find other devicdes and computers on a network, and allows your computer to be visible to them.

* Manage Network Connections: From the Network and Sharing Center, users can view and configure wired (Ethernet) and wireless (Wi-Fi) network connections, ensuring seamless access to resources.

> There are a lot more settings that can be manipulated/changed/viewed in the control panel. These are just a few that we cover in this module.
