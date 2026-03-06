## Table of Contents 
1. reg commands
2. PowerShell cmdlets for registry
3. navigate regedit.exe

### 1. reg commands

Users can perform a variety of tasks, including creating, deleting, and modifying registry keys and values. This is particularly useful for batch operations or automated scripts.

Common Commands:

|Command               |          Description                |
|:------------------------------------------|:-----------------------------------------------------------------------------|
|`reg query`    |   Retrieve registry data from specified keys or values.      |
|`reg add`    |      Add a new registry key or value.      |
|`reg delete`    |    Delete a specified registry key or value.      |
|`reg export` and `reg import`    |    Backup and restore registry data from a file.      |


### 2. PowerShell cmdlets for registry

With cmdlets like `Get-Item`, `Set-Item`, and `Remove-Item`, users can interact with registry keys and values programmatically, providing more flexibility than traditional tools.

Common Cmdlets:

|Command               |          Description                |  Example
|:------------------------------------------|:-----------------------------------------|:------------------------------------|
|`Get-ItemProperty`    |    Retrieve registry values from specified registry keys.    |Example: Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name DevicePath    |
|`Set-ItemProperty`    |Modify existing registry values.    |    Example: Set-ItemProperty -Path "C:\temp\mytestfile.txt" -Name IsReadOnly -Value $true    |
|`New-Item`    |    Create new registry keys.    |     Example: New-Item -Path "HKCU:\Software\MyNewApplication"    |
|`Remove-Item`     |   Delete specified registry keys.    |    Example: Remove-Item -Path C:\Path\To\Your\File.txt    |

### 3. Navigate regedit.exe

This graphical interface is built into Windows, providing a user-friendly way to navigate the complex structure of the Windows Registry.


