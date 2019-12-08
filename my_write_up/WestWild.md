# WestWild 1.1
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/West_Wild/accueil.png" >
</p>
Let’s start with scanning my local private network to get the adress IP of my target.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/West_Wild/netdiscover1.png" >
</p>
the adress of my target => 10.0.4.34
Our next step is to scan our target with NMAP.
```
nmap -sC -sV -o scan.nmap 10.0.4.34
```
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/West_Wild/scan.png">
</p>
there is one port open: 80=> server APACHE , 22 => ssh and 139,445 => samba
Let's check the server Apache on port 80.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/West_Wild/accueil.png">
</p>
