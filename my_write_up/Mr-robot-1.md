# Mr-robot-1
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/Mr-robot-1/1.png" >
</p>
Let’s start with scanning my local private network to get the adress IP of my target.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image//Mr-robot-1/netdiscover.png" >
</p>
the adress of my target => 10.0.4.17
Our next step is to scan our target with NMAP.
```
nmap -sC -sV -o scan.nmap 10.0.4.17
```
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image//Mr-robot-1/scan.png">
</p>
there is one port open: 80=> server APACHE et 443 => ssl/http
Let's check the server Apache on port 80.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/Mr-robot-1/1.png" >
</p>
 Mr. Robot, it has three keys hidden in different locations. The main goal is to find all three tokens hidden in the system. Each key is progressively difficult to find.First we check the robots.txt if there is any hidden file.
 <p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/Mr-robot-1/key1.png" >
</p>
Great, we get the first key.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/Mr-robot-1/key11.png" >
</p>
