# Structures, Typedef, Énumérations et Unions en C

## Introduction

- **Vidéo n°14** de la formation en langage C.
- Sujet : Création de types de données personnalisés.
- Contexte : Illustré avec l'exemple d'un joueur dans un jeu vidéo.

## 1. Structures en C

### Définition

- Une **structure** permet de regrouper plusieurs variables (données) en une seule entité.
- Exemple : Un joueur (`player`) avec plusieurs attributs (nom d'utilisateur, points de vie, points de magie).

### Déclaration et Initialisation

- **Déclaration d'une structure** :
  ```c
  struct player {
      char username[256];
      int hp;
      int mp;
  };
  ```
- **Initialisation** :
  ```c
  struct player p1 = {"MonPseudo", 100, 100};
  ```
- **Accès aux champs** :  
  Utiliser l'opérateur `.`  
  Exemple : `p1.username`, `p1.hp`, `p1.mp`.

### Modification des Champs

- Pour les types numériques, affectation directe (ex. `p1.hp = 50;`).
- Pour les chaînes de caractères, utiliser `strcpy` :
  ```c
  strcpy(p1.username, "Naoki");
  ```

## 2. Typedef pour Créer un Nouveau Type

- **Objectif** : Simplifier la syntaxe en créant un alias pour une structure.
- **Exemple avec typedef** :
  ```c
  typedef struct player {
      char username[256];
      int hp;
      int mp;
  } player;
  ```
- Après typedef, déclaration d'une variable :
  ```c
  player p1;
  ```

## 3. Passage par Pointeurs et Accès via la Flèche

- Pour modifier une structure dans une fonction, on passe son adresse.
- **Accès aux champs via un pointeur** :
  - Utiliser l'opérateur `->` (équivalent à `(*p).champ`).
  - Exemple : Si `p` est un pointeur vers un `player`, accéder à son nom avec `p->username`.

## 4. Énumérations (enum)

### Définition

- Permet de définir un ensemble de constantes nommées.
- Exemple : Définir un type booléen.
  ```c
  enum boolean { FALSE, TRUE };
  ```
- Par défaut, la première valeur vaut 0, la suivante 1, etc.

### Utilisation avec Typedef

- Pour créer un alias et simplifier l'utilisation :
  ```c
  typedef enum { FALSE, TRUE } boolean;
  ```

## 5. Unions

### Définition

- Une **union** regroupe plusieurs types de données dans **la même zone mémoire**.
- Seul un membre peut être utilisé à un instant donné.

### Exemple

- Déclaration d'une union pour stocker un nombre entier ou un flottant :
  ```c
  union number {
      int i;
      float f;
  };
  ```
- **Utilité** : Permet d’optimiser l’utilisation de la mémoire en partageant le même espace pour différentes représentations d'une donnée.

## 6. Remarques Supplémentaires

- **Champs de bits** :  
  - Mentionnés brièvement pour contrôler l'usage de la mémoire au niveau du bit (particulièrement utile en environnement embarqué).
- **Applications Pratiques** :
  - Les structures, énumérations et unions sont essentielles pour organiser des données complexes (ex. : gérer des personnages de jeu, des configurations, etc.).
  - Elles facilitent la lecture et la maintenance du code.

## Conclusion

- **Maîtriser ces concepts** est fondamental pour la programmation en C.
- Ils permettent de créer des types de données sur mesure, de mieux organiser les informations et de gérer efficacement la mémoire.
- La suite de la formation abordera d'autres notions comme l'allocation dynamique et la gestion de fichiers.

---

N'hésitez pas à poser des questions si certains points nécessitent plus de précisions !
