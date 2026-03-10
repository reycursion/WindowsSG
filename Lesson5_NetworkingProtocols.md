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
|`net user`  | Manages user accounts on the local machine or a domain. Administrators can add, delete, modify, or display user account information. | Add a new user: net user username password /add  net user JohnDoe P@ssw0rd /add (Creates a new user "JohnDoe" with password "P@ssw0rd") |
|   |    |   Delete a user: net user username /delete  net user JohnDoe /delete (Removes the user "JohnDoe") |
Display all users:
net user
Example:
net user (Lists all user accounts on the machine)
3. net group
Usage: Manages local groups and their members. Allows adding or removing users from groups and viewing group membership.
Example:
Add a user to a group:
net localgroup groupname username /add
Example:
net localgroup administrators JohnDoe /add (Adds "JohnDoe" to the "Administrators" group)
Remove a user from a group:
net localgroup groupname username /delete
Example:
net localgroup administrators JohnDoe /delete (Removes "JohnDoe" from the "Administrators" group)
4. net share
Usage: Manages shared network resources such as folders, printers, and devices. Displays shared resources or configures new shares.
Examples:
Create a shared folder:
net share sharename=path
Example:
net share Documents=C:\Users\JohnDoe\Documents (Shares the "Documents" folder)
List all shared resources:
net share
Example:
net share (Displays all shared resources on the local machine)
Remove a shared folder:
net share sharename /delete
Example:
net share Documents /delete (Removes the shared "Documents" folder)
5. net start / net stop
Usage: Starts or stops services on the local machine. This is useful for managing background services like networking, file sharing, or system processes.
Examples:
Start a service:
net start servicename
Example:
net start spooler (Starts the Print Spooler service)
Stop a service:
net stop servicename
Example:
net stop spooler (Stops the Print Spooler service)
6. net use
Usage: Connects to or disconnects from a shared resource on the network. It can also display information about currently mapped network drives and connections.
Examples:
Map a network drive:
net use Z: \\servername\sharename
Example:
net use Z: \\Server01\Documents (Maps the shared folder "Documents" on "Server01" to the Z: drive)
Disconnect a network drive:
net use Z: /delete
Example:
net use Z: /delete (Disconnects the Z: network drive)
Display all mapped network drives:
net use
Example:
net use (Lists all currently mapped network drives and connections)
7. net session
Usage: Displays information about the sessions that are currently open on the machine. This can be useful for monitoring active connections and troubleshooting network issues.
Examples:
View active sessions:
net session
Example:
net session (Lists all active network sessions on the local machine)
8. net time
Usage: Synchronizes the system time with a network time server, ensuring that the machine's clock is accurate and synchronized with a trusted source.
Examples:
Synchronize time with a time server:
net time \\time.server /set
Example:
net time \\time.windows.com /set (Synchronizes the local computer's time with "time.windows.com")
9. net file
Usage: Manages open files on the network, including displaying a list of files currently being accessed and the ability to close them.
Examples:
View open files:
net file
Example:
net file (Lists all open files on the local machine or server)
Close an open file:
net file fileID /close
Example:
net file 123 /close (Closes the file with ID 123)
10. net share
Usage: Manages shared resources (like folders or printers) on a Windows system. You can use it to create, display, or manage shares, such as shared folders or drives, on the computer.
Syntax:
net share — Displays all shared resources on the computer.
net share [share_name] — Displays information about a specific shared resource.
net share [share_name]=[folder_path] — Shares a folder on the network.
net share [share_name] /delete — Deletes a network share.
11. netstat
Usage: used for network diagnostics and troubleshooting. It provides information about active network connections, open ports, and listening services on the system. It's a useful tool for analyzing network traffic and detecting any unusual activity.
Analyze network traffic for potential issues.
Syntax:
netstat — Displays active connections, ports, and other network statistics.
netstat -a — Shows all active connections and listening ports.
netstat -n — Displays network addresses in numeric form (IP address and port number).
netstat -o — Displays active connections and the process ID (PID) using the connection.
netstat -b — Displays the executable involved in creating each connection or listening port.


### 4. Control Panel
