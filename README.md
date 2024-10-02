# tp-01-unix
<h1>1 Installation Machine virtuelle</h1><br>
<h2>1.1 Debian et supports d’intallation</h2><br>
La version installer est la version actuelle la stable, bookworm : version 12 <br>

<h2>1.4 Installation</h2>
j'ai galéré.

<h1>2 Post-Installation</h1><br>
<h2>2.1 Configuration ssh</h2><br>
apt search ssh<br>
apt install openssh-server<br>
nano /etc/ssh/sshd_config<br>

Cherche la ligne suivante :<br>
#PermitRootLogin prohibit-password <br>
Modifie-la pour : <br>
PermitRootLogin yes <br>
systemctl restart ssh

<h2>2.2 Connexion à la machine virtuelle depuis la machine hôte</h2>
ip a<br>
ssh root@<adresse_ip_vm> <br>
Remplace <adresse_ip_vm> par l'adresse IP de la machine virtuelle. <br>
Pour test is SSH est bien installer fait ssh root@localhost,<br>
un message de confirmation devrait apparaitre.<br>
La connexion a la machine de l'hôte ne fonctionne pas,<br>
"ssh: connect to host <adresse_ip_vm> port 22: Connection timed out"<br>

<h2>2.3 Nombre de paquets installés</h2>
dpkg -l | wc -l             (environ 320)<br>

<h2>2.4 Space Usage</h2>
l'espace utiliser repensant 970 Mo <br>

<h2>2.5 Résultats et explications des commandes</h2>
<strong>echo $LANG</strong> ; résultat: en_US.UTF-8 <br>

<strong>-hostname</strong> ; résultat: *vbox* <br>

<strong>-hostname -d</strong> ; résultat:*sorbonne-universite.fr* <br>

<strong>-Verification emplacement depots</strong> ;  Pour vérifier quels dépôts sont activés pour l'installation de paquets, résultat: deb http://deb.debian.org/debian/ bookworm main <br>

<strong>-passwd/shadow</strong> ; Pour voir les comptes ayant un mot de passe configuré. Exemple: <br>
<img width="450" alt="shadow" src="https://github.com/user-attachments/assets/1c21d4d1-16c6-4d03-b95e-69efb11972b6"><br>

<strong>-Compte utilisateurs</strong> ; affiche les comptes utilisateurs mais sauf ceux qui sont associés à des services ou les comptes systems. Exemple:<br>
<img width="219" alt="user" src="https://github.com/user-attachments/assets/0f739659-fba3-4101-95fa-d3c59a2c6880"><br>
 
<strong>-*fdisk -l* et *fdisk -x*</strong> ; fdisk -l affiche la table des partitions et les informations sur le disque. La commande fdisk -x donne plus de détails sur la géométrie et les structures de disque. Cela te permet d'examiner la structure des partitions. <br>

<strong>-*df -h*</strong> ; donne une vision d'ensemble de l'utilisation de l'espace disque. <br>

<h1>3. Aller plus loin</h1>
<strong>Preseed</strong> : Le preseed est un fichier de configuration qui permet d'automatiser l'installation de Debian et dérivés. Cela sert à répondre automatiquement aux questions posées durant l'installation (comme les paramètres de partitionnement, la configuration réseau, etc.). <br>

<strong>Rescue Mode</strong> : Si tu oublies ton mot de passe root, tu peux redémarrer ta machine virtuelle en mode "rescue" ou "recovery" et suivre les étapes pour changer le mot de passe :<br>
Redémarre la machine.<br>
Accède au mode "rescue" dans GRUB en appuyent sur ESC puis sur "c" au lancement .<br>
Une fois dans le mode "rescue", utilise la commande suivante pour réinitialiser le mot de passe root :<br>
passwd root<br>

<strong>Redimensionner une partition</strong> : Pour redimensionner la partition racine sans réinstaller, il vaut utiliser gparted ou les outils resize2fs et fdisk. Il faut démonter la partition, redimensionner<br> avec fdisk, puis ajuster avec resize2fs.<br>


