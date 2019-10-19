# Kioptrix_2
##### 1-reconnaissance
La première phase consiste à decouvrir l'adresse ip de notre machine.Étant donné que j'utilise un réseau privé sur un hôte Linux 
distant, j'ai choisi de vérifier les paramètres réseau sur le système Kali afin de déterminer l'adresse IP et le masque de sous-réseau 
du réseau privé. De plus, j’ai créé un répertoire ensiie 1 dans le répertoire personnel de root, sur le système Kali, pour capturer et stocker des fichiers.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/kioptrix_2/eth0.png" width="860" height="220">
</p>
Avec l’adresse IP et le masque de sous-réseau du système Kali obtenus,je peux decouvrir l'adresse de ma machine qui est dans cette plage d'adresse:10.0.4.0/24
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/kioptrix_2/netdiscover.png" width="860" height="220">
</p>
Les paramètres utilisés pour Nmap effectueront une analyse sur les ports ouverts,les services qui s'éxécutent sur chaque port et leur versions,tout ces informations sont stockés dans un fichier scan.nmap
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/kioptrix_2/real_scan.png" width="860" height="450">
</p>
En examinant les résultats de l'analyse Nmap, les ports TCP 80 et 443 utilisent Apache Server version 2.0.52. De plus, le port TCP 22 utilise Open SSH version 3.9p1, le port TCP 631 utilise CUPS 1.1 et le port TCP 3306 utilise MySQL (version inconnue pour le moment).
##### 2-Exploitation
Pour examiner de plus près les ports TCP 80, j'ai lancé Nitko avec les paramètres d'hôte, de port et de fichier de sortie.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/kioptrix_2/nikto.png" width="860" height="450">
</p>
il ne semble pas y avoir d’exploitation pour un shell distant.mais Nikto nous informe que la requete HTTP contient des spécifiques 
QUERY STRING.donc On va essayer avec SQLMAP pour trouver la base de donnée.
tout d'abord on intercepte la requête via burp suite.
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/kioptrix_2/burp_suite_3.png" width="860" height="220">
</p>
ensuite on récupère toutes les informations sur la requête et les enregistrés dans un fichier burp.txt.et enfin lancer sqlmap.**>sqlmap -r burp.txt --dbs**
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/kioptrix_2/database_name_5.png" width="860" height="220">
</p>
ensuite on récupère les tables du database webapp.**>sqlmap -r burp.txt -D webapp --tables**
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/kioptrix_2/table_name_6.png" width="860" height="220">
</p>
enfin récupèrer les comptes utilisateur.**>sqlmap -r burp.txt -D webapp -T users --dump**
<p align="center">
  <img src="https://rajoul.github.io/my_write_up/image/kioptrix_2/get_users_7.png" width="860" height="220">
</p>
On a réussi à trouver deux comptes utilisateurs et leurs mots de pass.











