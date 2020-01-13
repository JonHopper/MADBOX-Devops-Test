Test MADBOX DevOps
===

## Technologie utilisees

| Categorie| Technologie | Raison particuliere ? |
| :------: | :--------: | :------:|
| VPN | Wireguard | Overhead minimum / Facilite d'installation  |
| HTTP | Apache2 | Habitude du rewrite engine |
| DNS | Bind9 | |
| Routage | IPTables | |

## Timeline
| Duree| Etape | Difficulte particuliere ? |
| :------: | :--------: | :------:|
| 10 mins | Installation de Debian 10 | |
| 5 mins | Installation des paquets | |
| 15 mins | Deploiement de la VM sur le NAS | ArchLinux: modules noyaux a charger manuellement |
| 10 mins | Configuration de la page statique sur Apache2 |
| 15 mins | Configuration de bind9 pour rediriger google.com | |
| 40 mins | Configuration du server et client Wireguard | Le NAT hairpin de ma gateway... |


## Developement / Deploiement
* J'ai commence par creer une VM VirtualBox sur mon poste
* J'ai installe Debian 10 dessus puis je l'ai exporte (OVA)
* Apres avoir installe VirtualBox-nox sur mon NAS (ArchLinux), j'ai importe la VM
* J'ai terminer l'installation et la configuration des differents services
* Puis j'ai configurer une redirection de port (avec la regle firewall correspondante) derriere le NAT de ma gateway Internet


## Commentaires
* NGINX aurait tout aussi bien fait l'affaire comme serveur HTTP (peut etre meme plus rapide)
* Si j'avais eu une license, j'aurais utilise VMWare ESXi au lieu de VirtualBox
* Sur un petit projet d'une seule machine comme celui-ci, l'utilisation d'un outil de provisioning comme Ansible
serait overkill, par contre sur un projet plus complexe et necessitant une grande scalabilite je m'en serai servi
