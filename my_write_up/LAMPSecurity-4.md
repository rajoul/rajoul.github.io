# LAMPSecurity 4
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/LAMPSecurity-4/accueil.png" width="760" height="260">
</p>
##### 1-reconnaissance
Let’s start with scanning my local private network to get the adress IP of my target.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/LAMPSecurity-4/netdiscover.png" width="800" height="200">
</p>
the adress of my target => 10.0.4.12

Our next step is to scan our target with NMAP.
**nmap -sC -sV -o scan.nmap 10.0.4.12**
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/LAMPSecurity-4/scan.png" width="800" height="400">
</p>
