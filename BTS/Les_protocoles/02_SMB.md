# 📁 Le protocole SMB (Server Message Block)

## 📌 Introduction

Le protocole **SMB** (Server Message Block) est un protocole réseau de type client-serveur qui permet le partage de ressources telles que des fichiers, des imprimantes et des ports série entre ordinateurs sur un réseau local. Initialement développé par IBM en 1983, il a été largement adopté et intégré dans les systèmes Windows, et est également pris en charge par d'autres systèmes d'exploitation via des implémentations comme Samba. 

---

## 🧩 Fonctionnement de SMB

SMB fonctionne selon un modèle **client-serveur** :

* **Client** : envoie des requêtes pour accéder à des ressources partagées.
* **Serveur** : répond aux requêtes en fournissant l'accès aux ressources demandées.

Le protocole utilise principalement le port **TCP 445** pour établir des connexions directes. Dans les versions antérieures, il pouvait également utiliser les ports **TCP 139** et **UDP 137-138** via NetBIOS.

---

## 🧱 Versions de SMB

| Version       | Année de sortie | Systèmes associés                  | Caractéristiques principales                                                       |                                                     |
| ------------- | --------------- | ---------------------------------- | ---------------------------------------------------------------------------------- | --------------------------------------------------- |
| **SMB 1.0**   | 1983            | Windows NT 4.0, Windows 2000       | Première version, également connue sous le nom de CIFS                             |                                                     |
| **SMB 2.0**   | 2006            | Windows Vista, Windows Server 2008 | Amélioration des performances et réduction du nombre de commandes                  |                                                     |
| **SMB 2.1**   | 2007            | Windows 7, Windows Server 2008 R2  | Optimisations supplémentaires                                                      |                                                     |
| **SMB 3.0**   | 2012            | Windows 8, Windows Server 2012     | Introduction du chiffrement et du multicanal                                       |                                                     |
| **SMB 3.1.1** | 2015            | Windows 10, Windows Server 2016    | Sécurité renforcée avec l'authentification préalable et le chiffrement AES-128-GCM 
---

## 🔐 Sécurité et bonnes pratiques

SMB 1.0 présente des vulnérabilités connues et n'est plus recommandé. Il est conseillé de désactiver cette version et d'utiliser SMB 3.x, qui offre des fonctionnalités de sécurité avancées telles que :

* **Chiffrement des données** : protège les données en transit contre les interceptions.
* **Signature des paquets** : assure l'intégrité des communications.
* **Authentification renforcée** : utilisation de mécanismes d'authentification avancés pour vérifier l'identité des utilisateurs.

---

## 🛠 Mise en œuvre de SMB

### Sous Windows

Pour créer un partage SMB :

1. Accédez aux propriétés du dossier à partager.
2. Allez dans l'onglet **Partage** et cliquez sur **Partage avancé**.
3. Cochez **Partager ce dossier** et définissez les autorisations appropriées.

Pour accéder à un partage SMB :

* Utilisez l'Explorateur de fichiers et entrez le chemin UNC, par exemple : `\\serveur\partage`.

### Sous Linux avec Samba

Samba est une suite logicielle qui permet aux systèmes Unix/Linux de partager des ressources via SMB.

1. Installez Samba :

   ```bash
   sudo apt-get update
   sudo apt-get install samba
   ```



2. Configurez le fichier `/etc/samba/smb.conf` pour définir les partages.
3. Redémarrez le service Samba :

   ```bash
   sudo systemctl restart smbd
   ```



Pour monter un partage SMB sur Linux :

```bash
sudo mount -t cifs //serveur/partage /mnt/point_de_montage -o username=utilisateur
```



---

## ⚖️ Comparaison avec d'autres protocoles

| Protocole | Utilisation principale          | Sécurité intégrée   | Systèmes compatibles              |                                                                                                                                                            |
| --------- | ------------------------------- | ------------------- | --------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **SMB**   | Partage de fichiers/imprimantes | Oui (SMB 3.x)       | Windows, Linux (via Samba), macOS |                                                                                                                                                            |
| **FTP**   | Transfert de fichiers           | Non (en clair)      | Multi-plateforme                  |                                                                                                                                                            |
| **NFS**   | Partage de fichiers             | Oui (avec Kerberos) | Principalement Unix/Linux         |
---

## 📚 Ressources supplémentaires

* [Le protocole SMB pour les débutants - IT-Connect](https://www.it-connect.fr/le-protocole-smb-pour-les-debutants/)
* [Le protocole SMB : fonctionnement et versions - Malekal](https://www.malekal.com/protocole-smb-fonctionnement-versions/)
* [Qu'est-ce que le protocole SMB - Surfshark](https://surfshark.com/fr/blog/protocole-smb)

---