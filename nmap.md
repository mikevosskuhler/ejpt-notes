- `-sn` Ping sweep
- `-sT` TCP connect scan
- `-sS` SYN scan
- `-sV` version detect
- `-p` custom port list
- `-Pn` skip ping
- `-A` OS and version detection
- `-reason` details on closed / open status
- `--script= vuln` get cve's
- `iL` Host list

```bash
fping 1.2.3.0/24 > output.txt
cat output.txt | grep -v unreachable | sed "s/ is alive/g" > hosts.txt
nmap -iL hotst.txt
```

```
nmap 1.2.3.4/24 -A -oX output.nmap -T4
```