## Table of Contents 
1. Survey Commands
2. Creating a Baseline


### 1. Survey Commands

Survey commands are commonly used by system administrators, incident responders, and forensic investigators to gather important system information during an investigation or while troubleshooting a system. These commands help to quickly assess the state of the system, identify running processes, network activity, disk usage, system information, and other critical data. Below are some of the most frequently used survey commands in Command Prompt (CMD) and PowerShell.

System Information
|:------------------------------------------|:-----------------------------------------------------------------------------|
| Command	| Purpose	|   Example Usage  |
systeminfo Displays detailed system information	  | systeminfo |
hostname |	Shows the computer's hostname  |	hostname |

Process Information
|:------------------------------------------|:-----------------------------------------------------------------------------|
| Command	| Purpose	|   Example Usage  |
|tasklist	| Lists all running processes  |	tasklist |
|Get-Process  | Retrieves all running processes in PowerShell |	Get-Process |

Network Information	
|:------------------------------------------|:-----------------------------------------------------------------------------|
| Command	| Purpose	|   Example Usage  |
|netstat	Shows active network connections and ports |	netstat -ano |
|ipconfig	| Displays network configuration information |	ipconfig |
|Get-NetTCPConnection	| Lists active TCP/IP connections |	Get-NetTCPConnection |

Service Information	
|:------------------------------------------|:-----------------------------------------------------------------------------|
| Command	| Purpose	|   Example Usage  |
|sc query	 | Queries the status of services |	sc query |
|Get-Service	| Lists all installed services in PowerShell |	Get-Service |

File System	
|:------------------------------------------|:-----------------------------------------------------------------------------|
| Command	| Purpose	|   Example Usage  |
|dir |	Lists files and directories	 | dir C:\Windows |
|Get-ChildItem	|Lists files and directories in PowerShell	| Get-ChildItem -Path C:\Windows|

### 2. Creating a Baseline
