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
the version of wordpress is 4.7.10 and there are 17 vulnerabilities. Let's enumerate users of the app.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-2/5.png" width="740" height="240">
</p>
There are three users: jerry,tom,admin. I tried to brute force the admin password with rockyou.txt wordlist but nothing useful.
At the home page there is Flag menu,that tell us to make my own wordlist.txt with **cewl tool** 
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-2/6.png" width="740" height="240">
</p>
Then, this is the commande to make the wordlist.txt.
```
cewl --url http://dc-2/ -w wordlist.txt
```
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-2/cewl.png" width="740" height="240">
</p>
With wpscan,we can also perform brute force on users and passwords,the file users contain users:jerry,tom and admin,there is the syntax.
```
./wpscan --url http://dc-2/ --usernames users -w wordlist.txt
```
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-2/7.png" width="740" height="240">
</p>
wpscan discover two passwords: jerry=>adipiscing, tom => parturient. we authenticate first with tom Credentials but there is nothing inside.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/DC-2/8.png" width="740" height="240">
</p>















