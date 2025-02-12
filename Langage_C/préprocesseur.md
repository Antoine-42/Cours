### Les Directives du Préprocesseur en C  

Cette séance aborde **les directives du préprocesseur**, une partie essentielle du langage C. Ce n'est pas la session la plus passionnante, car elle est **très théorique**, mais elle est **indispensable** pour comprendre des concepts avancés comme les **tableaux, structures et énumérations**.

#### 🔹 **Qu'est-ce que le préprocesseur ?**  
Le préprocesseur est **un sous-programme** qui s'exécute **avant la compilation** pour **modifier le code source** selon certaines directives (`#include`, `#define`, etc.).  

---

### 📌 **Principales directives du préprocesseur**  

#### ✅ **1. `#include` – Inclure un fichier**  
- Permet **d'ajouter du code externe** (ex: bibliothèques standard comme `stdio.h`).
- **Deux syntaxes** :  
  - `<stdio.h>` → Pour les bibliothèques standard.  
  - `"mon_fichier.h"` → Pour ses propres fichiers.  
- S'exécute **avant la compilation** pour rendre le code utilisable.

#### ✅ **2. `#define` – Définir une constante**  
- Permet de créer des **valeurs constantes** utilisées partout dans le code.  
- Exemple :  
  ```c
  #define TVA 20
  ```
  - Avantage : **Si la valeur change**, on modifie seulement le `#define` et pas tout le code !  
  - Peut être utilisé aussi pour **remplacer des instructions** (ex : renommer `printf` par `afficher`).  

#### ✅ **3. `#ifndef`, `#define`, `#endif` – Protection des fichiers `.h`**  
- Empêche **les inclusions infinies** quand un fichier inclut un autre.  
- Syntaxe classique dans un fichier `.h` :  
  ```c
  #ifndef MON_FICHIER_H
  #define MON_FICHIER_H
  
  // Déclarations de fonctions ou constantes
  
  #endif
  ```
- Vérifie si `MON_FICHIER_H` **est déjà défini** avant d'inclure le fichier une nouvelle fois.  

#### ✅ **4. Constantes prédéfinies en C**  
Quelques **macros utiles** fournies par le préprocesseur :  
- `__FILE__` → Nom du fichier en cours.  
- `__LINE__` → Ligne du fichier.  
- `__DATE__` → Date de compilation.  
- `__TIME__` → Heure de compilation.  
- Permet d'afficher des infos de **debugging** facilement.

---

### 🎯 **Conclusion**  
- Le **préprocesseur** prépare le code **avant la compilation**.
- `#include` ajoute des fichiers.  
- `#define` définit des **constantes** ou remplace du code.  
- `#ifndef` protège les **fichiers `.h`** pour éviter des **inclusions infinies**.  
- Quelques **constantes prédéfinies** existent pour le debug.  

👉 **Prochaine séance : Les pointeurs** – Un sujet clé du langage C.  
💡 **Astuce :** S'entraîner à utiliser `#define` et `#ifndef` en créant ses propres bibliothèques `.h`.
