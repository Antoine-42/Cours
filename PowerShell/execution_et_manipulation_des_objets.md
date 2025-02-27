# PowerShell - Partie 2 : Exécution de Scripts et Manipulation des Objets



## 1. Exécution de Scripts PowerShell
### Sécurité et politique d'exécution
Par défaut, PowerShell bloque l'exécution des scripts pour des raisons de sécurité. Pour permettre leur exécution, il faut modifier la politique avec la commande suivante (exécutée en mode administrateur) :

```powershell
Set-ExecutionPolicy RemoteSigned
```

Explication des options :
- `Restricted` : Aucun script ne peut être exécuté.
- `RemoteSigned` : Les scripts locaux sont autorisés, mais ceux téléchargés nécessitent une signature.
- `Unrestricted` : Tous les scripts peuvent être exécutés sans restriction.

### Lancer un script PowerShell
Un script PowerShell est un fichier avec l'extension `.ps1`. Pour exécuter un script, utilisez :

```powershell
.\MonScript.ps1
```

Ou, si le fichier est dans un autre dossier :

```powershell
C:\Scripts\MonScript.ps1
```

Si un message d'erreur apparaît, vérifiez la politique d'exécution :

```powershell
Get-ExecutionPolicy
```

---

## 2. Manipulation des Objets PowerShell
Contrairement aux commandes CMD classiques qui renvoient du texte brut, PowerShell fonctionne avec des objets, ce qui permet de manipuler directement les données.

### a) Afficher les propriétés d'un objet
PowerShell permet d'obtenir des informations détaillées sur un élément du système. Par exemple, pour afficher les propriétés de processus en cours d'exécution :

```powershell
Get-Process | Select-Object Name, Id, CPU
```

Cette commande affiche uniquement le **nom**, l'**ID** et l'utilisation **CPU** des processus actifs.

### b) Filtrer des résultats
On peut filtrer des objets avec `Where-Object`. Par exemple, pour afficher uniquement les processus utilisant plus de 10 unités CPU :

```powershell
Get-Process | Where-Object {$_.CPU -gt 10}
```

Ici, `$_` représente l'objet en cours d'examen.

### c) Trier des données
On peut trier les résultats avec `Sort-Object`. Exemple :

```powershell
Get-Process | Sort-Object CPU -Descending
```

Cela trie les processus par utilisation CPU, du plus gourmand au moins gourmand.

### d) Exporter des résultats
Il est possible d'enregistrer les résultats dans un fichier CSV pour une analyse ultérieure :

```powershell
Get-Process | Select-Object Name, Id, CPU | Export-Csv -Path C:\processus.csv -NoTypeInformation
```

---

## 3. Prochaines Étapes
Dans la prochaine partie, nous verrons comment gérer les fichiers et dossiers avec PowerShell : création, suppression, modification et automatisation de tâches de gestion des fichiers.
