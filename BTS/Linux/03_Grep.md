# 🐧 Guide Complet : Utilisation de `grep` sur Ubuntu

La commande **`grep`** est un outil puissant sous Linux permettant de rechercher des motifs spécifiques dans des fichiers ou des flux de données. Ce guide détaille son utilisation sur Ubuntu.

---

## 🔍 Introduction à `grep`

`grep` (Global Regular Expression Print) permet de rechercher du texte en fonction d'un motif dans un ou plusieurs fichiers. Il est couramment utilisé pour filtrer des logs, extraire des informations et analyser du texte.

### 📌 Syntaxe de base :
```bash
grep [OPTIONS] "motif" fichier
```
- `motif` : texte ou expression régulière à rechercher.
- `fichier` : fichier(s) à analyser.

---

## 📚 Exemples d'utilisation de `grep`

### 🔎 Recherche simple dans un fichier
Rechercher le mot "erreur" dans `syslog` :
```bash
grep "erreur" /var/log/syslog
```

### 🔍 Recherche récursive dans les fichiers d’un dossier
Chercher "password" dans tous les fichiers du dossier actuel et sous-dossiers :
```bash
grep -r "password" ./
```

### 🔢 Afficher le numéro de ligne des résultats
Afficher les lignes avec leur numéro contenant "failed" :
```bash
grep -n "failed" /var/log/auth.log
```

### 📂 Rechercher un mot dans plusieurs fichiers
```bash
grep "ERROR" fichier1.txt fichier2.txt
```

### 🚫 Exclure les lignes contenant un mot
Afficher toutes les lignes sauf celles contenant "warning" :
```bash
grep -v "warning" fichier.log
```

---

## 🔧 Options les plus utiles avec `grep`

- `-i` : Ignore la casse (majuscules/minuscules).
- `-v` : Affiche les lignes **ne contenant pas** le motif.
- `-n` : Affiche le **numéro des lignes** correspondantes.
- `-c` : Compte le **nombre de lignes** contenant le motif.
- `-l` : Affiche uniquement les **noms des fichiers** contenant le motif.
- `-E` : Utilisation d’**expressions régulières avancées**.
- `--color=auto` : Met en évidence le motif recherché dans les résultats.

Exemple :
```bash
grep --color=auto -i "root" /etc/passwd
```

---

## 🎯 Exemples avancés

### 📂 Rechercher plusieurs mots (OU logique)
```bash
grep -E "erreur|failed|warning" fichier.log
```

### 🔠 Recherche insensible à la casse
```bash
grep -i "erreur" fichier.log
```

### 📊 Compter les occurrences d’un mot
```bash
grep -c "connexion" fichier.log
```

### 📋 Filtrer les processus en cours
Rechercher les processus Apache actifs :
```bash
ps aux | grep "apache"
```

### 🔗 Grep avec `find` pour rechercher dans des fichiers spécifiques
```bash
find /var/log -name "*.log" | xargs grep "error"
```

---

## 📢 Astuces supplémentaires

- `egrep` et `fgrep` sont des variantes de `grep`, mais `grep -E` est recommandé pour les regex avancées.
- `grep` est souvent utilisé avec d’autres commandes comme `awk` et `sed` pour des traitements plus avancés.

---

🎯 **Conclusion**

`grep` est un outil incontournable pour la gestion et l’analyse de texte sous Linux. Sa combinaison avec d’autres commandes permet une automatisation efficace et une recherche rapide d’informations précises. 🚀🐧

