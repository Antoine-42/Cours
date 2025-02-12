### Les Fonctions en C

Les fonctions sont un élément clé de la programmation en C. Elles permettent de structurer le code, d'éviter les répétitions et d'améliorer la lisibilité. Une fonction regroupe un ensemble d'instructions sous un nom spécifique, pouvant être réutilisé plusieurs fois dans un programme.

---

## 1. Principe des Fonctions

Une fonction en C suit une structure bien définie :
1. **Type de retour** : indique la nature de la valeur retournée par la fonction (`int`, `float`, `void`, etc.).
2. **Nom de la fonction** : doit respecter les règles de nommage des variables.
3. **Paramètres** : valeurs passées à la fonction pour son exécution.
4. **Corps de la fonction** : contient les instructions exécutées à l'appel de la fonction.
5. **Valeur de retour** (optionnelle) : donnée renvoyée par la fonction à la fin de son exécution.

---

## 2. Déclaration et Définition d'une Fonction

### Exemple simple :
```c
#include <stdio.h>

// Déclaration de la fonction (prototype)
int addition(int a, int b);

int main() {
    int resultat = addition(10, 5);
    printf("Résultat : %d\n", resultat);
    return 0;
}

// Définition de la fonction
int addition(int a, int b) {
    return a + b;
}
```
### Explication :
- **Déclaration** : `int addition(int a, int b);` annonce la fonction avant son utilisation.
- **Définition** : la fonction est implémentée plus bas dans le code.
- **Appel de fonction** : `addition(10, 5);` exécute la fonction en lui passant `10` et `5` comme arguments.
- **Valeur de retour** : le `return` envoie le résultat (`a + b`) à la fonction appelante.

⚠️ **Pourquoi une déclaration ?**  
Si la définition de la fonction apparaît après le `main()`, il est nécessaire d’informer le compilateur de son existence via un prototype.

---

## 3. Les Paramètres et Valeurs de Retour

### Fonction avec paramètre et retour
```c
int multiplier(int x, int y) {
    return x * y;
}
```
Ici, la fonction prend deux entiers et retourne leur produit.

### Fonction sans paramètre et sans retour
```c
void afficherMessage() {
    printf("Bonjour !\n");
}
```
Elle ne prend **aucun paramètre** (`void`) et ne retourne rien.

### Fonction avec paramètre mais sans retour
```c
void afficherNombre(int nombre) {
    printf("Le nombre est : %d\n", nombre);
}
```
Elle affiche simplement une valeur sans renvoyer de résultat.

---

## 4. L'Utilité des Fonctions

Les fonctions permettent de **factoriser** le code, évitant ainsi de répéter plusieurs fois les mêmes instructions.  
Exemple avec un programme de jeu où une balle doit être réinitialisée à une position donnée :

```c
int initialiserPosition() {
    return 100; // La position initiale
}

int main() {
    int balleX = initialiserPosition();
    printf("Position de départ : %d\n", balleX);
    return 0;
}
```
Si l’on doit modifier la position de départ, il suffit de changer **une seule ligne** dans la fonction `initialiserPosition()`.

---

## 5. Passage de Paramètres et Portée des Variables

Les variables déclarées dans une fonction sont **locales**, c'est-à-dire accessibles uniquement dans cette fonction.  
Exemple :
```c
void test() {
    int a = 10; // Cette variable est propre à test()
}
```
Si on tente d’accéder à `a` dans une autre fonction, on obtiendra une erreur.

### Passage par valeur vs passage par adresse
- **Par valeur** : Une copie du paramètre est créée.
- **Par adresse (pointeurs)** : Permet de modifier directement la variable passée.

Exemple :
```c
void modifierValeur(int *x) {
    *x = 20;
}

int main() {
    int nombre = 10;
    modifierValeur(&nombre);
    printf("Valeur après modification : %d\n", nombre);
    return 0;
}
```
Ici, `modifierValeur()` modifie directement `nombre` via un pointeur.

---

## 6. Prototype et Organisation du Code

Dans des programmes plus complexes, il est préférable de **séparer** les fonctions du `main()` pour une meilleure lisibilité.  
On utilise alors des **prototypes** en haut du fichier :

```c
#include <stdio.h>

// Prototype
int somme(int a, int b);

int main() {
    int resultat = somme(4, 3);
    printf("Somme : %d\n", resultat);
    return 0;
}

// Définition après le main()
int somme(int a, int b) {
    return a + b;
}
```
Le prototype permet au **compilateur** de savoir qu’une fonction existe avant d’être définie plus bas.

---

## 7. Conclusion

Les fonctions sont essentielles pour **structurer** et **modulariser** un programme. Elles permettent de :
- Éviter la répétition de code.
- Faciliter la lecture et la maintenance.
- Rendre le programme plus flexible et évolutif.

Dans la prochaine partie, nous verrons **comment organiser un programme en plusieurs fichiers** pour améliorer encore plus la lisibilité et la gestion du code.
