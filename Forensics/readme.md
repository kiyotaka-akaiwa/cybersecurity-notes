# Forensics

## Windows

### Imaging

**Important Files and Folders**:
- C:/Windows/System32/NetworkList - NLA

### Memory Forensics

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
  - Networks
    - HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Signatures - Previously Connected Network and Domains
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
    
