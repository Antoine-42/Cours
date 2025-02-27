# 🔢 Les Opérateurs en PowerShell

---

## 📌 Introduction

Les **opérateurs** en PowerShell permettent d'effectuer des calculs, des comparaisons, des opérations logiques et bien plus encore. Ils sont essentiels pour manipuler des données et contrôler le flux d'exécution d'un script.

---

## 🔹 Opérateurs Arithmétiques
Ces opérateurs servent à effectuer des opérations mathématiques sur des nombres.

| Opérateur | Description | Exemple |
|-----------|------------|---------|
| `+` | Addition | `5 + 3  # 8` |
| `-` | Soustraction | `10 - 4  # 6` |
| `*` | Multiplication | `6 * 7  # 42` |
| `/` | Division | `20 / 4  # 5` |
| `%` | Modulo (reste) | `10 % 3  # 1` |

📌 **Exemple d'utilisation :**
```powershell
$nombre1 = 10
$nombre2 = 4
$somme = $nombre1 + $nombre2
Write-Output "La somme est : $somme"
```

---

## 🔹 Opérateurs de Comparaison
Ces opérateurs permettent de comparer des valeurs et retournent `$true` ou `$false`.

| Opérateur | Description | Exemple |
|-----------|------------|---------|
| `-eq` | Égalité | `5 -eq 5  # True` |
| `-ne` | Différent | `5 -ne 3  # True` |
| `-gt` | Supérieur à | `10 -gt 7  # True` |
| `-lt` | Inférieur à | `2 -lt 5  # True` |
| `-ge` | Supérieur ou égal | `6 -ge 6  # True` |
| `-le` | Inférieur ou égal | `3 -le 4  # True` |

📌 **Exemple d'utilisation :**
```powershell
$age = 18
if ($age -ge 18) {
    Write-Output "Tu es majeur."
} else {
    Write-Output "Tu es mineur."
}
```

---

## 🔹 Opérateurs Logiques
Ces opérateurs permettent de combiner plusieurs conditions.

| Opérateur | Description | Exemple |
|-----------|------------|---------|
| `-and` | ET logique | `(5 -gt 3) -and (10 -lt 20)  # True` |
| `-or` | OU logique | `(5 -gt 10) -or (20 -lt 30)  # True` |
| `-not` | Négation | `-not(5 -eq 5)  # False` |

📌 **Exemple d'utilisation :**
```powershell
$admin = $true
$connecte = $false
if ($admin -and $connecte) {
    Write-Output "Accès autorisé."
} else {
    Write-Output "Accès refusé."
}
```

---

✅ **Prochaine étape :** [Les Structures de Contrôle](05_Structures_Controle.md)

