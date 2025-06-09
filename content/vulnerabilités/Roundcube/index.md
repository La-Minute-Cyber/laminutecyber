---
title: "⚠️ [CERT-FR] : Faille critique dans Roundcube Webmail"
date: 2025-06-05
showHero: false
tags: ["CERT-FR", "Roundcube", "CVE", "Webmail"]
summary: "Une vulnérabilité critique affecte Roundcube Webmail, permettant à un utilisateur authentifié d’exécuter du code arbitraire à distance. Une preuve de concept est publique et touche aussi des instances cPanel et Plesk. Patch disponible, mise à jour immédiate recommandée."
authors:
  - "lucas"
---

> **CERTFR-2025-ALE-008** | **CVE-2025-49113 – Critique (RCE)**  
> 🛡️ *Exécution de code via injection de template HTML*  
> ⚠️ Preuve de concept publique – Mise à jour urgente recommandée

---

## 🛑 Vulnérabilité critique dans Roundcube Webmail

Le [CERT-FR](https://cert.ssi.gouv.fr/alerte/CERTFR-2025-ALE-008/) alerte sur une faille majeure dans **Roundcube Webmail**, identifiée comme [CVE-2025-49113](https://www.cve.org/CVERecord?id=CVE-2025-49113).  
Cette vulnérabilité permet à un **utilisateur authentifié** d’exécuter **du code PHP arbitraire à distance**, en exploitant une faiblesse dans le moteur de rendu HTML des e-mails.

---

## 🧪 Détail de l’exploitation

Cette faille s’apparente à une **injection de template** côté serveur. En insérant une charge utile dans un e-mail HTML, l’attaquant peut :

- Injecter des objets PHP manipulables
- Détourner le traitement du contenu HTML
- Déclencher l’exécution de code arbitraire

⚠️ L'exploitation est possible **sans privilèges élevés**, tant que l’accès à une session authentifiée est obtenu.  
Elle est **particulièrement dangereuse sur des serveurs mutualisés** ou via des environnements comme **cPanel** ou **Plesk**, où Roundcube est souvent préinstallé.

---

## 🎯 Versions concernées

- Roundcube < 1.6.11  
- Roundcube < 1.5.10

---

## 📤 Correctifs disponibles

Roundcube a publié le **1er juin 2025** deux mises à jour corrigeant la vulnérabilité :

- 🔧 [1.6.11](https://roundcube.net/news/2025/06/01/security-updates-1.6.11-and-1.5.10) pour la branche 1.6.x
- 🔧 [1.5.10](https://roundcube.net/news/2025/06/01/security-updates-1.6.11-and-1.5.10) pour la branche 1.5.x

Les correctifs désactivent l’interprétation de certaines balises HTML dangereuses dans les modèles de rendu.

---

## 🔒 Recommandations

- ✅ **Mettre à jour immédiatement Roundcube**
- 🕵️‍♂️ **Auditer les journaux d’accès** (webmail, IMAP, SMTP)
- 🚫 **Désactiver temporairement l’affichage HTML** si mise à jour impossible
- 🧱 **Renforcer les contrôles d'accès et la supervision des comptes**

---

## 🧠 Pourquoi c’est grave

L’impact d’une telle vulnérabilité ne se limite pas à un seul utilisateur.  
Un accès à une boîte e-mail peut permettre à un attaquant de :

- Pivoter vers d'autres services du serveur
- Injecter du code dans les environnements partagés ;
- Voler des identifiants ou secrets liés à l’hébergement.

---

## 📚 Sources

- 🔗 [CERTFR-2025-ALE-008 (cert.ssi.gouv.fr)](https://cert.ssi.gouv.fr/alerte/CERTFR-2025-ALE-008/)
- 🔗 [Bulletin Roundcube officiel](https://roundcube.net/news/2025/06/01/security-updates-1.6.11-and-1.5.10)
- 🔗 [CVE-2025-49113 (cve.org)](https://www.cve.org/CVERecord?id=CVE-2025-49113)

---

## 🧩 En résumé

⚠️ La faille CVE-2025-49113 affecte potentiellement **des milliers d’instances webmail** exposées sur Internet.  
La publication rapide d’une **preuve de concept** la rend particulièrement dangereuse.  

🔐 **Admins, mettez à jour vos serveurs Roundcube dès maintenant.**
