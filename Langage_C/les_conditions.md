# Les Conditions en C

## Introduction

- **Contexte :**  
  Après avoir vu les opérateurs, cette séance aborde les structures conditionnelles pour effectuer des tests sur des variables ou sur des retours de fonction.
- **Objectif :**  
  Apprendre à utiliser les instructions conditionnelles (`if`, `else if`, `else`, le ternaire et le `switch`) pour diriger l'exécution d'un programme en fonction de conditions.

## 1. La structure `if`

- **Fonction :**  
  Permet d'exécuter un bloc d'instructions uniquement si une condition donnée est vraie.
- **Syntaxe :**
  ```c
  if (condition) {
      // instructions à exécuter si la condition est vraie
  }
  ```
- **Astuce :**  
  Si le bloc contient une seule instruction, les accolades sont facultatives, mais il est conseillé de les utiliser pour améliorer la lisibilité.

## 2. Les structures `else if` et `else`

- **`else if` :**  
  Permet de chaîner plusieurs conditions pour tester différentes situations.
- **`else` :**  
  Exécute un bloc d'instructions lorsque toutes les conditions précédentes sont fausses.
- **Exemple :**
  ```c
  if (nombre == 0) {
      printf("nombre vaut zéro\n");
  } else if (nombre < 20) {
      printf("nombre est inférieur à 20\n");
  } else {
      printf("nombre est supérieur ou égal à 20\n");
  }
  ```

## 3. Opérateurs de comparaison

- **`==`** : Teste l'égalité.
- **`!=`** : Teste la non-égalité.
- **`<`, `<=`, `>`, `>=`** : Comparaison numérique.

## 4. Les opérateurs logiques

- **`&&` (ET) :**  
  Toutes les conditions doivent être vraies.
- **`||` (OU) :**  
  Au moins une condition doit être vraie.

## 5. L'opérateur ternaire

- **Fonction :**  
  Permet de réaliser une affectation conditionnelle de façon concise.
- **Syntaxe :**
  ```c
  condition ? valeur_si_vrai : valeur_si_faux;
  ```
- **Exemple :**
  ```c
  int est15 = (age == 15) ? 1 : 0;
  ```
  Ce code affecte `1` à `est15` si `age` est égal à 15, sinon `0`.

## 6. La structure `switch`

- **Fonction :**  
  Permet de tester une seule variable contre plusieurs valeurs possibles.
- **Syntaxe :**
  ```c
  switch(variable) {
      case valeur1:
          // instructions pour valeur1
          break;
      case valeur2:
          // instructions pour valeur2
          break;
      // ...
      default:
          // instructions si aucune valeur ne correspond
          break;
  }
  ```
- **Astuce :**  
  Utiliser `break` à la fin de chaque case pour éviter un comportement inattendu.

## Conclusion

- **Bilan :**  
  - Les structures conditionnelles permettent de contrôler le flux d'exécution d'un programme selon des tests logiques.
  - L'opérateur ternaire offre une syntaxe compacte pour affecter rapidement le résultat d'un test.
  - Le `switch` simplifie la gestion de plusieurs cas sur une seule variable.
- **Prochaine étape :**  
  La prochaine séance portera sur les boucles, une autre notion clé pour contrôler l'exécution répétée d'instructions.
---
