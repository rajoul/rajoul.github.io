# LAMPSecurity-5
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/LAMPSecurity-5/accueil.png" width="840" height="260">
</p>
Let’s start with scanning my local private network to get the adress IP of my target.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/LAMPSecurity-5/netdiscover.png" width="800" height="200">
</p>
the adress of my target => 10.0.4.13

Our next step is to scan our target with NMAP.
**nmap -sC -sV -o scan.nmap 10.0.4.13**
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/LAMPSecurity-5/scan.png" width="800" height="400">
</p>
there are three port open: 80=> server APACHE, 25 => SMTP, 22 => SSH, 3306 => mysql, 139,445 => SAMBA et 110 =>pop3
Let's check the server Apache on port 80.
I get the root access with two different ways :
##### first way
At the the Blog menu there is a admin panel authenticity.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/LAMPSecurity-5/scan.png" width="800" height="260">
</p>
