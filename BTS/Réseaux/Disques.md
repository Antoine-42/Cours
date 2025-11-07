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


| Champ | Description |
|-------|--------------|
| **UUID ou /dev/sdX** | Identifiant unique ou nom du périphérique |
| **Point de montage** | Dossier où sera montée la partition (`/home`, `/var`…) |
| **Type** | Type de système de fichiers (`ext4`, `xfs`, `btrfs`, etc.) |
| **Options** | Paramètres de montage (`defaults`, `nofail`, etc.) |
| **Dump** | Indique si la partition doit être sauvegardée (souvent 0) |
| **Pass** | Ordre de vérification au démarrage (1 = racine, 2 = autres) |

---

### 🧪 3.2 Exemples pratiques

Partition racine

UUID=fd0587f2-d0d0-404c-b4c3-aa358b8dacd6 / ext4 defaults 0 1

Partition /home sur un second disque

UUID=377d38df-2140-4440-80fd-904271438ad1 /home ext4 defaults 0 2

Partition /var séparée

UUID=46a177d7-9856-4137-95a1-432e61085bde /var ext4 defaults 0 2


---

## 🧠 4. À retenir

- Linux **monte les partitions dans des dossiers**, pas avec des lettres de disque.  
- Le fichier **`/etc/fstab`** décrit quelles partitions sont **montées automatiquement** au démarrage.  
- **Séparer `/home`, `/var` ou `/boot`** sur des partitions dédiées améliore la **sécurité**, la **performance** et la **maintenance** du système.

---

