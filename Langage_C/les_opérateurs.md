
# Les opérateurs fondamentaux:

## Les différents types d'opérations:

\+ (addition)  
\- (soustraction)  
\* (multiplication)  
/ (Division)  
% (modulo, qui donne le reste d’une division entière)  

L’opérateur modulo est particulièrement utile pour vérifier si un nombre est pair ou impair (nombre % 2 == 0) et a des applications en cryptographie.

### Les calculs en C peuvent être effectués :

* Directement dans le code (printf("%d", 6 + 4);).  
* Avec des variables (int somme = a + b;).  
* Dans des scénarios dynamiques, comme la mise à jour du niveau d’un joueur (niveau_joueur = niveau_joueur + 1;).  
* Les opérateurs d'affectation combinés permettent de simplifier l’écriture des opérations courantes.

### Exemples:

a += x; équivaut à a = a + x;  
a -= x;, a *= x;, a /= x;, a %= x; fonctionnent de la même manière.  

### Pour incrémenter ou décrémenter une variable de 1, on peut utiliser :

a++; ou ++a; pour ajouter 1.
a--; ou --a; pour soustraire 1.
La différence entre pré-incrémentation (++a) et post-incrémentation (a++) est subtile et devient importante dans certaines affectations.

### Les priorités:

Concernant la priorité des opérateurs, la multiplication (*), la division (/) et le modulo (%) sont prioritaires sur l’addition (+) et la soustraction (-). L’utilisation de parenthèses permet de forcer un ordre spécifique dans les calculs.

En conclusion, ces opérateurs et concepts sont fondamentaux en C et seront réutilisés dans la suite de l’apprentissage, notamment avec les structures conditionnelles et les boucles.
