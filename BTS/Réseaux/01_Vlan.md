# 🌐 Cours Complet sur les VLANs (Débutant → Avancé)

---

## 🧩 MODULE 1 : INTRODUCTION AUX VLANs (DÉBUTANT)

### 📌 Définition
- **VLAN (Virtual Local Area Network)** : Réseau local virtuel.
- Permet de **segmenter un réseau physique** en plusieurs réseaux logiques.
- Chaque VLAN correspond à un **domaine de broadcast distinct**.

### 🧠 Pourquoi utiliser des VLANs ?
- Sécurité : Isolation du trafic entre VLANs.
- Organisation : Regrouper les utilisateurs par service (ex : RH, IT).
- Réduction du broadcast.
- Meilleure gestion du réseau.

### 📚 Exemple simple
- VLAN 10 : Service Informatique
- VLAN 20 : Service Comptabilité
- VLAN 30 : Service RH

Les machines de VLAN 10 ne peuvent pas communiquer directement avec celles de VLAN 20 sans un **routeur** ou **Layer 3 Switch**.

---

## 🔧 MODULE 2 : FONCTIONNEMENT TECHNIQUE DES VLANs

### 🎛️ Types de ports
- **Access Port** : Port affecté à un seul VLAN. Utilisé pour connecter des terminaux.
- **Trunk Port** : Port capable de transporter plusieurs VLANs. Utilisé entre switches ou vers un routeur.

### 📦 Encapsulation (IEEE 802.1Q)
- Ajout d'un tag VLAN (4 octets) dans la trame Ethernet.
- Trame 802.1Q = [Préambule] + [En-tête 802.1Q] + [Données] + [CRC]
- VLAN ID : 12 bits (possibles de 1 à 4094)

### 📍 VLAN par défaut
- VLAN 1 est actif par défaut sur tous les ports.
- Il transporte le trafic de gestion (CDP, STP, VTP...).

---

## 🏗️ MODULE 3 : CONFIGURATION VLANs SUR CISCO IOS (INTERMÉDIAIRE)

### 🛠️ Créer des VLANs
```bash
Switch(config)# vlan 10
Switch(config-vlan)# name Informatique
Switch(config)# vlan 20
Switch(config-vlan)# name Comptabilite
