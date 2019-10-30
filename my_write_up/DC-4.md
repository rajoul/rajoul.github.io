# DC-4
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-4/1.png" >
</p>
Let’s start with scanning my local private network to get the adress IP of my target.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-4/netdiscover.png" >
</p>
the adress of my target => 10.0.4.20
Our next step is to scan our target with NMAP.
```
nmap -sC -sV -o scan.nmap 10.0.4.20
```
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-4/scan.png">
</p>
there is one port open: 80=> server APACHE et 22 => ssh.
Let's check the server Apache on port 80.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-4/1.png" >
</p>
