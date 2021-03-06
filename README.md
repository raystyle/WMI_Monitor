# WMI_Monitor
Log newly created WMI consumers and processes

https://www.fireeye.com/blog/threat-research/2016/08/wmi_vs_wmi_monitor.html

Note: You must run PowerShell as administrator before using the script. 
The script requires PowerShell version 3 or above and will run in its current state as two separate PowerShell functions.

1. Open an Administrator PS window and type:

    ```
    Import-Module .\<path to WMIMonitor.ps1>
    
    New-EventSubscriberMonitor 
    ```    
    You should see a message "The new event subscriber has been successfully created!"
    
    In a new PowerShell window, test a process call create function 
    ```    
    wmic process call create "notepad.exe" 
    ```    
2. Check the Application Event log for EID 8. When new WMI process call creates or consumers are created, these events will be recorded in the Details section of the log event

3. To disable logging, open an Administrator PS shell and type:

    ```
    Remove-SubscriberMonitor
    ```
  You should see a message "The event subscriber and all associated WMI objects have been successfully removed."
