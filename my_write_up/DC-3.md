# DC-3
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-3/1.png" >
</p>
Let’s start with scanning my local private network to get the adress IP of my target.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-3/netdiscover.png" >
</p>
the adress of my target => 10.0.4.17
Our next step is to scan our target with NMAP.
```
nmap -sC -sV -o scan.nmap 10.0.4.17
```
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-2/scan.png">
</p>
there is one port open: 80=> server APACHE.
Let's check the server Apache on port 80.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-3/1.png" >
</p>
We start enumerating directories,with **gobuster tool**.
```
gobuster dir -u 10.0.4.17 -w /usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt
```
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-3/2.png" >
</p>
There is an administrator page, that is an admin panel,we need password for admin user.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-3/3.png" >
</p>
We start identifying first the the CMS.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-3/4.png" >
</p>
there is different way to gat credentials:
1-brute force with hydra
2-use sqlmap
3-use nmap scripts
I tried to find script for joomla CMS.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-3/5.png" >
</p>
After I started to brute force the admin panel with nmap.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-3/6.png" >
</p>
Great, we get admin:snoopy, let's authenticate and see what inside the dashboard.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-3/7.png" >
</p>










