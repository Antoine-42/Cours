# 🖥️ Guide Complet : Mode Audit et Sysprep sur Windows

Ce guide détaillé t'explique clairement le **mode Audit** et l’outil **Sysprep** pour Windows, deux outils indispensables pour préparer des ordinateurs en vue d'un déploiement massif en entreprise.

---

## 🚀 Qu'est-ce que le Mode Audit ?

Le **Mode Audit** est une fonctionnalité de Windows permettant aux administrateurs de configurer, personnaliser et préparer un système d'exploitation avant son déploiement final.

### 📌 Pourquoi utiliser le Mode Audit ?
- Installer des logiciels ou des mises à jour sans créer d’utilisateur spécifique.
- Modifier ou personnaliser l’environnement Windows sans démarrer le processus d’installation utilisateur.
- Préparer des images système propres pour le déploiement.

### 🔧 Comment démarrer en Mode Audit ?

1. Pendant l'installation initiale de Windows, à l'écran « Paramètres régionaux », appuie sur :
   ```
   Ctrl + Maj + F3
   ```
   Le PC redémarre automatiquement en mode Audit.

2. À partir d’un système déjà installé, tu peux lancer manuellement le mode Audit avec la commande suivante :
   ```cmd
   C:\Windows\System32\sysprep\sysprep.exe /audit
   ```

---

## 🛠️ Qu'est-ce que Sysprep ?

L’outil **Sysprep** (System Preparation) prépare les systèmes Windows pour le déploiement ou la capture d’image. Il supprime toutes les informations uniques d'un PC (comme l'ID de sécurité, SID).

### 📌 Pourquoi utiliser Sysprep ?
- Éviter les conflits d’identifiants uniques (SID) dans les environnements réseau.
- Automatiser le déploiement de multiples ordinateurs avec une image de référence.
- Faciliter l’intégration des PC dans des domaines Active Directory.

### 🔧 Comment utiliser Sysprep ?

1. Une fois les configurations réalisées en mode Audit :
   - Lance Sysprep depuis l’invite de commandes en administrateur :
   ```cmd
   C:\Windows\System32\sysprep\sysprep.exe
   ```

2. Choisis les options suivantes :
   - **Généraliser** : pour effacer les informations uniques.
   - **Mode OOBE** (Out-of-Box Experience) : pour que l’utilisateur final personnalise son installation à sa première connexion.
   - Sélectionne « Arrêter » après l'exécution pour capturer l'image via un logiciel dédié (ex : MDT, WDS).

### 🔍 Options principales de Sysprep :

- **/generalize** : Supprime les informations spécifiques (SID, drivers spécifiques).
- **/oobe** : Démarre Windows avec les options d’accueil classiques (création de compte, paramètres régionaux).
- **/audit** : Redémarre en mode Audit après Sysprep.
- **/shutdown** : Éteint le PC après avoir exécuté Sysprep, idéal pour capturer l’image.

### 📝 Exemple concret de commande Sysprep :

```cmd
C:\Windows\System32\sysprep\sysprep.exe /oobe /generalize /shutdown
```

---

## 📸 Capturer une image après Sysprep :

Après avoir exécuté Sysprep et arrêté le système :
- Utilise un outil comme **DISM**, **WDS** ou **MDT** pour capturer l'image.
- Stocke cette image sur un serveur pour un déploiement rapide vers plusieurs ordinateurs.

### Exemple avec DISM :

- Démarre le PC avec un média d’installation Windows.
- Ouvre une invite de commande (Shift + F10) :
  ```cmd
  dism /capture-image /imagefile:C:\Images\image.wim /capturedir:D:\ /name:"Windows Image"
  ```

---

## 🔑 Bonnes pratiques Sysprep :
- Effectue toujours des tests sur une machine de référence avant de généraliser l'image.
- Documente clairement les modifications réalisées dans ton image.
- Garde une copie originale de ton image avant chaque modification majeure.

---
