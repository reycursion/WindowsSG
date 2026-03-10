## Table of Contents 
1. services
2. 

### 1. Windows Services

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

### Service Management Console Overview
Once the Services window is open, you’ll see a list of all services running on the system. This window typically displays the following information for each service: 
* Name: The name of the service (e.g., Windows Update, Print Spooler).
* Description: A brief description of what the service does.
* Status: Whether the service is currently running, stopped, or paused.
* Startup Type: The configuration of the service’s startup behavior. This can be set to:
  * Automatic: Starts when the system boots.
  * Manual: Starts only when specifically requested.
  * Disabled: The service will not start.
* Log On As: The account under which the service is running (e.g., Local System, Network Service, or Local Service).
