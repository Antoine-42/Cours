# 🛠️ Installation et Premiers Pas avec PowerShell

---

## 📥 Installation de PowerShell
PowerShell est disponible sur **Windows, Linux et macOS**. Voici comment l'installer selon ton système d'exploitation.

### 🔹 Windows
Depuis Windows 10, PowerShell est préinstallé, mais une version plus récente peut être installée.

📝 **Vérifier la version actuelle** :
```powershell
$PSVersionTable.PSVersion
```

📌 **Installer la dernière version** :
- 📥 **Via le Microsoft Store** : [Télécharger ici](https://aka.ms/powershell)
- 💻 **Via la ligne de commande** :
  ```powershell
  winget install --id Microsoft.Powershell --source winget
  ```

---

### 🔹 Linux
PowerShell est disponible sous plusieurs distributions Linux. Voici l’installation pour les plus courantes :

- 🐧 **Ubuntu / Debian** :
  ```bash
  sudo apt update && sudo apt install -y powershell
  ```
- 🔵 **CentOS / Fedora** :
  ```bash
  sudo dnf install -y powershell
  ```
- 🎯 **Arch Linux** :
  ```bash
  sudo pacman -S powershell
  ```

---

### 🔹 macOS
🍏 L'installation se fait via Homebrew :
```bash
brew install --cask powershell
```

---

## 🚀 Lancer PowerShell
Une fois installé, ouvre PowerShell :

- **Windows** : Cherche "PowerShell" dans le menu Démarrer et ouvre **PowerShell** ou **PowerShell (Admin)**.
- **Linux/macOS** : Ouvre un terminal et tape :
  ```bash
  pwsh
  ```

---

## ✅ Tester PowerShell
Pour vérifier que tout fonctionne, entre la commande suivante :
```powershell
Write-Output "Hello, PowerShell!"
```

📢 Si "Hello, PowerShell!" s'affiche, tu es prêt à commencer ! 🎉

---

✅ **Prochaine étape :** [Les variables_et_types_de_donnees de PowerShell](03_Variables_et_Types_de_Donnees.md)

