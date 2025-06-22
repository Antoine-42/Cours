# Injection SQL

 ## Description détaillée


Une injection SQL est une faille de sécurité qui va permettre a une personne d'attaquer un site par exemple. Pour cela il va faire des injections de code notament des requetes SQL qui sont malveillantes et donc qui est en lien avec une base de données. Cela est possible lorsque des donnees ne sont pas correctement filtrés et que le site n'est pas assez sécurisé.

## Risques sur le système

Une injection SQL peut entraîner plusieurs problèmes graves :

Un vol de données : la personne qui attaque peut lire toutes les tables de la base de données.

Modification des données : ajout, modification ou suppression de données.

Prise de contrôle de comptes (ex. admin).

Avoir acces au serveur et donc faire des commandes en tout genre.

## Sécurisation (bases essentielles)

Installer les mises à jour de sécurité dès leur publication pour les logiciels de base de données et serveurs web.

Octroyer les privilèges minimums requis aux comptes qui accèdent à la base SQL (principe du moindre privilège).

Éviter l’utilisation de comptes partagés entre plusieurs applications ou sites web.

Valider toutes les entrées utilisateur, y compris celles provenant de menus déroulants ou boutons radio. Même des champs "contrôlés" peuvent être manipulés.

Utiliser des requêtes préparées (requêtes paramétrées) qui empêchent l'insertion de code SQL dans les données.

Configurer un système de gestion des erreurs sécurisé : les messages d’erreur doivent être enregistrés dans des logs internes et ne jamais s’afficher dans le navigateur. Cela empêche les attaquants d’obtenir des informations sur la base ou la structure du site.

#  XSS (Cross-Site Scripting)

XSS signifie cross-site scripting, c'est une vulnérabilité qui va permettrea une personne malveillante d'injecter du code JavaScript dans une page web. Il va ensuite etre executé par les utilisateurs du site. XSS vise donc les utilisateurs des sites et pas directement le serveur.

Il existe plusieurs types de XSS :

Réfléchi : le code est injecté via un lien ou un formulaire, et exécuté immédiatement.

Persistant : le code est stocké dans la base de données (ex. dans un commentaire), puis affiché à tous les visiteurs.

DOM-based : l’injection passe uniquement par le JavaScript côté client.

## Les Risques

Vol de cookies ou de sessions (ex : pirater une connexion utilisateur)

Modification visuelle du site

Phishing : insertion de faux formulaires pour voler des identifiants

Propagation de malwares via des scripts injectés


## Sécurisation

Traiter toutes les données comme potentiellement dangereuses
On ne doit jamais faire confiance aux données reçues, même si elles viennent d’un utilisateur connecté.

Encoder les données (échappement)

Avant d'afficher des données dans une page web, on remplace les caractères spéciaux (comme <, >, ", ') par leurs équivalents HTML (ex: < devient &lt;).
Cela empêche le navigateur d’exécuter du code injecté par un attaquant.

Filtrer les données
Avant de stocker ou d’utiliser les données, on élimine les balises ou mots dangereux
Ce filtrage s’applique en entrée (quand l’utilisateur envoie des données) et en sortie (avant de les afficher).

Valider les entrées utilisateur
On vérifie que les données ont le bon type et le bon format (ex: un champ téléphone ne doit pas accepter de texte ou de balises HTML).

Utiliser une politique de sécurité du contenu (CSP)
CSP (Content Security Policy) est une règle définie côté serveur qui limite les sources autorisées pour les scripts.
Même si un script malveillant est injecté, le navigateur refusera de l’exécuter s’il ne provient pas d’une source de confiance.

# Brute Force

Le Brut Force a un objectif, tester automatiquement le plus grand nombre de combinaisons de mots de passe pour acceder a un compte ou a un systeme. Il va donc faire des essaues succesifs j'usqua trouver la bonne combinaison.

Il existe plusieurs formes :

Brute force classique : on teste toutes les combinaisons possibles.

Dictionnaire : on teste une liste de mots de passe connus.

Attaque ciblée : on se base sur des informations connues de la victime.

## Les Risques
Il existe plusieurs risques: 

Une connexion non autorisée à des comptes utilisateurs ou administrateurs

Un blocage ou ralentissement du service à cause du grand nombre de tentatives

Un vol de données personnelles

Une utilisation malveillante de comptes compromis.

## Sécurisation

Limiter les tentatives de connexion
Après un certain nombre d’échecs (ex : 5), bloquer temporairement le compte ou l’adresse IP.

Utiliser un CAPTCHA
Empêche les robots automatisés de continuer à essayer des mots de passe.

Imposer des mots de passe forts
Exiger un mot de passe avec : majuscules, minuscules, chiffres, caractères spéciaux, et longueur minimale (ex : 10 caractères).

Mettre en place l’authentification à deux facteurs (2FA)
Même si le mot de passe est deviné, un code temporaire (envoyé par SMS ou appli mobile) est nécessaire pour se connecter.

# Sécurisation d'une base MySQL

Dans le TP FlopSecurity, la gestion des utilisateurs sur la base de données MySQL contribue sûrement à la sécurité de l’architecture, selon plusieurs principes. Tout d’abord, les rôles sont bien distincts : le compte root est pour l’administration système, le compte dba pour gérer les bases, le compte flopsecurity pour l’application web. Ainsi, une faille dans l’application n’entraîne pas l’accès au serveur de la base de données.

