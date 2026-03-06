## Table of Contents 
1. GUIs
2. net commands (CLI)
3. PowerShell commands
4. eventlog commands
5. scheduled tasks

### Focus: User & Group Management
Effective user and group management is essential for ensuring secure access to resources, simplifying administrative tasks, and maintaining overall system integrity. 

## Management Methods (Possible ways to interact with users and groups)

### 1. Graphical User Interface (GUI):
  - Navigate to Control Panel
  - Navigate to User Accounts
  - Navigate to Manage User Accounts


### 2. Command Line Interface (CLI):

net.exe is a suite of commands that can be used in the CLI to manage users and groups. Note: These commands will also work in PowerShell although they are not inate POSH cmdlets.
net commands

|Task                  |          Example                  |
|:------------------------------------------:|:-----------------------------------------------:|
|Add a user                                 | `net user username password /add`                                  |
|Add domain user                          | `net user username password /add /domain`                              |
|Add a local group:                         | `net localgroup groupname /add`                            |
|Add domain local group:                  | `net localgroup groupname /add /domain`                        |
|Add domain global group:                  |  `net group groupname /add /domain`                              |

> Note:
> - Domains Local Groups: These groups can contain members from any trusted domain, but are granted permissions only to resources in their own domain
> - Domain Global Groups: These groups contain members only from their own domain but can be granted permissions to resources in any trusting domain.

### 3. PowerShell:

|Task                  |          Example                  |
|:------------------------------------------:|:-----------------------------------------------------------------------------:|
|Create a local User:                       | New-LocalUser –Name "username" -Password (ConvertTo-SecureString "Password12345!" -AsPlainText -Force) |
|Create a local group:  | New-LocalGroup –Name "groupname"          |

### 4. Accessing Logs:

Open the command line and type powershell, or navigate to the PowerShell interface by typing powershell in the search bar.

|Task                  |          Example                  |
|:------------------------------------------:|:-----------------------------------------------------------------------------:|
|To view all logs, type:                  | `Get-EventLog *`         (The asterisk is a wildcard and shows all logs.) |
|To view specific logs, type:             | Get-EventLog <log name>  Example: `Get-EventLog Application`  |
|To clear a specific log, type:     |       Clear-EventLog <log name>    Example: `Clear-EventLog Application`  |

> Note: If you clear your logs and then use the get-eventlog cmdlet to grab those logs, you should get a red error message that states there are no logs - which is correct because you just deleted them.
Event Viewer is the GUI used to view these logs. 
If you open Event Viewer and navigate to the Windows Logs tab you should see the same logs. You are free to explore this GUI to see how it works compared to CLI/POSH.

### 5. Scheduled Tasks:

Common schtasks Commands:

|Task                  |        Description                 |            Example                 |
|:------------------------------------------:|:--------------------------------:|:---------------------------------------------:|
|`schtasks /?`                  |  Displays scheduled tasks and command usage.                        |
|`schtasks /create`              |   Creates a new task.                       | Example:      `schtasks /create /sc once /tn command /tr cmd.exe /st 08:00` (Schedules a one-time task to run cmd.exe at 08:00)     |
|`schtasks /delete`            |  Deletes a task by name.                        |  Example:     `schtasks /delete /tn command`    |
|`schtasks /change`          |  Changes the task that is run (does not change the task name).   |  Example:  `schtasks /change /tn Notepad /tr C:\Windows\System32\calc.exe` (Changes the scheduled task to run calc.exe instead of Notepad)  |
|`schtasks /query`   |    Displays current scheduled tasks.   |  Example:  `schtasks /query /tn Notepad /v /fo list`  (Displays detailed information about the Notepad task)    |

> Task Scheduler is the GUI used to view these tasks
The current tasks are shown in the middle pane. To the right you can see options to create, run, disable etc. other tasks. You are free to explore this GUI to see how it works compared to CLI/POSH.


