# 📂 Protocoles FTP, FTPS et SFTP 

Le **FTP (File Transfer Protocol)** et ses variantes **FTPS** et **SFTP** sont des protocoles permettant le transfert de fichiers entre un client et un serveur. Ces protocoles sont largement utilisés pour l'échange de données sur les réseaux, notamment pour l'hébergement de sites web et la gestion des fichiers à distance.

---

## 📤 Qu'est-ce que le FTP ?

Le **FTP (File Transfer Protocol)** est un protocole standard utilisé pour transférer des fichiers entre un client et un serveur via un réseau TCP/IP.

### ✅ Caractéristiques du FTP :
- Fonctionne en mode **client-serveur**.
- Utilise deux connexions distinctes : **commande (port 21)** et **données (port 20 en mode actif)**.
- Permet l'authentification avec un **nom d'utilisateur et un mot de passe**.
- Peut fonctionner en mode **actif** ou **passif**.

### ⚠️ Inconvénients du FTP :
- **Aucune sécurité intégrée** : les données (y compris les mots de passe) sont envoyées en clair.
- Vulnérable aux attaques **interception (sniffing)** et **attaques MITM** (Man-In-The-Middle).

---

## 🔒 Qu'est-ce que le FTPS ?

Le **FTPS (FTP Secure)** est une extension sécurisée du FTP qui utilise **SSL/TLS** pour chiffrer les données et sécuriser les connexions.

### ✅ Caractéristiques du FTPS :
- Ajoute une **couche de chiffrement** avec **SSL/TLS**.
- Peut fonctionner en mode **explicite** (le chiffrement est activé sur demande) ou **implicite** (chiffrement obligatoire).
- Compatible avec les serveurs FTP classiques tout en offrant un **meilleur niveau de sécurité**.

### ⚠️ Inconvénients du FTPS :
- Nécessite une **gestion des certificats SSL/TLS**.
- Moins compatible avec certains pare-feux, car il utilise plusieurs ports dynamiques.

---

## 🔑 Qu'est-ce que le SFTP ?

Le **SFTP (SSH File Transfer Protocol)** est une alternative sécurisée au FTP, utilisant le protocole **SSH (Secure Shell)** pour chiffrer la transmission des données.

### ✅ Caractéristiques du SFTP :
- Fonctionne sur un **seul port (22)** contrairement au FTP/FTPS.
- Utilise un **chiffrement natif** basé sur SSH pour sécuriser toutes les communications.
- Permet l'authentification par **mot de passe** ou **clés SSH**.
- Plus flexible et sécurisé que FTP et FTPS.

### ⚠️ Inconvénients du SFTP :
- Moins performant que FTP en raison du chiffrement.
- Peut nécessiter une **configuration spécifique des serveurs** SSH.

---

## 🆚 Différences entre FTP, FTPS et SFTP

| Protocole | Sécurité | Ports utilisés | Chiffrement | Authentification |
|-----------|----------|---------------|------------|----------------|
| **FTP**  | ❌ Aucune | 21 (commandes) + 20 (données en mode actif) | ❌ Non | Nom d'utilisateur / Mot de passe |
| **FTPS** | ✅ SSL/TLS | 21 (explicite) ou 990 (implicite) + ports dynamiques | ✅ Oui | Certificat SSL, Nom d'utilisateur / Mot de passe |
| **SFTP** | ✅ SSH | 22 | ✅ Oui | Mot de passe, Clés SSH |

---

## 🔗 Exemples d'utilisation

✔️ **FTP** : Hébergement de fichiers sur un serveur non sensible à la sécurité.

✔️ **FTPS** : Transfert de fichiers sécurisé pour des entreprises nécessitant une compatibilité avec FTP.

✔️ **SFTP** : Accès sécurisé à des serveurs distants avec chiffrement complet.

---

## ✅ Conclusion

Le choix entre **FTP, FTPS et SFTP** dépend principalement du **niveau de sécurité** requis :
- **FTP** est à éviter pour les transferts sensibles.
- **FTPS** améliore la sécurité tout en conservant la compatibilité avec FTP.
- **SFTP** est la meilleure solution pour une **protection optimale des données**.

💡 **Si la sécurité est une priorité, privilégiez FTPS ou SFTP !** 🔐🚀
