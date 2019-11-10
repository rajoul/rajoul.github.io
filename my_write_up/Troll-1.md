# Troll-1
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/Troll-1/1.png">
</p>
Let’s start with scanning my local private network to get the adress IP of my target.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/Troll-1/netdiscover.png">
</p>
the adress of my target => 10.0.4.26
Our next step is to scan our target with NMAP.
```
nmap -sC -sV -o scan.nmap 10.0.4.26
```
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/Troll-1/scan.png" >
</p>
there are three port open: 80=> server APACHE, 22 => SSH et 21 =>FTP(remote procedure call)
Let's check the server Apache on port 80.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/Troll-1/1.png">
</p>
