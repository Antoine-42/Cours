# Les Tableaux en C

## Introduction

- **Séance 12 du langage C**  
  Continuité après la séance sur les pointeurs.
- **Objectif**  
  Comprendre la déclaration, l'initialisation, l'accès et la manipulation des tableaux.

## 1. Déclaration et Initialisation

### Déclaration
- **Syntaxe de base :**
  ```c
  int tableau[5];
  ```
- Un tableau stocke **plusieurs valeurs du même type** dans un espace mémoire contigu.

### Initialisation
- **Avec valeurs explicites :**
  ```c
  int tableau[5] = {16, 4, -5, 22, 1888};
  ```
- **Initialisation partielle :**
  - Si vous initialisez une seule valeur, le reste est automatiquement mis à zéro.
  - Exemple :  
    ```c
    int tableau[5] = {4}; // La première case vaut 4, les autres 0.
    ```

## 2. Organisation en Mémoire

- Les **éléments du tableau sont stockés de manière contiguë** en mémoire.
- Chaque case occupe un emplacement consécutif (ex. si `tableau[0]` est à l’adresse 1000, alors `tableau[1]` sera à 1004 pour un `int` sous certains systèmes).

## 3. Accès et Modification des Éléments

- **Accès via indice :**
  - Le premier élément est à l'indice 0 (ex. `tableau[0]`), le dernier à `tableau[taille-1]`.
- **Modification :**
  ```c
  tableau[2] = 14;
  ```
- **Parcours d’un tableau :**
  - Utilisation d’une boucle `for` :
    ```c
    for (int i = 0; i < 5; i++) {
      printf("%d ", tableau[i]);
    }
    ```

## 4. Utilisation des Tableaux dans les Fonctions

### Passage en Paramètre
- **Passage par adresse implicite :**  
  Le nom d’un tableau représente l’adresse de son premier élément.
- **Exemple de fonction d'affichage :**
  ```c
  void afficherTableau(int tab[], int taille) {
      for (int i = 0; i < taille; i++) {
          printf("%d ", tab[i]);
      }
      printf("\n");
  }
  ```

### Retourner un Tableau d'une Fonction
- **Problème courant :**  
  Retourner l’adresse d’une variable locale (qui disparaît à la fin de la fonction).
- **Solution :**  
  Utiliser un tableau **statique** :
  ```c
  int* creerTableau() {
      static int tab[5];
      // Initialisation ou modification du tableau...
      return tab;
  }
  ```

## 5. Bonus : Tableaux à Deux Dimensions

### Déclaration et Initialisation
- **Déclaration d’un tableau 2D :**
  ```c
  int damier[3][2] = {
      {1, 2},
      {3, 4},
      {5, 6}
  };
  ```
- Représente par exemple un damier ou une grille.

### Accès aux Éléments
- **Accès avec deux indices :**
  - `damier[i][j]` où `i` est l'indice de la ligne et `j` celui de la colonne.
- **Parcours avec double boucle :**
  ```c
  for (int i = 0; i < 3; i++) {
      for (int j = 0; j < 2; j++) {
          printf("%d ", damier[i][j]);
      }
      printf("\n");
  }
  ```

## Conclusion

- **Les tableaux sont essentiels en C** pour organiser et manipuler des données.
- Ils sont **étroitement liés aux pointeurs**, ce qui facilite leur utilisation dans les fonctions.
- **Prochaine étape :**  
  La vidéo annonce une suite sur les chaînes de caractères, qui reposent également sur les notions de tableaux et de pointeurs.

---

N'hésitez pas à poser des questions si certains points restent flous !
