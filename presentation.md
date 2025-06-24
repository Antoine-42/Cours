# 🎤 Script oral détaillé – Présentation Naoris (basé sur le diaporama)

---

## 🧾 Slide 1 – Titre

« Bonjour, je m’appelle Antoine Graëff et je vais vous présenter mon projet de fin d’année intitulé *Naoris*. Il s’agit d’un **coffre-fort numérique personnel** que j’ai entièrement développé.

Ce projet s’inscrit dans une logique d’indépendance, de sécurité et d’utilité concrète : il me permet de stocker et sécuriser mes fichiers et mes mots de passe tout en restant maître de mes données, puisque tout est auto-hébergé. »

---

## 📚 Slide 2 – Contexte : le chemin jusqu’à Naoris

« Avant d’en arriver à Naoris, j’ai exploré plusieurs pistes.

J’ai d’abord envisagé un projet basé sur un **M5 Stack avec reconnaissance biométrique**, mais j’ai rapidement vu que la mise en œuvre serait très complexe techniquement.

Ensuite, je suis parti sur un **NAS personnel avec Nextcloud**, mais j’ai été limité en personnalisation et en développement réel.

J’ai donc décidé de créer un projet **100 % développé par moi**, qui soit à la fois **utile au quotidien** et en lien direct avec la **cybersécurité**, un domaine qui me passionne. »

---

## 🧠 Slide 3 – Expression des besoins

« Les besoins étaient très concrets. D’abord, **centraliser mes fichiers** importants, qui étaient souvent éparpillés sur différents supports.

Ensuite, **sécuriser l’accès** à ces fichiers : comme ce sont des données sensibles, il fallait une vraie protection.

Je voulais aussi y accéder **de partout**, sans dépendre d’un service tiers, d’où l’idée de l’**auto-hébergement**.

Enfin, je voulais pouvoir **gérer plusieurs utilisateurs**, par exemple si je voulais partager l’outil tout en gardant le contrôle. »

---

## 🛠️ Slide 4 – De l’idée aux fonctionnalités

« J’ai transformé ces besoins en fonctionnalités concrètes :

1. Pour **centraliser**, j’ai intégré le téléversement de fichiers, l’organisation en dossiers, et la **prévisualisation directe** (PDF, images).
2. Pour la **sécurité**, l’accès se fait avec **mot de passe**, une **double authentification** via Google Authenticator, **chiffrement Fernet** et **HTTPS**.
3. Pour l’**accessibilité**, l’interface est responsive, hébergée sur un VPS, et accessible via mon **nom de domaine personnalisé**.
4. Pour la **gestion des utilisateurs**, chaque compte a un rôle (admin ou user), avec gestion des comptes et **historique de connexions**.
5. Enfin, j’ai créé un **dashboard** clair avec des stats : nombre de fichiers, poids total, dernières connexions, nombre de mots de passe. »

---
## 🧱 Slide5. Technologies utilisées

**Slide :**

* Utilisateur : interface responsive, intuitive
* Interface web : HTML/CSS/Jinja2, onglets
* Base de données : traitement sécurisé des données
* Backend Flask : sessions, rôles, 2FA, chiffrement Fernet
* Stockage local : fichiers par utilisateur, gestion complète
* Sécurité et déploiement : VPS OVH, Gunicorn, Nginx, SSL, nom de domaine

🎤 **À dire :**
« J’ai utilisé un ensemble de technologies complémentaires :

* L’**interface utilisateur** est claire, responsive, avec une navigation par onglets.
* Le front est en **HTML/CSS/Jinja2**, et le backend en **Flask**. C’est lui qui gère les sessions, les rôles utilisateurs, la 2FA, et le chiffrement.
* La **base de données SQLite** gère les comptes, fichiers et mots de passe, avec un traitement sécurisé.
* Les fichiers sont stockés **localement** sur le serveur, dans des dossiers propres à chaque utilisateur.
* Le tout est déployé sur un **VPS OVH**, avec **Gunicorn + Nginx**, **certificat SSL**, et **nom de domaine personnel**. »

---

💻 Slide 7 – Comment ça fonctionne
L’utilisateur accède à Naoris depuis son navigateur web. Quand il se connecte, envoie un fichier ou consulte un mot de passe, il envoie une requête HTTP.

