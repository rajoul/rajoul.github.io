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
