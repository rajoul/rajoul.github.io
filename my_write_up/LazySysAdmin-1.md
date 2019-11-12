# LazySysAdmin-1
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/LazySysAdmin-1/accueil.png" >
</p>
Let’s start with scanning my local private network to get the adress IP of my target.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/LazySysAdmin-1/netdiscover.png" >
</p>
the adress of my target => 10.0.4.30
Our next step is to scan our target with NMAP.
```
nmap -sC -sV -o scan.nmap 10.0.4.30
```
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/LazySysAdmin-1/scan.png" >
</p>
there are three port open: 80=> server APACHE, 22 => SSH et 139,445 =>samba ,3306 => mysql et 6667 => IRC that is a communication's protocol. 
Let's check the server Apache on port 80.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/LazySysAdmin-1/accueil.png" >
</p>