Cette requête passe par :

Nginx
➤ Sert de reverse proxy : il reçoit la requête, la sécurise avec HTTPS (Let’s Encrypt), puis la redirige vers l’application.

Gunicorn
➤ C’est un serveur qui permet de faire tourner mon application Flask de manière fluide, même avec plusieurs utilisateurs.

Flask
➤ C’est le cœur du projet :

Gère les connexions et permissions

Gère la 2FA (double authentification)

Traite les fichiers et les mots de passe

Génère les pages HTML avec Jinja2

SQLite
➤ Petite base de données qui stocke tout : utilisateurs, mots de passe (chiffrés avec Fernet), fichiers, logs...

Une fois la réponse prête, elle est renvoyée via Nginx jusqu’au navigateur. Tout ça se passe en quelques millisecondes.

🖥️ L’ensemble tourne sur un serveur VPS Ubuntu OVH avec mon nom de domaine naoris.fr. J’ai tout installé moi-même : Python, Nginx, Gunicorn, SSL, DNS, et système de redémarrage automatique (systemd).




## 📈 Slide 8 – Pistes d’évolution

**Slide :**

* Export Keepass ou CSV
* Extension Chrome
* Audit & logs
* Application mobile

🎤 **À dire :**
« Voici les pistes d’évolution envisagées pour Naoris :

* Un **export Keepass ou CSV** des mots de passe, pour assurer une portabilité.
* Une **extension Chrome** pour le remplissage automatique des mots de passe.
* Un système de **logs et d’audit**, avec historique des actions, IP, appareil utilisé…
* Et à terme, une **application mobile**, pour une utilisation encore plus fluide sur smartphone. »

---

## 🙏 Slide 9 – Conclusion

**Slide :**

* Merci pour votre attention
* Place à la démonstration

🎤 **À dire :**
« Merci de m’avoir écouté. Ce projet m’a permis d’apprendre énormément, de progresser dans plein de domaines, et surtout de construire un outil que j’utilise déjà au quotidien.

Je vais maintenant vous faire une démonstration en direct. »


# 🧠 Rappel des outils utilisés
🔹 Flask
Framework Python léger pour créer des applications web.
C’est lui qui gère toutes les fonctionnalités de Naoris : connexions, routes, traitement des fichiers, affichage des pages…

🔹 Gunicorn
C’est un serveur WSGI. Il sert d’intermédiaire entre Flask et Nginx.
Il permet de lancer Flask de manière stable et performante, avec plusieurs utilisateurs en même temps.

🔹 Nginx
C’est un serveur web.
Il sert de reverse proxy, filtre les requêtes, les sécurise avec le protocole HTTPS (certificat SSL), puis les redirige vers Gunicorn.

🔹 Jinja2
C’est un moteur de templates utilisé par Flask pour créer les pages HTML.
Il permet d’insérer dynamiquement du contenu (comme le nom de l’utilisateur ou la liste de fichiers) dans les pages.

🔹 Flask
C’est un outil en Python qui sert à créer un site web.
Il me permet de gérer les pages, les connexions, les boutons, les actions des utilisateurs...
👉 On appelle ça un framework : en gros, c’est une boîte à outils déjà prête pour créer plus vite un site ou une application.

🔹 Gunicorn
Flask tout seul n’est pas fait pour accueillir plein d’utilisateurs à la fois.
Gunicorn sert à faire tourner Flask de façon plus solide et rapide, surtout quand plusieurs personnes utilisent le site en même temps.
👉 C’est ce qu’on appelle un serveur WSGI : un programme qui "connecte" Python à Internet.

🔹 Nginx
C’est un gardien d’entrée. Il reçoit les demandes des utilisateurs (ex : "je veux me connecter"), les filtre, les sécurise avec le HTTPS, puis les envoie à Gunicorn.
👉 C’est ce qu’on appelle un reverse proxy.

🔹 Jinja2
Quand Flask doit créer une page web (ex : liste des fichiers), Jinja2 sert à remplir automatiquement la page avec les bonnes infos (nom du fichier, utilisateur connecté, etc.).
👉 C’est un remplisseur intelligent de pages HTML.
