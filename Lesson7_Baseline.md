## Table of Contents 
1. Survey Commands
2. Creating a Baseline


### 1. Survey Commands

Survey commands are commonly used by system administrators, incident responders, and forensic investigators to gather important system information during an investigation or while troubleshooting a system. These commands help to quickly assess the state of the system, identify running processes, network activity, disk usage, system information, and other critical data. Below are some of the most frequently used survey commands in Command Prompt (CMD) and PowerShell.

#### System Information
| Command	| Purpose	|   Example Usage  |
|:------------------------------------------|:----------------------------------------|:-------------------------------------|
|`systeminfo` | Displays detailed system information	  | `systeminfo` |
|`hostname` |	Shows the computer's hostname  |	`hostname` |

#### Process Information
| Command	| Purpose	|   Example Usage  |
|:------------------------------------------|:-----------------------------------------|:------------------------------------|
|`tasklist`	| Lists all running processes  |	`tasklist` |
|`Get-Process`  | Retrieves all running processes in PowerShell |	`Get-Process` |

#### Network Information	
| Command	| Purpose	|   Example Usage  |
|:------------------------------------------|:------------------------------------|:-----------------------------------------|
|`netstat` |	Shows active network connections and ports |	`netstat -ano` |
|`ipconfig`	| Displays network configuration information |	`ipconfig` |
|`Get-NetTCPConnection`	| Lists active TCP/IP connections |	`Get-NetTCPConnection` |

#### Service Information	
| Command	| Purpose	|   Example Usage  |
|:------------------------------------------|:--------------------------------------|:---------------------------------------|
|`sc query`	 | Queries the status of services | `sc query` |
|`Get-Service`	| Lists all installed services in PowerShell |	`Get-Service` |

#### File System	
| Command	| Purpose	|   Example Usage  |
|:------------------------------------------|:----------------------------------|:-------------------------------------------|
|dir |	Lists files and directories	 | dir C:\Windows |
|Get-ChildItem	|Lists files and directories in PowerShell	| Get-ChildItem -Path C:\Windows|

### 2. Creating a Baseline

One way to do a baseline is to save a copy of your current configurations to a file > this is your baseline. At a later time you can compare that file to the new current configurations.

Let's try with PowerShell:

A pretty simple way is to just run:

`Get-Process | Export-Clixml -Path C:\Documents\Baseline01.xml`

> This saves the current process to an xml document named Baseline01.xml

`Get-Process | Export-Csv -Path C:\Documents\Baseline01.csv`

> This saves the current process to a csv document named Baseline01.csv if you want the file to be formatted like a spreadsheet to open in Libre Calc or Microsoft Excel

`Get-Service | Export-Clixml -Path C:\Documents\Baseline01.xml`

> This will add all of the services on your system to the already existing file named Baseline01.xml

To compare this file later you can do the same previous actions but save the file with a new name (Baseline02.xml)
Then you can run the following command:

```Compare-Object -ReferenceObject $(get-content -path "C:\Users\cvte1\Documents\Baseline01.xml") -DifferenceObject $(get-content -path "C:\Users\cvte1\Documents\Baseline02.xml")```

* <= means the item appeared only in the reference object/document
* => means the item appeared only in the difference object/document
* == means the item is present in both objects/documents

Another way is to hash the files and create an if statement to compare them. You will learn more about if statements in the PowerShell module.

example:

`$FileHash01 = Get-FileHash -Path "C:\Users\cvte1\Documents\Baseline01.xml"
#echo $FileHash01
$ExpectedHash = "put your hash here"

if ($FileHash01 -eq $ExpectedHash) {
write-output "The file hashes match" }
else 
{ 
write-output "The file hashes do not match" }`

> Note: Might need to run the echo $FileHash01 first to get the input for the $ExpectedHash
