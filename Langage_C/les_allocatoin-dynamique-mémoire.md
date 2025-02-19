# Allocation Dynamique de Mémoire en C

## Introduction

- **Séance 15** de la formation en langage C.
- Objectif : Réserver et gérer dynamiquement des zones mémoire pour des données dont la taille n'est pas connue à l'avance (ex. : nombre de joueurs dans un jeu).

## 1. Inclusion des Bibliothèques

- **Header à inclure :**
  - `#include <stdio.h>` pour les entrées/sorties.
  - `#include <stdlib.h>` pour les fonctions d'allocation dynamique (malloc, calloc, realloc, free).

## 2. Exemple d'Application

- **Contexte :**  
  Créer un tableau dynamique (liste) de joueurs dont le nombre est déterminé par l'utilisateur.
- **Processus :**
  - Demander à l'utilisateur le nombre de joueurs (via `scanf`).
  - Stocker ce nombre dans une variable (ex. `int nb_joueurs;`).

## 3. Utilisation de malloc et calloc

- **malloc :**
  - Alloue un espace mémoire non initialisé.
  - Exemple :
    ```c
    int *liste_joueurs = malloc(nb_joueurs * sizeof(int));
    ```
- **calloc :**
  - Alloue et initialise à zéro.
  - Exemple :
    ```c
    int *liste_joueurs = calloc(nb_joueurs, sizeof(int));
    ```

## 4. Vérification de l'Allocation

- **Tester si l'allocation a réussi :**
  ```c
  if (liste_joueurs == NULL) {
      fprintf(stderr, "Erreur d'allocation mémoire\n");
      exit(1);
  }
  ```
- Permet d’éviter les accès à une zone mémoire non allouée.

## 5. Utilisation et Affichage

- **Initialisation et remplissage :**
  - Utiliser une boucle `for` pour remplir le tableau (ex. : stocker une valeur calculée comme `i * 3` pour chaque joueur).
- **Affichage :**
  - Parcourir le tableau et afficher les valeurs pour vérifier le bon fonctionnement.

## 6. Réallocation de la Mémoire (realloc)

- **But :**  
  Ajuster la taille d'une zone mémoire déjà allouée (par exemple, si le nombre de joueurs change en cours d'exécution).
- **Syntaxe :**
  ```c
  int *nouvelle_liste = realloc(liste_joueurs, nouvelle_taille * sizeof(int));
  if (nouvelle_liste == NULL) {
      fprintf(stderr, "Erreur de réallocation\n");
      exit(1);
  }
  liste_joueurs = nouvelle_liste;
  ```
- **Remarque :**
  - L'adresse mémoire peut changer après `realloc`.

## 7. Libération de la Mémoire

- **Libérer la mémoire allouée dynamiquement :**
  ```c
  free(liste_joueurs);
  ```
- **Importance :**
  - Pour éviter les fuites de mémoire, chaque appel à `malloc` (ou `calloc`/`realloc`) doit être suivi d'un `free` lorsque la mémoire n'est plus nécessaire.

## Conclusion

- L'allocation dynamique de mémoire permet de gérer efficacement des données dont la taille varie à l'exécution.
- C'est une compétence essentielle pour écrire des programmes flexibles et efficaces en C.
- La prochaine vidéo abordera la gestion des fichiers, une autre notion clé du langage C.

---

N'hésitez pas à poser des questions si certains points nécessitent des éclaircissements !
