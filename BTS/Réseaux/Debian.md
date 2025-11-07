# Structure des dossiers de base – résumé

## Objectifs du module

- Identifier les principaux répertoires du système Debian  
- Comprendre leur rôle et leur contenu  
- Utiliser des commandes pour explorer la hiérarchie du système:contentReference[oaicite:0]{index=0}

## Partie 1 : Introduction à la hiérarchie des fichiers

Debian suit la norme **Filesystem Hierarchy Standard (FHS)**, qui définit l’organisation logique des fichiers afin de :

- séparer les fichiers système des fichiers utilisateur,  
- faciliter la maintenance et la sécurité,  
- uniformiser les pratiques entre distributions Linux:contentReference[oaicite:1]{index=1}.

Comprendre cette hiérarchie permet de savoir où se trouvent les programmes, bibliothèques, fichiers de configuration et données utilisateur.

## Partie 2 : Les dossiers principaux

| Dossier | Rôle / contenu |
| --- | --- |
| `/` | Racine du système : point de départ de tous les autres dossiers |
| `/bin` | Programmes essentiels accessibles à tous (`ls`, `cp`, `mv`…) |
| `/sbin` | Programmes système réservés à l’administrateur (`iptables`, `reboot`…) |
| `/etc` | Fichiers de configuration du système et des services |
| `/home` | Dossiers personnels des utilisateurs |
| `/var` | Fichiers variables : logs, mail, bases de données |
| `/usr` | Programmes et bibliothèques non essentiels |
| `/tmp` | Fichiers temporaires, supprimés au redémarrage |
| `/boot` | Fichiers de démarrage (noyau, GRUB) |
| `/dev` | Périphériques représentés sous forme de fichiers |
| `/proc` | Infos sur les processus et le noyau |
| `/sys` | Infos sur le matériel et les pilotes |
| `/mnt` | Points de montage pour périphériques externes ou temporaires:contentReference[oaicite:2]{index=2} |

## Partie 3 : Zoom sur quelques dossiers clés

- **`/etc`** : contient les fichiers de configuration, par exemple `/etc/ssh/sshd_config` ou `/etc/network/interfaces`:contentReference[oaicite:3]{index=3}.  
- **`/var/log`** : regroupe les journaux du système, comme le fichier central `/var/log/syslog`:contentReference[oaicite:4]{index=4}.  
- **`/home`** : espace personnel des utilisateurs, chaque utilisateur ayant son sous-répertoire (`/home/[nom]`):contentReference[oaicite:5]{index=5}.  

## Partie 4 : Commandes utiles

```bash
$ ls /                # Liste les dossiers à la racine
$ cd /etc             # Se déplacer dans le dossier de configuration
$ tree /              # Affiche l'arborescence (si installé)
$ du -sh /var/*       # Voir la taille des sous-dossiers de /var
$ mkdir /tmp/myfolder # Créer un répertoire dans /tmp
$ rm -R /tmp/myfolder # Supprimer un dossier dans /tmp
$ touch /tmp/myfile   # Créer un fichier vide dans /tmp
$ nano /tmp/myfile    # Éditer le fichier
$ rm /tmp/myfile      # Supprimer un fichier dans /tmp