Ensuite, chaque compte a exactement les droits pour les fonctions qu’il exerce. Par exemple, l’utilisateur flopsecurity n’accède qu’à la base de données du même nom. La base de données système mysql ou performance_schema lui est accessible. Limiter les utilisateurs permet de réduire énormement les conséquences d’une attaque, comme une injection SQL : l’attaquant est limité par la portée de son accès.

Le TP montre qu’il vaut mieux restreindre les connexions à quelques hôtes seulement. Par exemple, un utilisateur peut être défini pour pouvoir uniquement se connecter en local (@localhost), ce qui empêche des connexions non souhaitées vers l’extérieur.

Pour finir, la configuration prévoit l’activation des logs de MySQL (logs généraux, logs des requêtes lentes et logs des requêtes sans index qui remontent les comportements anormaux et facilitent ultérieurement un audit des bases de données). Ce qui montre l’application du principe du moindre privilège incontournable pour la sécurité dans une base de données, et montre des bonnes pratiques pour un environnement de production.

# Connexion SSH

Pour renforcer la sécurité d’une connexion SSH, il faut  adapter la configuration par défaut d’OpenSSH. En premier, on empêchera la connexion directe avec le compte root afin d’obliger les administrateurs à passer par un utilisateur standard, on peut désactiver de manière obligatoire l’authentification par mot de passe (PasswordAuthentication no) et on ne dotera que de clés SSH non prévisibles par exemple.

Modifier le port par défaut utilisé pour le service SSH (passer de 22 à 2222 par exemple) permet d’échapper à certains scanners automatiques. On peut restreindre l’accès SSH à certains utilisateurs grâce au paramètre AllowUsers.

# Firewall

Le firewall se définit ici comme un dispositif de sécurité du réseau, permettant des filtrages de trafic entre un ordinateur (ou serveur) et le réseau de raccordement, dans le but de bloquer les connexions suspectes, et de laisser passer uniquement celles utiles au bon fonctionnement du système. Par exemple, sur un serveur web on n’autorise que les ports 80 (HTTP), 443 (HTTPS) et 22 (SSH), et on bloque Reste des autres.

Sous Linux, pour le configurer, on peut avoir recours à un outil simple, ufw, qui va pouvoir gérer les règles.
Par défaut, on appliquera une politique de sécurité stricte : toutes les connexions entrantes sont refusées, les connexions sortantes sont permises. On ouvrira ensuite uniquement les ports nécessaires avec la commande sudo ufw allow 22 ou sudo ufw allow 80.

Les paramètres que l’on peut définir sont les ports, protocoles (TCP ou UDP), adresses IP autorisées ou interdites, services. On peut définir des règles différentes pour l’entrée et la sortie activer les logs, prioriser certaines connexions.
Ainsi, bien configuré, le firewall agit comme un filtre, protège le serveur de nombreuses attaques réseau, et ne laisse passer que ce qui est utile.

# Rôle des autres solutions de sécurisation

Parmi les autres solutions pour sécuriser un serveur,il y a  les mises à jour système. En effet, de nombreuses failles de sécurité sont découvertes en permanence dans les logiciels. Ces failles sont en général rapidement corrigées. Ainsi, faire des mises à jour permet de se protéger contre des failles déjà connues, sans modifier son application. C’est un moyen simple d’éviter de nombreuses attaques.

Par la suite, les paramètres de configuration d’Apache2 ont également un impact non négligeable sur la sécurité. Les réglages par défaut ne doivent pas être conservés. En particulier, des modules inutiles doivent être désactivés, la version du serveur masquée, l’accès aux directories critiques restreint, ainsi que de s’assurer que des en-têtes HTTP de sécurité comme Content-Security-Policy, X-Frame-Options, etc. sont utilisés. Cela permet de réduire les risques d’attaques par injection ou d’accès non autorisé à certains fichiers.

Enfin, on peut se demander si la réécriture d’URL a une influence sur la sécurité. En elle même, elle ne protège pas le serveur, mais elle diminue la visibilité sur la structure interne, par exemple on ne montrera pas un fichier sous la forme page.php?id=2 mais on affichera une URL un peu plus propre, sous la forme /article/2. Cela cache les paramètres et rend un peu plus difficile certaines attaques, en particulier les injections simples. Cependant, une mauvaise configuration de la réécriture peut devenir elle même une faille, donc à manipuler avec prudence.

# Veille technologique

La veille technologique permet de rester à jour , c’est-à-dire suivre les recommandations publiées par des organismes spécialisés comme l’ANSSI ou l’OWASP.

L’ANSSI (Agence nationale de la sécurité des systèmes d’information) propose plusieurs documents très utiles pour sécuriser un site web. Par exemple, le "Guide d’hygiène informatique" nous donne des regles de bases aappliques (mots de passe, mises à jour, droits d’accès, etc.). L’ANSSI publie aussi des guides de configuration sécurisée pour des logiciels comme Apache, MySQL ou OpenSSH. Enfin, elle propose régulièrement des bulletins d’alerte (CERT-FR) qui informent sur les failles récentes ou les attaques en cours.

De son côté, l’OWASP est une organisation internationale qui s’occupe spécialement de la sécurité des applications web. Il existe le  Top 10 OWASP, une liste des 10 principales failles de sécurité rencontrées sur les sites web. On peut retrouver dans ce top 10 par exemple 
– les injections, faille XSS etc...