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
