# Natas 1
```
import requests,re

username="natas0"
password="natas0"

url=str("http://%s.natas.labs.overthewire.org" %username)

r=requests.post(url,auth=(username,password))
print(r.text)

if re.findall('The password (.*)',r.text):
    print('good')
#<!--The password for natas1 is gtVrDuiDfck831PqWsLEZy5gyDz1clto -->
```
