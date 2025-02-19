# Les Chaînes de Caractères en C

## Introduction

- **Vidéo 13 de la formation C**  
  L'objectif est de comprendre et manipuler les chaînes de caractères, qui sont essentiellement des textes.
- **Notion de base**  
  Une chaîne de caractères en C est implémentée comme un **tableau de `char`**.

## 1. Déclaration et Initialisation

- **Déclaration automatique :**
  - Exemple sans spécifier la taille :
    ```c
    char texte[] = "Bonjour, monde!";
    ```
  - Le compilateur calcule automatiquement la taille en ajoutant le caractère de fin `\0`.

- **Déclaration avec taille fixe :**
  - Exemple en spécifiant la taille :
    ```c
    char prenom[26];
    ```
  - **Attention :**  
    Toujours prévoir une case supplémentaire pour le caractère de fin (`\0`).

## 2. Principe de Fonctionnement

- **Tableau de `char` contigu :**
  - Les caractères sont stockés dans des cases mémoires consécutives.
- **Caractère de fin (`\0`) :**
  - Sert à indiquer la fin de la chaîne.
  - Important pour les fonctions d’affichage et de manipulation (ex. `%s` dans `printf`).

## 3. Affichage et Lecture

- **Affichage :**
  - Utilisation de `%s` dans `printf` :
    ```c
    printf("%s", texte);
    ```
- **Lecture de chaîne :**
  - On peut utiliser `scanf` (ou d'autres fonctions sécurisées) pour lire une chaîne.
  - Veiller à ne pas dépasser la taille du buffer pour éviter les débordements.

## 4. Manipulation avec les Fonctions du `<string.h>`

### Copier une Chaîne

- **`strcpy`**  
  Copie la chaîne source dans la chaîne destination.
  ```c
  strcpy(destination, source);
  ```

### Calculer la Longueur

- **`strlen`**  
  Retourne la longueur de la chaîne (sans compter le `\0`).
  ```c
  size_t longueur = strlen(texte);
  ```

### Comparer des Chaînes

- **`strcmp`**  
  Compare deux chaînes de manière lexicographique.
  - Retourne 0 si elles sont identiques.
  - Retourne un nombre négatif si la première est inférieure, positif sinon.
  ```c
  int result = strcmp(chaine1, chaine2);
  ```

### Concaténer des Chaînes

- **`strcat`**  
  Fusionne deux chaînes.
  ```c
  strcat(destination, source);
  ```

### Écrire dans une Chaîne

- **`sprintf`**  
  Écrit une chaîne formatée dans un buffer (similaire à `printf`).
  ```c
  sprintf(buffer, "Valeur : %d", valeur);
  ```

### Rechercher dans une Chaîne

- **`strchr`**  
  Recherche la première occurrence d’un caractère dans une chaîne.
  ```c
  char *ptr = strchr(texte, 'a');
  ```
- **`strstr`**  
  Recherche une sous-chaîne dans une autre chaîne.
  ```c
  char *ptr = strstr(texte, "mot");
  ```

## 5. Bonnes Pratiques et Précautions

- **Taille des buffers :**
  - Toujours s'assurer que le tableau de `char` est suffisamment grand pour accueillir le texte et le caractère de fin.
- **Sécurité :**
  - Attention aux débordements de mémoire lors de la lecture ou de la copie de chaînes.
  - Utiliser des fonctions sécurisées ou vérifier la taille des entrées.
- **Modification des chaînes :**
  - Une chaîne initialisée avec une valeur fixe ne peut pas être agrandie dynamiquement.
  - Pour modifier une chaîne, il est recommandé d'utiliser des fonctions du `<string.h>` comme `strcpy`.

## Conclusion

- **Essentiel en C :**
  - La gestion des chaînes de caractères est cruciale pour manipuler du texte, afficher des messages et interagir avec l'utilisateur.
- **Fondamentaux à maîtriser :**
  - Comprendre que les chaînes sont des tableaux de `char` se terminant par `\0`.
  - Savoir utiliser les fonctions clés de `<string.h>` pour copier, mesurer, comparer, concaténer et rechercher dans les chaînes.
- **Suite de la formation :**
  - Ces notions serviront de base pour la suite, notamment pour la gestion des fichiers et l'allocation dynamique.

---

N'hésitez pas à poser des questions si certains points restent flous ou à demander des précisions supplémentaires !
