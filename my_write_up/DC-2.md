# DC-2
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-2/3.png" width="840" height="300">
</p>
Let’s start with scanning my local private network to get the adress IP of my target.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-2/netdiscover.png" width="800" height="200">
</p>
the adress of my target => 10.0.4.16
Our next step is to scan our target with NMAP.
```
nmap -sC -sV -o scan.nmap 10.0.4.16
```
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-2/scan.png" width="800" height="500">
</p>
there is one port open: 80=> server APACHE.
Let's check the server Apache on port 80.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-2/1.png" width="740" height="240">
</p>
the page can't be uploaded,So I added the adress of the target machine to the file /etc/hosts with dc-2 hostname.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-2/2.png" width="740" height="240">
</p>
After, we Can see the page clearly,the website is buit with wordpress.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-2/3.png" width="740" height="240">
</p>
the firt step after we discover the website is buit with wordpress is fingerprinting, that allow us to discover the version of the
wordpress and exploit vulnerabilities of this one, with **wpscan tool**.
```
./wpscan.rb --url http://dc-2/ 
```
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-2/4.png" width="740" height="240">
</p>
