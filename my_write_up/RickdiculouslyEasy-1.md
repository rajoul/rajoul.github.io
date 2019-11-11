# RickdiculouslyEasy-1
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/RickdiculouslyEasy-1/accueil.png" >
</p>
Let’s start with scanning my local private network to get the adress IP of my target.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/RickdiculouslyEasy-1/netdiscover.png" >
</p>
the adress of my target => 10.0.4.29
Our next step is to scan our target with NMAP.
```
nmap -sC -sV -o scan.nmap 10.0.4.29
```
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/RickdiculouslyEasy-1/scan.png" >
</p>
there are three port open: 80=> server APACHE, 22 => SSH et 21 =>FTP ,9090 
Let's check the server Apache on port 80.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/RickdiculouslyEasy-1/accueil.png" >
</p>
Starting by checking the ftp service that allow anonymous user and retrieve the first flag.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/RickdiculouslyEasy-1/ftp.png" >
</p>
Next enumerating directories, with gobuster tool.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/RickdiculouslyEasy-1/1.png" >
</p>
we look what is in passwords directories.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/RickdiculouslyEasy-1/2.png" >
</p>
We get an other flag with 10 points.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/RickdiculouslyEasy-1/3.png" >
</p>

