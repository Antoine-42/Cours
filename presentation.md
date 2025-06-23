# 🎤 Script oral détaillé – Présentation Naoris (basé sur le diaporama)

---

## 🧾 Slide 1 – Titre

**Slide :**

* NAORIS
* ANTOINE GRAEFF
* PROJET BTS - 2025
* COFFRE-FORT NUMÉRIQUE

🎤 **À dire :**
« Bonjour, je m’appelle Antoine Graëff et je vais vous présenter mon projet de fin d’année intitulé *Naoris*. Il s’agit d’un **coffre-fort numérique personnel** que j’ai entièrement développé.

Ce projet s’inscrit dans une logique d’indépendance, de sécurité et d’utilité concrète : il me permet de stocker et sécuriser mes fichiers et mes mots de passe tout en restant maître de mes données, puisque tout est auto-hébergé. »

---

## 📚 Slide 2 – Contexte : le chemin jusqu’à Naoris

**Slide :**

* PROJET 1 – M5 STACK : Système de sécurité, reconnaissance biométrique, mais trop compliqué à réaliser
* PROJET 2 – NAS PERSONNEL : Nextcloud, fonctionnel mais peu personnalisable et peu de code
* PROJET FINAL : 100 % développé, utile au quotidien, lié à la cybersécurité

🎤 **À dire :**
« Avant d’en arriver à Naoris, j’ai exploré plusieurs pistes.

J’ai d’abord envisagé un projet basé sur un **M5 Stack avec reconnaissance biométrique**, mais j’ai rapidement vu que la mise en œuvre serait très complexe techniquement.

Ensuite, je suis parti sur un **NAS personnel avec Nextcloud**, mais j’ai été limité en personnalisation et en développement réel.

J’ai donc décidé de créer un projet **100 % développé par moi**, qui soit à la fois **utile au quotidien** et en lien direct avec la **cybersécurité**, un domaine qui me passionne. »

---

## 🧠 Slide 3 – Expression des besoins

**Slide :**

* Centraliser mes fichiers
* Sécuriser l’accès
* Accessible de partout
* Gérer plusieurs utilisateurs

🎤 **À dire :**
« Les besoins étaient très concrets. D’abord, **centraliser mes fichiers** importants, qui étaient souvent éparpillés sur différents supports.

Ensuite, **sécuriser l’accès** à ces fichiers : comme ce sont des données sensibles, il fallait une vraie protection.

Je voulais aussi y accéder **de partout**, sans dépendre d’un service tiers, d’où l’idée de l’**auto-hébergement**.

Enfin, je voulais pouvoir **gérer plusieurs utilisateurs**, par exemple si je voulais partager l’outil tout en gardant le contrôle. »

---

## 🛠️ Slide 4 – De l’idée aux fonctionnalités

**Slide :**

1. Centraliser les fichiers : upload, dossiers, prévisualisation
2. Sécuriser l’accès : mot de passe, 2FA, chiffrement, SSL
3. Accès depuis partout : déploiement, nom de domaine, responsive, auto-hébergement
4. Utilisateurs : création, rôles, gestion, historique
5. Dashboard : nombre de fichiers, taille, connexions, mots de passe

🎤 **À dire :**
« J’ai transformé ces besoins en fonctionnalités concrètes :

1. Pour **centraliser**, j’ai intégré le téléversement de fichiers, l’organisation en dossiers, et la **prévisualisation directe** (PDF, images).
2. Pour la **sécurité**, l’accès se fait avec **mot de passe**, une **double authentification** via Google Authenticator, **chiffrement Fernet** et **HTTPS**.
3. Pour l’**accessibilité**, l’interface est responsive, hébergée sur un VPS, et accessible via mon **nom de domaine personnalisé**.
4. Pour la **gestion des utilisateurs**, chaque compte a un rôle (admin ou user), avec gestion des comptes et **historique de connexions**.
5. Enfin, j’ai créé un **dashboard** clair avec des stats : nombre de fichiers, poids total, dernières connexions, nombre de mots de passe. »

