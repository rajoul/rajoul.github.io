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
  <img src="https://rajoul.github.io/my_write_up/image/LAMPSecurity-5/scan.png" width="800" height="500">
</p>
there are three port open: 80=> server APACHE, 25 => SMTP, 22 => SSH, 3306 => mysql, 139,445 => SAMBA et 110 =>pop3
Let's check the server Apache on port 80.
I get the root access with two different ways :
##### first way
At the the Blog menu there is a admin panel authenticity.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/LAMPSecurity-5/admin_panel.png" width="800" height="230">
</p>
the first thing I do is brute forcing the credentials with Hydra'tool.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/LAMPSecurity-5/hydra.png" width="800" height="230">
</p>
Great, I get the user(admin) and password(shannon).After we authenticate with them and access the admin priviledge zone, there is
a possibility to add a new php page,that give me the power to upload a reverse shell successfully.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/LAMPSecurity-5/5.png" width="800" height="350">
</p>
After I saved the page, I run it and the shell is sended bask to my listener.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/LAMPSecurity-5/6.png" width="800" height="300">
</p>
I get the remote access to the target as a **apache** user,I check the version of the OS it seems to be vulnerable to local priviledge escalation.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/LAMPSecurity-5/7.png" width="800" height="230">
</p>
metasploit is the best tool for discovering exploits, 
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/LAMPSecurity-5/searchsploit.png" width="800" height="230">
</p> 
So, I upload it,compile it and send it to my target to execute it.And Finally we have a root access.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/LAMPSecurity-5/root_access.png" width="800" height="300">
</p> 








