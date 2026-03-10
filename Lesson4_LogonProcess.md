## Table of Contents 
1. services
2. c

### 1. services

Windows Services are specialized applications designed to run in the background of a Windows operating system, executing long-running tasks that do not require direct user interaction. Unlike regular applications that typically run in the foreground with a graphical user interface (GUI), Windows services operate invisibly, allowing the system to perform essential functions while the user is working or even when no user is logged in.

* The Service Control Manager (SCM) is the central management service for all Windows services.
* Service Control Programs (SCPs) are the tools used to interact with and manage services on a Windows system. These can include graphical user interfaces (GUIs), command-line tools, or PowerShell scripts.
 * The most common GUI SCP is services.msc
 * The most common scripting SCP is PowerShell
* Launching the Services Tool
 * Open the Start Menu: Click on the Start button or press Win + S.
 * Search for Services: Type “services” into the search box.
 * Run as Administrator: Click on "Services" from the search results, then select “Run as Administrator” to open the Services management console.
* Launching PowerShell
 * Start menu’s Run dialog: Open the Run window (by pressing Win + R), type cmd, and press Enter.
 * Or you could start typing "PowerShell" in the search bar and it will appear.
> Tip: It is best practice to open your PowerShell GUI as administrator because some commands will not run without escalated privileges.
