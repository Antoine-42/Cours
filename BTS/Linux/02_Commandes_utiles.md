# 🐧 Commandes Linux Essentielles

Voici une liste claire et utile des commandes Linux les plus importantes pour débuter et gérer efficacement ton système au quotidien.

---

## 🖥️ Gestion du Système

- Afficher le répertoire courant :
```bash
pwd
```

- Lister les fichiers et dossiers :
```bash
ls
ls -l (affiche les détails)
ls -a (affiche les fichiers cachés)
```

- Se déplacer entre dossiers :
```bash
cd dossier (pour entrer dans un dossier)
cd .. (revenir au dossier précédent)
cd ~ (revenir au dossier personnel)
```

- Créer un dossier :
```bash
mkdir nom_dossier
```

- Supprimer fichiers/dossiers :
```bash
rm fichier (supprime un fichier)
rm -r dossier (supprime un dossier et son contenu)
```

- Copier ou déplacer des fichiers :
```bash
cp fichier /destination
mv fichier /destination (déplacer)
```

---

## 🔍 Gestion de fichiers

- Afficher le contenu d'un fichier :
```bash
cat fichier
```

- Afficher les premières/dernières lignes d’un fichier :
```bash
head fichier (début du fichier)
tail fichier (fin du fichier)
```

- Éditer un fichier texte :
```bash
nano fichier
vim fichier
```

---

## 📂 Permissions et droits

- Changer les droits d'un fichier/dossier :
```bash
chmod 755 fichier
```

- Modifier le propriétaire d’un fichier/dossier :
```bash
chown utilisateur fichier
```

---

## 🖥️ Gestion du système

- Afficher l’espace disque :
```bash
df -h
```

- Afficher la mémoire disponible :
```bash
free -h
```

- Vérifier l’utilisation des ressources :
```bash
top
htop
```

---

## 🌐 Réseaux

- Afficher l'adresse IP et configurations réseau :
```bash
ip addr
ifconfig
```

- Tester la connectivité vers un site web :
```bash
ping google.com
```

- Vérifier la connectivité réseau :
```bash
ping 8.8.8.8
```

---

## ⚙️ Gestion des paquets

- Installer un logiciel :
```bash
apt install nom_du_paquet (Debian/Ubuntu)
yum install nom_du_paquet (CentOS/Fedora)
```

- Mettre à jour les logiciels :
```bash
apt update && apt upgrade
```

- Supprimer un logiciel :
```bash
apt remove nom_du_paquet
```

---

## 🔧 Gestion du système

- Éteindre ou redémarrer :
```bash
shutdown now
reboot
```

- Redémarrer un service :
```bash
systemctl restart nom_du_service
```

---


