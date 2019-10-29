# DC-2
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-1/3.png" width="840" height="300">
</p>
Let’s start with scanning my local private network to get the adress IP of my target.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-1/netdiscover.png" width="800" height="200">
</p>
the adress of my target => 10.0.4.16
Our next step is to scan our target with NMAP.
```
nmap -sC -sV -o scan.nmap 10.0.4.16
```
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-1/scan.png" width="800" height="500">
</p>
there is one port open: 80=> server APACHE.
Let's check the server Apache on port 80.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-1/1.png" width="740" height="240">
</p>
the page can't be uploaded,So I added the adress of the target machine to the file /etc/hosts.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-1/2.png" width="740" height="240">
</p>
After, we Can see the page clearly,the website is buit with wordpress.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-1/3.png" width="740" height="240">
</p>
