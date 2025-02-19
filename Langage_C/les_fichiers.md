# Gestion des Fichiers en C (Séance 16)

## Introduction

- **Objectif :**  
  Découvrir la gestion des fichiers en mode texte (lecture, écriture, positionnement, renommage, suppression) en C.
- **Contexte :**  
  Dernière séance sur les notions de base avant d’aborder des sujets plus avancés (structures de données, 2D, réseau, programmation système).

## 1. Ouverture et Fermeture de Fichiers

- **Ouverture d'un fichier :**  
  Utilisation de la fonction `fopen` avec différents modes d'ouverture.
  - **Modes courants :**
    - `"r"` : Lecture seule (le fichier doit exister).
    - `"w"` : Écriture seule (le fichier est créé ou écrasé).
    - `"a"` : Ajout en fin de fichier (crée le fichier si inexistant).
    - `"r+"` : Lecture/écriture (le fichier doit exister).
- **Vérification :**
  ```c
  FILE *fic = fopen("sauvegarde.txt", "r");
  if (fic == NULL) {
      fprintf(stderr, "Erreur d'ouverture du fichier\n");
      exit(1);
  }
  ```
- **Fermeture :**  
  Toujours fermer le fichier avec `fclose(fic);` pour libérer les ressources.

## 2. Lecture des Fichiers

- **Lecture caractère par caractère :**
  - Utilisation de `fgetc(fic)` qui retourne le caractère lu ou `EOF` en fin de fichier.
- **Lecture ligne par ligne :**
  - Utilisation de `fgets(buffer, taille, fic)` qui lit une ligne (avec gestion du caractère de fin `\0`).
- **Lecture formatée :**
  - Utilisation de `fscanf` (similaire à `scanf`) pour lire des données formatées depuis un fichier.

## 3. Écriture dans les Fichiers

- **Écriture caractère par caractère :**
  - Utilisation de `fputc(caractère, fic);`
- **Écriture de chaînes de caractères :**
  - Utilisation de `fputs(chaine, fic);`
  - Ou encore `fprintf(fic, "format", ...)` pour écrire du texte formaté, similaire à `printf`.

## 4. Positionnement dans le Fichier

- **Fonctions de positionnement :**
  - `ftell(fic)` : Retourne la position actuelle du curseur.
  - `fseek(fic, offset, origine)` : Déplace le curseur vers une position spécifique.
    - `origine` peut être `SEEK_SET` (début), `SEEK_CUR` (position actuelle) ou `SEEK_END` (fin).
  - `rewind(fic)` : Ramène le curseur au début du fichier.
- **Utilité :**  
  Permet de lire ou d'écrire à des positions spécifiques dans un fichier.

## 5. Renommage et Suppression de Fichiers

- **Renommer un fichier :**
  - Utilisation de `rename("ancien_nom", "nouveau_nom");`
- **Supprimer un fichier :**
  - Utilisation de `remove("nom_du_fichier");`
  - **Attention :**  
    Le fichier est supprimé définitivement (il n'est pas envoyé à la corbeille).

## 6. Fonctions Complémentaires

- **Fonctions sécurisées :**  
  Certaines fonctions comme `fgets` limitent la lecture à un nombre de caractères défini, évitant ainsi les débordements.
- **Lecture formatée avancée :**  
  Utilisation de `fscanf` pour récupérer plusieurs données (texte, entiers, etc.) en une seule opération.

## Conclusion

- **Bilan :**  
  La séance a présenté les principaux outils pour gérer les fichiers en C, de l'ouverture à la fermeture, en passant par la lecture, l'écriture et le positionnement.
- **Importance :**  
  Ces notions sont essentielles pour manipuler des données stockées dans des fichiers, étape fondamentale avant de passer à des concepts plus avancés (structures de données, programmation système, etc.).
- **Prochaines étapes :**  
  La prochaine séance abordera les structures de données, qui s'appuieront sur toutes les notions vues (pointeurs, tableaux, fichiers, etc.).

---

N'hésitez pas à poser des questions ou à demander des précisions sur certains points !
