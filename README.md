# tp-01-unix
1.4 Installation<br>
j'ai galéré.

2.1 configuration ssh

apt search ssh

apt install openssh-server<br>
nano /etc/ssh/sshd_config


Cherche la ligne suivante :<br>
#PermitRootLogin prohibit-password <br>
Modifie-la pour : <br>
PermitRootLogin yes <br>
systemctl restart ssh

2.2 Connexion à la machine virtuelle depuis la machine hôte<br>
ip a<br>
ssh root@<adresse_ip_vm> <br>
Remplace <adresse_ip_vm> par l'adresse IP de la machine virtuelle. <br>
Pour test is SSH est bien installer fait ssh root@localhost,<br>
un message de confirmation devrait apparaitre.<br>
La connexion a la machine de l'hôte ne fonctionne pas,<br>
"ssh: connect to host <adresse_ip_vm> port 22: Connection timed out"<br>

2.3 Nombre de paquets installés<br>
dpkg -l | wc -l             (environ 320)<br>
df -h

2.4 Space Usage<br>
l'espace utiliser repensant 970 Mo

2.5 Résultats et explications des commandes<br>
echo $LANG ; résultat: en_US.UTF-8 <br>

-hostname ; résultat: *vbox* <br>

-hostname -d ; résultat:*sorbonne-universite.fr* <br>

-Verification emplacement depots ;  Pour vérifier quels dépôts sont activés pour l'installation de paquets, résultat: deb http://deb.debian.org/debian/ bookworm main <br>
passwd/shadow ; Pour voir les comptes ayant un mot de passe configuré <br>

-Compte utilisateurs ; affiche les comptes utilisateurs mais sauf ceux qui sont associés à des services ou les comptes systems <br>

-*fdisk -l* et *fdisk -x* ; fdisk -l affiche la table des partitions et les informations sur le disque. La commande fdisk -x donne plus de détails sur la géométrie et les structures de disque. Cela te permet d'examiner la structure des partitions. <br>

-*df -h* ; donne une vision d'ensemble de l'utilisation de l'espace disque. <br>
