### Les Boucles en C

Les boucles sont un concept fondamental en programmation. Elles permettent de répéter un ensemble d’instructions plusieurs fois, sans avoir à les écrire manuellement à chaque itération. Dans le langage C, il existe trois types principaux de boucles : `while`, `do...while` et `for`. Chacune a ses particularités et est utilisée dans des cas spécifiques.

---

## 1. La boucle `while`

La boucle `while` exécute un bloc de code **tant qu’une condition est vraie**. Cela signifie que si la condition est fausse dès le départ, le bloc de code ne sera jamais exécuté.

### Structure de la boucle `while` :
```c
while (condition) {
    // Instructions à exécuter tant que la condition est vraie
}
```
### Exemple :
```c
int i = 0;
while (i < 5) {
    printf("Message %d\n", i);
    i++;
}
```
Dans cet exemple :
- `i` commence à `0`.
- Tant que `i < 5`, la boucle s’exécute et affiche un message.
- À chaque tour, `i` est incrémenté.
- Quand `i` atteint `5`, la condition devient fausse et la boucle s’arrête.

⚠️ **Attention aux boucles infinies** : Si on oublie d’incrémenter `i`, la condition `i < 5` sera toujours vraie et la boucle ne s’arrêtera jamais, ce qui peut faire planter le programme.

---

## 2. La boucle `do...while`

La boucle `do...while` est similaire à la boucle `while`, à la différence près qu’elle **s’exécute toujours au moins une fois**, même si la condition est fausse dès le début.

### Structure :
```c
do {
    // Instructions exécutées au moins une fois
} while (condition);
```

### Exemple :
```c
int i = 10;
do {
    printf("Affiché au moins une fois\n");
    i++;
} while (i < 5);
```
Dans ce cas :
- `i` vaut `10`, donc la condition `i < 5` est fausse dès le départ.
- **Mais** le bloc de code s’exécute **une fois** avant de tester la condition.
- Ensuite, comme `i < 5` est faux, la boucle ne recommence pas.

Cette boucle est utile lorsqu’on veut **garantir qu’un bloc de code s’exécute au moins une fois** avant de vérifier une condition.

---

## 3. La boucle `for`

La boucle `for` est particulièrement utile lorsque l’on connaît à l’avance **le nombre exact d’itérations**. Contrairement aux boucles `while`, qui nécessitent une initialisation externe et une mise à jour de la variable de boucle, la boucle `for` intègre **trois parties** directement dans sa structure :

### Structure :
```c
for (initialisation ; condition ; mise à jour) {
    // Instructions répétées
}
```

### Exemple :
```c
for (int i = 0; i < 5; i++) {
    printf("Tour %d\n", i);
}
```
Explication :
1. `int i = 0;` → La variable `i` est initialisée à `0` avant le début de la boucle.
2. `i < 5;` → La condition est testée avant chaque itération. Si elle est vraie, la boucle continue ; sinon, elle s’arrête.
3. `i++` → À la fin de chaque itération, `i` est incrémenté de 1.

Cette boucle est **idéale** pour les situations où on sait combien de fois répéter l’action. 

Exemple d'utilisation pour parcourir un tableau :
```c
int tab[] = {10, 20, 30};
for (int i = 0; i < 3; i++) {
    printf("%d\n", tab[i]);
}
```
Ici, on utilise `for` pour parcourir un tableau de 3 éléments et afficher chaque valeur.

---

## 4. Les mots-clés `break` et `continue`

Parfois, on veut **interrompre une boucle avant son terme** ou **passer une itération** sans exécuter tout le bloc.

### `break` : quitter la boucle immédiatement
Si une condition spécifique est remplie, on peut **sortir immédiatement de la boucle**.

Exemple :
```c
for (int i = 0; i < 5; i++) {
    if (i == 2) break; // Stoppe la boucle quand i vaut 2
    printf("%d\n", i);
}
```
Résultat affiché :
```
0
1
```
Dès que `i == 2`, l’instruction `break` arrête la boucle.

### `continue` : sauter une itération
Le mot-clé `continue` permet de **passer directement à l’itération suivante** sans exécuter le reste du bloc.

Exemple :
```c
for (int i = 0; i < 5; i++) {
    if (i == 2) continue; // Passe à l'itération suivante quand i == 2
    printf("%d\n", i);
}
```
Résultat affiché :
```
0
1
3
4
```
Quand `i == 2`, `continue` saute cette itération et la boucle reprend au tour suivant.

---

### Quand utiliser quelle boucle ?
- **`while`** : Utilisé quand on ne sait pas à l’avance combien de fois la boucle doit s’exécuter.
- **`do...while`** : Quand on veut que le code s’exécute **au moins une fois** avant de vérifier la condition.
- **`for`** : Idéal quand on connaît **le nombre exact d’itérations**, notamment pour **parcourir des tableaux**.

---

Les boucles sont essentielles pour **optimiser et simplifier le code** en évitant les répétitions inutiles. Elles permettent d’exécuter efficacement des tâches comme **le parcours de données, les calculs itératifs et la gestion d’événements**.
