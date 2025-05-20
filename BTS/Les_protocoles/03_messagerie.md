# 📧 Protocoles de messagerie : SMTP, POP3, IMAP et MAPI

## 📌 Introduction

La messagerie électronique repose sur plusieurs protocoles qui assurent l'envoi, la réception et la gestion des e-mails. Les principaux protocoles utilisés sont :

* **SMTP** (Simple Mail Transfer Protocol) : pour l'envoi des e-mails.
* **POP3** (Post Office Protocol version 3) : pour la récupération des e-mails en local.
* **IMAP** (Internet Message Access Protocol) : pour la gestion des e-mails en ligne.
* **MAPI** (Messaging Application Programming Interface) : pour une intégration avancée avec Microsoft Exchange.

---

## 📤 SMTP : Simple Mail Transfer Protocol

### Fonctionnement

* **Rôle** : achemine les e-mails du client vers le serveur de messagerie, puis vers le serveur du destinataire.
* **Ports utilisés** :

  * 25 : port standard non sécurisé.
  * 465 : port sécurisé (SMTPS).
  * 587 : port sécurisé recommandé pour l'envoi authentifié.
* **Processus** :

  1. Le client envoie l'e-mail au serveur SMTP.
  2. Le serveur SMTP utilise les enregistrements DNS (MX) pour localiser le serveur du destinataire.
  3. L'e-mail est transféré au serveur du destinataire.

---

## 📥 POP3 : Post Office Protocol version 3

### Fonctionnement

* **Rôle** : télécharge les e-mails du serveur vers le client, puis les supprime du serveur (sauf configuration contraire).
* **Ports utilisés** :

  * 110 : port standard non sécurisé.
  * 995 : port sécurisé (POP3S).
* **Caractéristiques** :

  * Accès hors ligne aux e-mails.
  * Pas de synchronisation entre plusieurs appareils.
  * Risque de perte d'e-mails en cas de défaillance du client.

---

## 🔄 IMAP : Internet Message Access Protocol

### Fonctionnement

* **Rôle** : synchronise les e-mails entre le serveur et le client, permettant un accès depuis plusieurs appareils.
* **Ports utilisés** :

  * 143 : port standard non sécurisé.
  * 993 : port sécurisé (IMAPS).
* **Caractéristiques** :

  * Les e-mails restent stockés sur le serveur.
  * Synchronisation en temps réel des actions (lecture, suppression, etc.).
  * Accès aux e-mails depuis n'importe quel appareil connecté.

---

## 🧩 MAPI : Messaging Application Programming Interface

### Fonctionnement

* **Rôle** : interface propriétaire de Microsoft pour une intégration complète avec Exchange.
* **Caractéristiques** :

  * Synchronisation des e-mails, contacts, calendriers et tâches.
  * Fonctionnalités collaboratives avancées.
  * Utilisé principalement avec Microsoft Outlook et Exchange.

---

## ⚖️ Comparaison des protocoles

| Protocole | Rôle principal      | Stockage des e-mails | Synchronisation | Accès multi-appareils | Sécurité intégrée |                                                                      |
| --------- | ------------------- | -------------------- | --------------- | --------------------- | ----------------- | -------------------------------------------------------------------- |
| SMTP      | Envoi des e-mails   | Serveur              | Non             | Oui                   | Oui               |                                                                      |
| POP3      | Réception en local  | Client               | Non             | Non                   | Oui               |                                                                      |
| IMAP      | Gestion en ligne    | Serveur              | Oui             | Oui                   | Oui               |                                                                      |
| MAPI      | Intégration avancée | Serveur              | Oui             | Oui                   | Oui               |
---

## 📚 Ressources supplémentaires

* [Découverte des protocoles SMTP, POP, IMAP et MAPI - IT-Connect](https://www.it-connect.fr/messagerie-decouverte-des-protocoles-smtp-pop-imap-et-mapi/)
* [Protocoles de messagerie : SMTP, POP, IMAP - Provectio](https://blog.provectio.fr/protocoles-de-messageries-smtp-pop-imap/)
* [Les protocoles SMTP, POP3 et IMAP en 4 minutes - YouTube](https://www.youtube.com/watch?v=WxXiGkJkP7A)

---