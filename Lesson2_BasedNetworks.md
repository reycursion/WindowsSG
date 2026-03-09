## Table of Contents 
1. Security Identifier(SID)

SIDs are structured in a specific format that conveys meaningful information. A typical SID might look like this: S-1-5-21-3623811015-3361044348-30300820-1013. Each segment of this string plays a vital role in identifying the account and its attributes:

* S: This prefix denotes that the identifier is a Security Identifier.
* 1: Represents the revision level, indicating the version of the SID format. Currently, this value is 1 and has not changed.
* 5: The authority identifier, which generally corresponds to the security authority that created the SID. The most common authority is 5, representing the NT Authority, but other values can indicate different authorities.
* 1-2-3: The next three SubAuthority arrays contain 32-bit random numbers to uniquely identify the domain.
 *Local or Domain Identifier: This segment specifies the security authority that issued the SID, indicating whether it belongs to a local or domain account.
* Relative Identifier (RID): The RID identifies the specific type of account, whether it is a user account, group account, or other defined types.

## Well-Known SIDs: These predefined SIDs represent standard accounts within the system that have specific, commonly understood roles. For example:

|SID Value         |  Description         |
|:------------------------------------------|:-----------------------------------------------------------------------------|
|NULL S-1-0-0     |    No Security principal. Used when the SID is unknown.  |
|EVERYONE S-1-1-0    | WORLD. A group that includes all users.   |
|LOCAL S-1-2-0   |    A group that includes all users who have physically logged on locally.   | 
|NT_AUTHORITY S-1-5  |   A SID containing only the SECURITY_NT_AUTHORITY identifier authority.   |
|LOCAL_SYSTEM S-1-5-18 |  An account that is used by the operating system.  |
|LOCAL_SERVICE S-1-5-19  |  A local service account, which has limited privileges for running local services without access to network resources. |
|NETWORK_SERVICE S-1-5-20   |  A network service account, which has more privileges than the Local Service account, specifically designed for services requiring network access. | 
|ADMINISTRATOR   S-1-5-21-\<machine\>-500 | A user account for the system administrator. By default, it is the only user account that is given full control over the system.   |
|GUEST  S-1-5-21-\<machine\>-501   |  A user account for people who do not have individual accounts. This user account does not require a password. By default, the Guest account is disabled.  |
|KRBTGT S-1-5-21-\<domain\>-502 |  A service account that is used by the Key Distribution Center (KDC) service.  |

More extensive list: https://learn.microsoft.com/en-us/openspecs/windows_protocols/ms-dtyp/81d92bba-d22b-4a8c-908a-554ab29148ab

## Ways to access SIDs

CLI/PowerShell:

|Command               |          Description                |
|:------------------------------------------|:-----------------------------------------------------------------------------|
|`whoami /user`      |This will show your username and associated SID.    |
|`wmic useraccount get name, sid`       |This will show you all of the names and associated SIDs of the current users on your system.    |
|`wmic useraccount where name='username' get sid`    | Replace "username" with a specific username to see the associated SID    |
|`Get-CimInstance Win32_UserAccount \| Select Name, SID`     |  This a POSH cmdlet that will also give you all of the names and SIDs of the users on your system.    |

> Note: The WMI command-line (WMIC) utility provides a command-line interface for Windows Management Instrumentation (WMI). 
WMIC is deprecated as of Windows 10, version 21H1; and as of the 21H1 semi-annual channel release of Windows Server. This utility is superseded by Windows PowerShell for WMI.

> The Get-CimInstance cmdlet gets the CIM instances of a class from a CIM server. You can specify either the class name or a query for this cmdlet. 
This example retrieves the CIM instances of a class named Win32_Process. You will learn more about these in your PowerShell module.

***SIDs can also be viewed in the Registry and the Server Manager which we will cover in future lessons.***
