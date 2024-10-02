# tp-01-unix
1.4 Installation
j'ai galéré.

2.1 configuration ssh

apt search ssh

apt install openssh-server
nano /etc/ssh/sshd_config


Cherche la ligne suivante :
#PermitRootLogin prohibit-password
Modifie-la pour :
PermitRootLogin yes
systemctl restart ssh

2.2 Connexion à la machine virtuelle depuis la machine hôte
ip a
ssh root@<adresse_ip_vm>
Remplace <adresse_ip_vm> par l'adresse IP de la machine virtuelle.
Pour test is SSH est bien installer fait ssh root@localhost,
un message de confirmation devrait apparaitre.
La connexion a la machine de l'hôte ne fonctionne pas,
"ssh: connect to host <adresse_ip_vm> port 22: Connection timed out"

2.3 Nombre de paquets installés
dpkg -l | wc -l             (environ 320)
df -h

2.4 Space Usage
l'espace utiliser repensant 970 Mo

2.5 Résultats et explications des commandes
echo $LANG ; résultat: en_US.UTF-8
hostname ; résultat: vbox
hostname -d ; résultat:sorbonne-universite.fr
verification emplacement depots ;  Pour vérifier quels dépôts sont activés pour l'installation de paquets, résultat: deb http://deb.debian.org/debian/ bookworm main
passwd/shadow ; Pour voir les comptes ayant un mot de passe configuré
compte utilisateurs ; affiche les comptes utilisateurs mais sauf ceux qui sont associés à des services ou les comptes systems
fdisk -l et fdisk -x ; fdisk -l affiche la table des partitions et les informations sur le disque. La commande fdisk -x donne plus de détails sur la géométrie et les structures de disque. Cela te permet d'examiner la structure des partitions.
df -h ; donne une vue d'ensemble de l'utilisation de l'espace disque.
