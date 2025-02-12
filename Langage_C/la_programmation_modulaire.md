### Résumé de la vidéo – **Modularité et Portée des Variables en C**  

Dans cette neuvième séance de la formation en C, on passe à un niveau intermédiaire avec deux notions essentielles : **la modularité** et **la portée des variables**.  

---

### 📌 **1. Modularité en C**  

La modularité consiste à organiser son code en **plusieurs fichiers** pour améliorer la lisibilité et la réutilisation. Cela permet aussi d’intégrer facilement des bibliothèques externes ou du code réutilisable.  

#### 🔹 **Organisation des fichiers :**  
- **Fichiers `.h` (fichiers d’en-tête)** → Contiennent les **prototypes de fonctions** et les **déclarations globales**.  
- **Fichiers `.c` (fichiers source)** → Contiennent l’**implémentation** des fonctions définies dans les `.h`.  
- **Fichier `main.c`** → Point d’entrée du programme.  

#### 🔹 **Exemple d’organisation :**  
- `main.c` → Contient la fonction `main()`, inclut les bibliothèques nécessaires.  
- `player.h` → Contient les prototypes de fonctions liées à un "joueur".  
- `player.c` → Contient l’implémentation des fonctions déclarées dans `player.h`.  

#### 🔹 **Compilation avec plusieurs fichiers :**  
Au lieu de compiler un seul fichier, on compile tous les `.c` avec :  
```bash
gcc *.c -o programme
```
Cela permet de compiler tous les fichiers sources en une seule exécutable.  

#### 🔹 **Protection des fichiers `.h` contre les inclusions multiples :**  
On utilise des **directives de préprocesseur** pour éviter d’inclure plusieurs fois le même fichier d’en-tête :  
```c
#ifndef PLAYER_H  
#define PLAYER_H  

// Prototypes et définitions ici  

#endif
```
Cela empêche les erreurs de compilation dues aux inclusions infinies.

---

### 📌 **2. Portée des Variables en C**  

En C, la **portée** d'une variable détermine **où** elle peut être utilisée et **quand** elle est détruite.  

#### 🔹 **Variables locales :**  
- Déclarées dans une fonction, elles n’existent que pendant l’exécution de cette fonction.  
- Une fois la fonction terminée, elles sont **détruites**.  

#### 🔹 **Variables globales :**  
- Déclarées **en dehors des fonctions**, accessibles partout dans le programme.  
- À éviter autant que possible car elles compliquent la gestion du code.  

#### 🔹 **Le mot-clé `static`**  
- **Dans une fonction** : permet de garder la valeur d’une variable entre plusieurs appels de la fonction.  
- **Dans un fichier** : empêche qu’une variable ou une fonction soit utilisée ailleurs que dans son fichier source.  

**Exemple : Variable `static` dans une fonction**  
```c
void compteur() {
    static int count = 0;  // Garde sa valeur entre chaque appel
    count++;
    printf("Appel numéro : %d\n", count);
}
```
Appeler `compteur();` plusieurs fois affichera une valeur qui **augmente** à chaque appel.

---

### 📌 **Conclusion**  
- **Modularité** = organisation du code en plusieurs fichiers `.c` et `.h` pour mieux structurer les programmes.  
- **Portée des variables** = variables locales détruites en fin de fonction, variables globales accessibles partout.  
- **Le mot-clé `static`** permet de conserver des variables entre appels ou de restreindre leur portée à un fichier.  

Prochaine séance ➡ **Pointeurs et gestion avancée de la mémoire**. 🚀
