# 🔹 Variables et Types de Données en PowerShell

---

## 📌 Introduction aux Variables

En PowerShell, une **variable** est un espace de stockage permettant de conserver une valeur pour une utilisation ultérieure. Toutes les variables commencent par un `$` suivi du nom de la variable.

📌 **Exemple de déclaration et d'affichage d'une variable :**
```powershell
$nom = "Antoine"  # Stocke une chaîne de caractères
$age = 25          # Stocke un nombre entier
$estAdmin = $true  # Stocke un booléen

Write-Output $nom  # Affiche "Antoine"
Write-Output $age  # Affiche 25
Write-Output $estAdmin  # Affiche True
```

PowerShell détecte automatiquement le type de la variable en fonction de la valeur que tu lui assignes.

---

## 📌 Les Types de Données en PowerShell

### 🔹 Chaînes de caractères (String)
Les chaînes de caractères sont utilisées pour stocker du texte.
```powershell
$message = "Bienvenue sur PowerShell"
Write-Output $message  # Affiche "Bienvenue sur PowerShell"
```

**Concaténation de chaînes :**
```powershell
$prenom = "Antoine"
$salutation = "Bonjour, " + $prenom  # Ajoute du texte
Write-Output $salutation  # Affiche "Bonjour, Antoine"
```

Avec **interpolation** :
```powershell
Write-Output "Bonjour, mon nom est $prenom."
```

---

### 🔹 Nombres (Integer, Double)
PowerShell supporte différents types de nombres :
```powershell
$entier = 42  # Nombre entier
$flottant = 3.14  # Nombre à virgule flottante
```

**Opérations mathématiques :**
```powershell
$somme = 10 + 5  # Addition
$produit = 10 * 2  # Multiplication
Write-Output $somme  # Affiche 15
Write-Output $produit  # Affiche 20
```

---

### 🔹 Booléens (Boolean)
Les valeurs booléennes permettent de représenter vrai ou faux.
```powershell
$estConnecte = $true  # Vrai
$estDeconnecte = $false  # Faux
```
**Utilisation d'un booléen dans une condition :**
```powershell
if ($estConnecte) {
    Write-Output "Utilisateur connecté."
} else {
    Write-Output "Utilisateur non connecté."
}
```

---

### 🔹 Tableaux (Arrays)
Les tableaux permettent de stocker plusieurs valeurs dans une seule variable.
```powershell
$jours = @("Lundi", "Mardi", "Mercredi")
Write-Output $jours[0]  # Affiche "Lundi"
```

**Ajouter un élément :**
```powershell
$jours += "Jeudi"
Write-Output $jours  # Affiche Lundi, Mardi, Mercredi, Jeudi
```

---

### 🔹 HashTables (Dictionnaires)
Un **Hashtable** est une collection de paires clé/valeur.
```powershell
$personne = @{ Nom = "Antoine"; Age = 25; Ville = "Paris" }
Write-Output $personne["Nom"]  # Affiche "Antoine"
```

---

## 📌 Conversion de Types
PowerShell permet de convertir une variable d'un type à un autre.
```powershell
$nombreTexte = "123"
$nombreConverti = [int]$nombreTexte
Write-Output ($nombreConverti + 1)  # Affiche 124
```
Autres conversions possibles : `[string]`, `[bool]`, `[array]`, etc.

---

✅ **Prochaine étape :** [Les Opérateurs en PowerShell](04_Operateurs.md)

