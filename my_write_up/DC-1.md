# DC-1
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-1/accueil.png" width="840" height="260">
</p>
Let’s start with scanning my local private network to get the adress IP of my target.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-1/netdiscover.png" width="800" height="200">
</p>
the adress of my target => 10.0.4.15
Our next step is to scan our target with NMAP.
```
nmap -sC -sV -o scan.nmap 10.0.4.13
```
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-1/scan.png" width="800" height="500">
</p>
there are three port open: 80=> server APACHE, 22 => SSH et 111 =>RPC(remote procedure call)
Let's check the server Apache on port 80.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-1/accueil.png" width="740" height="240">
</p>
the website is buit with drupal, wappalyzer extension extend the version of drupal site.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-1/wappa.png" width="800" height="300">
</p>
