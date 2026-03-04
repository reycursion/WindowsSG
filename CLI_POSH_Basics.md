## To familiarize/help with some CLI and POSH (PowerShell) navigation techniques we have listed some common commands and navigating tools here.

### Ways to open the Command Line in Windows:

Start menu’s Run dialog: Open the Run window **(by pressing Win + R)**, type **cmd**, and press **Enter**. 

Another way is by **typing “Command Prompt” or "cmd"** into the Windows **search bar**, where it will appear as an option. 

PowerShell can be opened the same way either through **(pressing Win + R)**, type **powershell**, and press **Enter**.

Or you could start **typing "PowerShell"** in the **search bar** and it will appear.

Tip: It is best practice to open your PowerShell GUI as administrator because some commands will not run without escalated privileges.

## 1. Help Commands
Help Commands are very "help"ful (lol)
In all seriousness, the help commands are some of the most powerful tools to have in your toolbox!

### CLI:
The help function is /?
Example: `dir /?`
  This will give you a help page on the dir command
Example: `reg /?`
  There are many reg commands. If you happen to forget which one you need but can at least remember it starts with reg you can throw a /? on the end and you will see the options you have now.
  From here you can continue to throw /? onto the end to stairstep your way to what you need

The examples portion is typically a lot of people's favorite area of the help pages because it gives you exact examples with descritions including the syntax and what the line of code is doing
The exmaples will be listed at the bottom of the help pages.
Example: `reg query /?`
  Scroll to the bottom of the page to see the examples.

### PowerShell
The help function is get-help
Example: `get-help get-service`
  This will give you a help page on the get-service cmdlet Note: commands in PowerShell are called cmdlets (pronounced commandlets)
The examples portion also exists in POSH. To see the examples you must add -examples on the end of your help command
Example: `get-help get-service -examples`

There is also an option in POSH that allows you to open the help page in a smaller window that has a find function to search for key terms
Example: `get-help get-service -showwindow`

## 2. Helpful Shortcuts
When typing a command and adding an option to it you can press ctrl + spacebar to see all of your options
Example: (type) `get-help get-service -` (then press ctrl + spacebar)
  If you are using PowerShell ISE these will populate for you in a dropdown menu

## 3. Tab completion:
  When typing commands you are able to type the first portion of the command and press the "tab" key to finish out the rest of the command
Example: (start typing) `get-ser` (then press tab) you'll see POSH finishes `get-service` for you
This helps with faster scripting and also with spelling errors. Sometimes we type fast and misspell things that the computer does not recognize. To save yourself trouble just tab complete.
Note: CLI and POSH are not case-sensitive 


## Basic CLI Commands:

**Basic Navigation & File Management:**

| Command                                   | Description                                                        |
|------------------------------------------:|--------------------------------------------------------------------|
|`whoami`                                   | Displays the current logged-in user.                               |
|`dir`	                                    | Lists all files and folders in the current directory.              |
|`cd Documents`	                            | Changes the current directory to “Documents”.  Note: You must be in Documents parent folder in order to cd into Documents or use the absolute path.      |
|`cd ..`	                                  | Moves up one directory level.                                        |
|`mkdir Reports`	                          | Creates a new folder named “Reports”.                              |
|`rmdir Reports`	                          | Removes a folder named “Reports”.                                  |
|`type nul > example.txt`                   | Creates an empty file named "example.txt"                          |
|`echo "This is a file." > example.txt`     | Creates a file with the contents: This is a file.                    |
|`notepad example2.txt`                     | Creates a file named "example2.txt" that you can edit in notepad      |
|`del example.txt`	                        | Deletes a file named “example.txt”.                                  |
|`copy file1.txt C:\Downloads`	            | Copies a file to another location.                                    |
|`move file1.txt C:\Downloads`	            | Moves a file to a different folder.                                  |

**System Information & Diagnostics:**

`systeminfo`                                Displays detailed configuration info about the system.
`ipconfig	`                                 Shows IP configuration for network interfaces.
`ping google.com`                         Tests network connectivity to a remote server.
`tasklist`                                 Lists all currently running processes.



## Basic PowerShell Commands:

| Command                                   | Description                                                        |
|------------------------------------------:|--------------------------------------------------------------------|
|`Get-Help`                                 | Displays help information about PowerShell cmdlets.                  |
|`Update-Help`                              | To update your Help File  Note: Update-Help -force will force the update      |
|`Get-Command`                              | Lists all cmdlets, functions, workflows, aliases installed on your system.    |
|`Get-ChildItem`                            | Displays the files and directories in the PowerShell console.            |
|`Get-Process`	                            | Retrieves the processes running on a local or remote computer.            |
|`Get-Service`                              | Gets the status of services on a local or remote machine.              |
|`New-Item`                                 | Creates a new item, such as a file or directory.                      |
|`Copy-Item`                                | Copies an item from one location to another.                          |
|`Remove-Item`                              | Deletes files or directories.                                    |

It is possible to switch to PowerShell from you CLI by simply typing the word "powershell" in your CLI. If you type "cmd" it will take you another logical layer deeper into another CLI shell. 
Note: It is easy to get many layers deep if you continue to do this. To go back a layer to your previous shell, type the word "exit". If you type exit from your original shell you will close out your CLI. So be careful not to type exit too many times.
Certain variables, functions, etc. that you create may only exist in that session. If you close they will delete from memory unless saved in your profile file, which will be covered in your PowerShell module.

Important Note: Read your error messages!! Often times people see a red error message and wonder what they did wrong or just give up. Read the error message because often times it tells you exactly what is wrong and maybe even how to fix the issue.

