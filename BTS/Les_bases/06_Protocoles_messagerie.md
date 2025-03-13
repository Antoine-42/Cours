# 📧 La Messagerie : Protocoles et Transferts

## 1️⃣ Les Protocoles de Messagerie

### ✉️ SMTP - **Simple Mail Transfer Protocol**
Le **SMTP** est un protocole de communication utilisé pour le **transfert de courrier électronique** d’un serveur à un autre.

🔹 **Ports par défaut :**  
- `25` → Non sécurisé, non chiffré  
- `465` → Sécurisé (avec chiffrement SSL/TLS)

---

### 📥 POP - **Post Office Protocol**
Le **POP** permet de **télécharger les e-mails** d’une boîte aux lettres sur un serveur de messagerie vers un client de messagerie (*Outlook, Courrier...*).  

📌 **Particularité :**  
Une fois téléchargé sur un appareil, l’e-mail **n’est plus accessible** sur un autre (exemple : un mail récupéré sur un PC ne sera plus visible sur un téléphone).  

🔹 **Port par défaut :** `110` (non sécurisé)

---

### 🔄 IMAP - **Internet Message Access Protocol**
L’**IMAP** permet de **synchroniser en permanence** les e-mails sur plusieurs appareils (PC, mobile, tablette).  
👉 Contrairement au **POP**, il crée une **copie du message** sur le PC ou le téléphone grâce à la **synchronisation**.

📌 **Avantage :**  
L’état de la boîte aux lettres reste identique sur **tous les appareils**.

🔹 **Ports par défaut :**  
- `143` → Non sécurisé  
- `993` → Sécurisé (chiffrement SSL/TLS)  

---

### 💼 MAPI - **Messaging Application Programming Interface**
Le **MAPI** est un protocole de messagerie **propriétaire de Microsoft**, utilisé pour la communication entre un **client de messagerie** (*Outlook*) et un **serveur Exchange**.

📌 **Avantages :**  
- Synchronisation des **e-mails**, **calendrier** et **contacts**  
- Compatible uniquement avec **Microsoft Outlook**  

🔹 **Flux web en HTTPS :** Port `443`

---

### 📌 Autres Abréviations Importantes  
- **MUA** (*Mail User Agent*) → Client de messagerie (ex : Outlook, Thunderbird)  
- **MTA** (*Mail Transfer Agent*) → Serveur de transfert d’e-mails (ex : Postfix, Sendmail)  
- **MDA** (*Mail Delivery Agent*) → Agent de distribution d’e-mails vers la boîte de réception  

---

## 🎯 Conclusion

Ce document explique les **différents protocoles de messagerie**.


📌 *Document en constante évolution avec de nouvelles informations au fil de l'apprentissage.*