# Disques, partitions et système de fichiers

## Structure des dossiers et montage des partitions

Sous Linux, l’arborescence commence à la racine `/`. Contrairement à Windows (où chaque disque est associé à une lettre C:, D:, etc.), chaque dossier de l’arbre peut être monté sur une partition distincte, voire sur un autre disque physique:contentReference[oaicite:0]{index=0}. Cette flexibilité permet d’isoler certaines zones du système pour améliorer la sécurité et la maintenance.

Quelques exemples de dossiers et de partitions dédiées :

| Dossier  | Rôle principal                                              | Partition dédiée ?              |
| -------- | ----------------------------------------------------------- | --------------------------------|
| `/`      | Racine du système                                           | Oui (obligatoire)               |
| `/home`  | Dossiers des utilisateurs                                   | Souvent séparé (disque/partition dédiés) |
| `/var`   | Logs, bases de données, fichiers temporaires                | Recommandé sur les serveurs     |
| `/boot`  | Fichiers de démarrage (GRUB, noyau)                         | Souvent séparé                  |
| `/mnt`   | Points de montage temporaires (clés USB, disques externes) | Peut être séparé                |

L’idée est que **chaque dossier peut être monté sur une partition différente**, même si les partitions se trouvent sur un même disque ou sur des disques distincts:contentReference[oaicite:1]{index=1}.

## Exemple concret

Imaginons un serveur avec deux disques :

- **Disque 1** : contient la racine `/`, le répertoire `/boot` et le répertoire `/var`.
- **Disque 2** : contient le répertoire `/home` (les données utilisateurs) et un dossier `/mnt` pour les points de montage temporaires.

Cette configuration sépare clairement les données des utilisateurs du système de base, ce qui facilite les sauvegardes et renforce la sécurité.

## La table des montages (`/etc/fstab`)

Linux utilise le fichier texte **`/etc/fstab`** (*File System Table*) pour savoir quelles partitions monter et avec quelles options. Chaque ligne décrit une partition ou un système de fichiers : son identifiant (UUID ou chemin `/dev/sdX`), le point de montage, le type de système de fichiers, des options, et deux valeurs numériques (dump/pass). Une erreur dans ce fichier peut empêcher le système de démarrer correctement.

### Structure d’une ligne `fstab`

Exemple :

