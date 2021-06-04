-   `unshadow /etc/passwd /etc/shadow`
-   `john -incremental -user:johndoe file`
-   `john -wordlist=<wordlist> -rules file`
-   `john <hashfile> --format=NT --wordlist=<wl>` crack windows hashes
-   `john <hashfile> --show` show cracked hashes (format=user:pwd:otherstuff)
-  `wget https://raw.githubusercontent.com/magnumripper/JohnTheRipper/bleeding-jumbo/run/ssh2john.py` get ssh2john
-  `python ssh2john.py id_rsa > outfile` 
-    `john --wordlist=<wordlist> outfile`
-    `/usr/share/john/ssh2john.py idrsa(1).id_rsa > ssh_key`

## basic cracking
- `cat hash | hashid # get hash format`
- `john hash --format=<format> --wordlist=/usr/share/wordlist/rockyou.txt`
- `john hash --format=<format> --show`