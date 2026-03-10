## Table of Contents 
1. services
2. services.msc
3. CLI commands
4. PowerShell cmdlets

### 1. Windows Services

Windows Services are specialized applications designed to run in the background of a Windows operating system, executing long-running tasks that do not require direct user interaction. Unlike regular applications that typically run in the foreground with a graphical user interface (GUI), Windows services operate invisibly, allowing the system to perform essential functions while the user is working or even when no user is logged in.

* The **Service Control Manager (SCM)** is the central management service for all Windows services.
* **Service Control Programs (SCPs)** are the tools used to interact with and manage services on a Windows system. These can include graphical user interfaces (GUIs), command-line tools, or PowerShell scripts.
  * The most common GUI SCP is **services.msc**
  * The most common scripting SCP is **PowerShell or CLI**
* Launching the Services Tool
  * Open the Start Menu: Click on the Start button or press Win + S.
  * Search for Services: Type “services” into the search box.
  * Run as Administrator: Click on "Services" from the search results, then select “Run as Administrator” to open the Services management console.
* Launching PowerShell or CLI
  * Start menu’s Run dialog: Open the Run window (by pressing Win + R), type powershell or cmd, and press Enter.
  * Or you could start typing "PowerShell" or "cmd" in the search bar and it will appear.
> Tip: It is best practice to open your CLI or PowerShell as administrator because some commands will not run without escalated privileges.

### Service Management Console Overview
Once the Services window is open, you’ll see a list of all services running on the system. This window typically displays the following information for each service: 
* Name: The name of the service (e.g., Windows Update, Print Spooler).
* Description: A brief description of what the service does.
* Status: Whether the service is currently running, stopped, or paused.
* Startup Type: The configuration of the service’s startup behavior. This can be set to:
  * Automatic: Starts when the system boots.
  * Automatic Delayed Start: Starts shortly after the boot process.
  * Manual: Starts only when specifically requested.
  * Disabled: The service will not start.
* Log On As: The account under which the service is running (e.g., Local System, Network Service, or Local Service).

Inside this GUI you can start services, stop them, change the startup type, see information about the service, etc. The General page is where you will find a lot of necessary information. Use this page to answer some of your PE's.

### CLI uses the sc.exe suite or net.exe suite 

Some example commands we can use are 

- `net-start` 
- `net-stop` 
- `sc-start`
- `sc-stop`

> Note: If using sc in PowerShell you must use sc.exe.

### PowerShell has many ways to manipulate the services as well.

First, to see the services, type `get-service` 
This will show you the service name, display name, and status 

If you want to see any other categories for the services start typing `get-service | where` then press ctrl + space and you will see the other categories that posh doesn't show you by default. 

Notice with the `get-service` command, the startup type is actually called the starttype - this is important to note when trying to change this value because posh does not recognize startuptype as an option.

Lets focus on a sepcific service to manipulate. 
We will use the service "XboxNetApiSvc". To gather information on this specific service I can do: 
get-service XboxNetApiSvc

From here I can pipe and use `select` or `select-object` to see specifically, the name, startup type, and status properties:
get-service XboxNetApiSvc | select name, StartType, status

The current startup type for this service is Manual and the status is Stopped. Let's change that.

To change any of these categories we are going to do the following command as an example: 
`set-service -name XboxNetApiSvc -StartupType Automatic -Status Running`

Now rerun the command to get that service name, startup type, and status that we ran earlier. If everything ran correctly you should see the new settings you changed.
