# Forensics

## File Analysis

**Tools**:
- Foremost
- Binwalk
- PDF
  - qPDF
  - xpdf
## Ransomware

**Tools**:
- RakhniRecryptor - https://support.kaspersky.com/common/disinfection/10556

## Windows

### Imaging

**Important Files and Folders**:
- C:/Windows/System32/NetworkList - NLA
- C:/Windows/CSC - CSC

### Memory Forensics

**Tools**:
- Volatility 3 (Must be run with sudo first time to create symbol table

### Registry

**Tools**:
- regedit.exe - Windows built-in explorer
- Registry Explorer - Explorer by Eric Zimmerman
- cafae.exe
- RegRipper
- SAMInside - Parse information about users profile
- DCode Date Tool - Decode registry timestamp

**Location**:
- C:/Windows/system32/config/ - HKLM
- C:/Users/<Username>/NTUSER.dat - HKCU
- C:/Users/<Username>/AppData/Local/Microsoft/Windows/USRCLASS.dat - HKCU\SOFTWARE\Classes


**Important Registries**
- User Logins
  - HKLM\SAM\Domains\Account\Users\ - Users, Last login, Last password change, Number of login, Number of login failure
- System Configurations
  - HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion - Windows OS Version Information
  - HKLM\SYSTEM\Select - Control Sets
  - HKLM\SYSTEM\CurrentControlSet - Current Control Set
    - HKLM\SYSTEM\CurrentControlSet\Control\ComputerName\ComputerName - Computer Name
    - HKLM\SYSTEM\CurrentControlSet\Control\TimeZoneInformation - Time Zone
    - HKLM\SYSTEM\CurrentControlSet\Control\FileSystem\NtfsDisableLastAccessUpdate
    - HKLM\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\Interfaces - List of network interfaces and IP addresses
    - HKLM\SYSTEM\CurrentControlSet\Services\LanmanServer\Shares - Network shares
    - HKLM\SYSTEM\CurrentControlSet\Control\Windows - Shutdown time
    - HKLM\SYSTEM\CurrentControlSet\Control\Watchdog\Display - Shutdown Count (Windows XP)
  - Networks
    - HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Signatures - Previously Connected Network and Domains (MAC Address can be used for Geolocation via WiGLE.net)
    - HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Nla\Cache - NLA Cache
    - HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\HomeGroup - NLA Information
    - HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Profiles - First and last connection time to the network
      - NameType
        - 0x47 - Wireless
        - 0x06 - Wired
        - 0x17 - Broadband
      - Category
        - 0x00 - Public
        - 0x01 - Private/Home 
        - 0x02 - Domain/Work
  - Autostarts
    - HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Run
    - HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\RunOnce
    - HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Run
    - HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\RunOnce
    - HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\Explorer\Run
    - HKLM\SYSTEM\CurrentControlSet\Services\ - If "Start" value is set to "0x02", it will run
- User Activity
  - Search History
    - HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\WordWheelQuery - Explorer search history
    - HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\TypedPaths - Manually typed path
  - Opened File
    - HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs - Recently opened file path
    - HKCU\SOFTWARE\Microsoft\Office\<Version>\<Program>\FileMRU - Recently opened file using Office softwares
    - HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\LastVisitedPidlMRU - Executable used to open the Open\Save explorer dialogue popup
    - HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSavePidlMRU - Open/Save location history from Explorer dialogue popup
  - Command and Program Executed
    - HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\RunMRU - Last exectured "Run" command
    - HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\UserAssist\<GUID>\Count - Last Run Time, Run Count, Name (ROT13 encoded), Focus Time, and Focus Count of an application
      - CEBFF5CD - Executable File Execution
      - F4E57C4B - Shortcut File Execution
      - https://learn.microsoft.com/en-us/dotnet/desktop/winforms/controls/known-folder-guids-for-file-dialog-custom-places
       - GUID for common folders


### Shell Item

**Shortcut File**

Structures - https://learn.microsoft.com/en-us/openspecs/windows_protocols/ms-shllink/16cb4ca1-9339-4d0c-a68d-bf1d6cc0f943 
Recent Items - C:/Users/<User>/AppData/Roaming/Microsoft/Windows/Recent (Cap of 149 files/folders)

Tools:
- LEcmd.exe - LNK Explorer
- lp.exe - LNK Parsing Utility

**Windows Task Bar Jumplists**

**Charm Bar**

**Shellbags**
