# 🚀 Commandes Utiles pour Windows

Voici quelques commandes pratiques à garder sous la main pour faciliter ton quotidien :

---

## ✅ Vérifier le SID d’un utilisateur

**Ouvre l’invite de commande et tape :**
```cmd
whoami /user
```

---

## 📦 Installer ou Mettre à jour des applications avec Winget

**Dans une fenêtre PowerShell :**

- **Chercher un logiciel :**
```powershell
winget search <nom_du_logiciel>
```

- **Installer un logiciel :**
```powershell
winget install <nom_du_logiciel>
```

- **Voir les mises à jour disponibles :**
```powershell
winget update
```

- **Installer toutes les mises à jour disponibles :**
```powershell
winget update --all
```

---

## 🌐 Afficher les paramètres réseau

**Ouvre l’invite de commande (ou exécute avec `Windows + R`) et tape :**
```cmd
ncpa.cpl
```

---

## 📋 Voir le presse-papier récent

**Raccourci clavier :** `Windows + V`

> 📌 *Pense à activer cette fonctionnalité la première fois !*

---

## 👤 Créer un compte local (sans lier à un compte Microsoft)

Lors de l’installation de Windows :
- Ouvre une invite de commande avec `SHIFT + F10`
- Entre la commande :
```cmd
OOBE\BYPASSNRO
```
- L’ordinateur redémarre, puis choisis : **« Je n’ai pas Internet » → « Continuer avec une installation limitée »**

---

🎯 **Document évolutif au fil du temps.**

