
# 📁 Protocoles FTP et SFTP : Comprendre le transfert de fichiers

## 📌 Introduction

Le transfert de fichiers est une opération essentielle en informatique, permettant de déplacer des données entre différents systèmes. Deux protocoles principaux sont utilisés pour cette tâche :

* **FTP (File Transfer Protocol)** : protocole standard pour le transfert de fichiers sur un réseau TCP/IP.
* **SFTP (SSH File Transfer Protocol)** : protocole sécurisé basé sur SSH pour le transfert de fichiers.

---

## 🔄 FTP : File Transfer Protocol

### 📖 Définition

Le **FTP** est un protocole de communication destiné au transfert de fichiers entre un client et un serveur sur un réseau TCP/IP.
Il fonctionne selon un modèle client-serveur et utilise deux connexions distinctes :

* **Connexion de commande** : établie sur le port 21, elle permet l'envoi des commandes et la réception des réponses.
* **Connexion de données** : établie sur le port 20, elle est utilisée pour le transfert effectif des fichiers.

### 🛠 Fonctionnement

Le FTP peut fonctionner en deux modes :

* **Mode actif** : le client ouvre un port et attend que le serveur établisse la connexion de données.
* **Mode passif** : le serveur ouvre un port et attend que le client établisse la connexion de données.

Ce protocole permet des opérations telles que :

* Téléversement et téléchargement de fichiers
* Création, suppression et renommage de fichiers et répertoires
* Affichage du contenu des répertoires

### ⚠️ Limitations

Le FTP présente des faiblesses en matière de sécurité :

* Les données, y compris les identifiants, sont transmises en clair
* Aucun chiffrement n’est prévu
* Vulnérable aux attaques de type interception (sniffing)

---

## 🔐 SFTP : SSH File Transfer Protocol

### 📖 Définition

Le **SFTP** est un protocole de transfert de fichiers sécurisé qui fonctionne au-dessus du protocole SSH (Secure Shell).
Contrairement au FTP, il chiffre toutes les données transmises, y compris les identifiants et les fichiers.

### 🛠 Fonctionnement

SFTP utilise une seule connexion sécurisée sur le port 22.
Il permet :

* Le transfert de fichiers chiffré
* La gestion de fichiers à distance (renommage, suppression, création de dossiers)
* L’authentification par mot de passe ou clé SSH

### ✅ Avantages

* **Sécurité** : toutes les données sont chiffrées
* **Authentification forte** : mot de passe ou clé SSH
* **Un seul port utilisé** : facilite la configuration des pare-feu

### ⚠️ Inconvénients

* **Plus complexe à mettre en place** qu’un simple FTP
* **Performances légèrement réduites** à cause du chiffrement

---

## ⚖️ Comparaison FTP vs SFTP

| Caractéristique          | FTP                         | SFTP                    |
| ------------------------ | --------------------------- | ----------------------- |
| **Port utilisé**         | 21 (commande), 20 (données) | 22                      |
| **Sécurité**             | Aucune                      | Chiffrement complet     |
| **Authentification**     | Identifiants simples        | Clé SSH ou mot de passe |
| **Nombre de connexions** | Deux                        | Une seule               |
| **Pare-feu**             | Difficile à configurer      | Facile à configurer     |

---

## 🧪 Exemples d'utilisation

### FTP avec FileZilla

1. Ouvrir FileZilla
2. Entrer l’adresse du serveur FTP, le nom d’utilisateur et le mot de passe
3. Naviguer et transférer les fichiers

### SFTP en ligne de commande

```bash
sftp utilisateur@serveur.com
sftp> put fichier.txt
sftp> get fichier.txt
sftp> exit
```

---

## 📚 Ressources supplémentaires

* [Kiteworks : Qu'est-ce que le SFTP ?](https://www.kiteworks.com/fr/glossaire/sftp-quest-ce-que-le-protocole-de-transfert-de-fichiers-securise/)
* [Wikipedia : File Transfer Protocol](https://fr.wikipedia.org/wiki/File_Transfer_Protocol)
* [Wikipedia : SSH File Transfer Protocol](https://fr.wikipedia.org/wiki/SSH_File_Transfer_Protocol)

---
