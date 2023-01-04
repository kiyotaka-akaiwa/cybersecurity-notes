# Forensics

## Windows

### Imaging

### Memory Forensics

### Registry

**Tools**:
- regedit.exe
- Registry Explorer
- cafae.exe
- RegRipper
- SAMInside

**Location**:
- C:/Windows/system32/config/
- C:/Users/<Username>/NTUSER.dat
- C:/Users/<Username>/AppData/Local/Microsoft/Windows/USRCLASS.dat

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
  - HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Signatures - Previously Connected Network and Domains
  - HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Nla\Cache - Previously Connected Domains
