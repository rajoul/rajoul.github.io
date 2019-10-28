# LAMPSecurity-6

```
nmap -sC -sV -o scan.nmap 10.0.4.14
gobuster dir -u 10.0.4.14 -w /usr/share/dirbuster/wordlists/directory_list-2.3-medium  : sql.db file retrieved
http://10.0.4.14/sql.db : we get the admin password 
go to admin panel to log in
after log in inject an image that contain a reverse shell: we get Apache user
local privesc: linux kernel 8478.sh 
```
**Noting new or learned from this machine, it is sooo classic.**
