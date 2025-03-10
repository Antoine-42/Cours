# Les adresses IP et l'architecture du processeur

## Les adresses IP

### Définition :
Une adresse IP identifie chaque équipement connecté à un réseau informatique.

### Types d'adresses IP :
- **IPv4** : Adresses composées de 4 valeurs (0-255) séparées par des points, ex : `192.168.1.1`.
- **IPv6** : Adresses hexadécimales avec 8 groupes séparés par des deux-points, ex : `1987:0C00:0000:0000`.

### Classes d'adresses IPv4 :
- **Classe A** : Entre `1 et 126` → Pour les grands réseaux avec beaucoup d’hôtes.
- **Classe B** : Entre `128 et 191` → Pour les réseaux de taille moyenne.
- **Classe C** : Entre `192 et 223` → Pour les réseaux locaux.
- **Classe D** : Entre `224 et 239` → Pour les réseaux multicast.
- **Classe E** : Entre `240 et 255` → Réservée pour la recherche et le développement.

### Adresses IP privées :
- Utilisées pour les équipements sur des réseaux locaux (**intranet**).
- Non utilisables directement sur Internet (**non routables**).

### Adresses IP publiques :
- Utilisées uniquement sur **Internet**.
- Adresses uniques dans le monde.

---

## Architecture d’un processeur

Il existe **deux types d’architectures** : **32 bits** et **64 bits**.  
Cela fait référence à la façon dont le processeur d’un ordinateur traite les informations.  
Un processeur **64 bits** traite une plus grande quantité de données qu’un processeur **32 bits**.  
👉 **Le 64 bits est donc plus rapide qu’un système 32 bits.**

---

## Le binaire

- **1 bit** est un nombre binaire et peut adopter deux valeurs : `0` et `1`.
- **Un ordinateur fonctionne avec des nombres binaires**, effectue des calculs et sauvegarde des informations sous forme binaire.
- **Un byte** est composé de **8 bits** :
  - `8 bits = 1 octet = 1 byte`

---

## Processeur VCPU

Un **vCPU (Virtual CPU)** est une unité de calcul attribuée à une **machine virtuelle (VM)** dans un environnement virtualisé.  
Il représente généralement un **thread logique** d'un processeur physique.  

### Importance :
- Le nombre de **vCPU** affecte les performances de la **VM**.
- Une mauvaise gestion des vCPU peut entraîner une **surcharge des ressources**.

---

## Sauvegarde de type WORM

Une sauvegarde de type **WORM** (**Write Once, Read Many**) est une technologie permettant **d'écrire des données une seule fois**, sans possibilité de modification ou suppression ultérieure.

### Caractéristiques :
- Utilisée pour répondre à des **exigences réglementaires**.
- Garantit **l'intégrité des données critiques**.
- Souvent utilisée dans les **secteurs financiers, juridiques ou médicaux**.

### Supports :
- **Physiques** : Disques optiques, bandes magnétiques.
- **Cloud / Logiciel** : Solutions de stockage sécurisées.

---