---

## 💻 Slide 5 – Architecture générale

**Slide :**

* Utilisateur → Navigateur Web → Serveur Nginx → Application Flask → Base de données → Affichage dynamique

🎤 **À dire :**
« Voici une description détaillée de l’**architecture technique** de Naoris. Mon objectif était de bâtir une infrastructure solide, sécurisée et performante, tout en restant compréhensible et maintenable.

Tout commence par l’**utilisateur**, qui accède à Naoris via un **navigateur web**. Il peut alors interagir avec la plateforme : se connecter, téléverser un fichier, consulter ses mots de passe, etc. Chaque action qu’il réalise génère une requête HTTP.

Cette requête arrive sur mon **serveur Nginx**, que j’ai configuré comme **reverse proxy**. Son rôle est multiple :

* D’une part, il reçoit et filtre les requêtes entrantes.
* D’autre part, il redirige ces requêtes vers l’application web réelle, qui tourne derrière, avec **Gunicorn**.
* Enfin, il assure la **sécurisation des échanges** grâce au **certificat SSL Let’s Encrypt**, pour garantir que toutes les données transmises entre l’utilisateur et le serveur sont chiffrées en HTTPS.

Une fois redirigée, la requête passe par **Gunicorn**, un serveur WSGI, qui permet de faire tourner une application Flask de manière stable et performante, en supportant plusieurs connexions simultanées.

Vient ensuite **Flask**, le cœur applicatif du projet. C’est là que tout est orchestré :

* La gestion des sessions utilisateur (connexion, déconnexion, vérification de rôle...)
* Le contrôle des accès selon le niveau de permissions (user ou admin)
* La gestion de la double authentification (2FA)
* Le traitement des fichiers : envoi, renommage, déplacement, suppression
* Le chiffrement/déchiffrement des mots de passe stockés

Flask s’appuie sur une **base de données SQLite**. Légère mais efficace, elle contient toutes les données nécessaires : comptes utilisateurs, mots de passe (chiffrés avec **Fernet**), historiques de connexion, chemins des fichiers, etc. C’est une solution adaptée pour un projet personnel tout en restant sécurisée.

Lorsque Flask doit générer une page HTML à afficher, il utilise **Jinja2**. C’est un moteur de templates qui permet d’injecter dynamiquement les bonnes données dans les bonnes pages (ex. liste des fichiers, nom de l’utilisateur connecté, statistiques, etc.).

Une fois le traitement terminé, la réponse est renvoyée à **Nginx**, qui la transmet au navigateur de l’utilisateur. Tout ce processus se déroule très rapidement : en quelques millisecondes, la page est générée, sécurisée et affichée à l’écran.

Enfin, tout ce système tourne sur un **serveur VPS Ubuntu chez OVH**, que j’ai entièrement configuré :

* création de l’environnement Python,
* installation des dépendances,
* configuration de Gunicorn et Nginx,
* mise en place du **nom de domaine `naoris.fr`**, avec gestion des **enregistrements DNS**,
* obtention du **certificat SSL**,
* et configuration d’un service `systemd` pour assurer un redémarrage automatique de l’application au boot ou en cas d’erreur.

Cette architecture m’a permis d’apprendre à gérer un vrai déploiement, dans des conditions professionnelles. »

---

## 🧱 Slide 6 – Technologies utilisées

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

## 📈 Slide 7 – Pistes d’évolution

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

## 🙏 Slide 8 – Conclusion

**Slide :**

* Merci pour votre attention
* Place à la démonstration

🎤 **À dire :**
« Merci de m’avoir écouté. Ce projet m’a permis d’apprendre énormément, de progresser dans plein de domaines, et surtout de construire un outil que j’utilise déjà au quotidien.

Je vais maintenant vous faire une démonstration en direct. »
