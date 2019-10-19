# Kioptrix_2
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
  <img src="https://rajoul.github.io/my_write_up/image/kioptrix_2/real_scan.png" width="860" height="420">
</p>
En examinant les résultats de l'analyse Nmap, les ports TCP 80 et 443 utilisent Apache Server version 2.0.52. De plus, le port TCP 22 utilise Open SSH version 3.9p1, le port TCP 631 utilise CUPS 1.1 et le port TCP 3306 utilise MySQL (version inconnue pour le moment).
