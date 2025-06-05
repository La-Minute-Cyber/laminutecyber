---
title: "🚨 Intrusion dans Salesforce : le piège du faux support IT"
date: 2025-06-04
showTableOfContents: true
showHero: False
tags: ["vishing", "social engineering", "salesforce"]
summary: "Une campagne de vishing ciblée a permis à UNC6040 de compromettre des comptes Salesforce, sans faille technique, via ingénierie sociale."
authors:
    - "lucas"
---

> **Campagne de vishing avancée** | **UNC6040** | **Aucune faille technique exploitée**  
> 📞 *Attaques par ingénierie sociale via faux support IT*  
> 🛡️ Salesforce & Google recommandent un renforcement des contrôles humains et techniques

---

## 🎯 Objectif : Vol de Données & Extorsion

Le 4 juin 2025, **Google Threat Intelligence Group (GTIG)** a révélé une campagne sophistiquée ayant compromis les environnements **Salesforce** d’au moins 20 entreprises (US + Europe).  
Le groupe **UNC6040** est à l’origine de cette attaque **sans faille technique**, exploitant uniquement des techniques de **vishing** (phishing vocal).

🎯 L’objectif ?  
- Obtenir des **identifiants sensibles**  
- Installer des **apps malveillantes** dans Salesforce  
- Lancer des **campagnes d’extorsion** différées

---

## 🔍 Méthodologie d’Attaque

1. **Vishing ciblé**  
   ➤ Un employé est contacté par un faux technicien ou support IT  
2. **Fausse application Salesforce**  
   ➤ L’utilisateur est incité à autoriser une app modifiée du **Data Loader** via les *Connected Apps*  
3. **Accès aux données Salesforce**  
   ➤ L’app malveillante permet des requêtes API massives  
4. **Mouvements latéraux**  
   ➤ Réutilisation des identifiants pour accéder à **Okta**, **Microsoft 365**, etc.  
5. **Infrastructure furtive**  
   ➤ Utilisation de **VPN commerciaux (Mullvad)** & de **panneaux de phishing Okta**

---

## 🧠 Leçon Clé : L’Humain, Talon d’Achille

> "Les attaques telles que l'hameçonnage vocal sont des escroqueries ciblées conçues pour exploiter les lacunes des utilisateurs en matière de sensibilisation à la cybersécurité."  
> — *Porte-parole Salesforce*

📌 **Aucune vulnérabilité technique** n’a été exploitée  
📈 **Augmentation forte des attaques** basées sur la manipulation psychologique

---

## 🧱 Recommandations Stratégiques

### ✅ 1. Appliquer le principe du moindre privilège
- Limiter l’accès aux outils puissants comme **Data Loader**  
- Restreindre les permissions critiques : `API Enabled`, `Manage Connected Apps`

### ✅ 2. Gérer rigoureusement les apps connectées
- Valider en interne les applications autorisées  
- Bloquer toute app non reconnue

### ✅ 3. Restreindre l’accès par IP
- Appliquer des **restrictions IP** aux utilisateurs et apps  
- Refuser les connexions hors VPN officiel

### ✅ 4. Surveiller les comportements anormaux
- Déclencher des alertes via **Salesforce Shield** :
  - Téléchargements massifs
  - Connexions suspectes
  - Activités API inhabituelles  
- Intégrer les logs à votre **SIEM**

### ✅ 5. Renforcer la MFA & la sensibilisation
- Imposer la **MFA partout**  
- Former les utilisateurs aux tentatives de **fatigue MFA** et **contournement social**

---

## 🧩 Liens avec des Groupes Connus

GTIG note des similarités avec les méthodes du groupe **The Comm**, affilié à **Scattered Spider** ([G1015](https://attack.mitre.org/groups/G1015/)).  
📦 Hypothèse : **revente ou exploitation différée** des données volées par d'autres groupes.

---

## 📉 Risques à Court et Moyen Terme

- 🔓 **Fuite de données sensibles** (clients, employés, contrats)  
- 💰 **Extorsion** et rançons  
- 🤝 **Perte de confiance** des partenaires  
- ⚖️ **Amendes réglementaires** (RGPD, CCPA…)  
- 📄 **Litiges juridiques** (en cas de non-notification)

---

## 🛡️ Conclusion : Une alerte pour tous

Cet incident souligne un point crucial :

> **Les environnements cloud ne sont sécurisés que si les utilisateurs le sont aussi.**

L’usage d’outils puissants, l’intégration d’API et l’automatisation ne doivent jamais affaiblir la **posture de sécurité humaine**.

---

## 📚 Sources & Lecture Complémentaire

- 🔗 [Google Threat Intelligence – Vishing & Data Extortion](https://cloud.google.com/blog/topics/threat-intelligence/voice-phishing-data-extortion?hl=en)  
- 🔗 [Bloomberg – Hackers Breach Salesforce Accounts](https://www.bloomberg.com/news/articles/2025-06-04/google-warns-hackers-stealing-salesforce-data-from-companies)  
- 🔗 [Salesforce Security Guide](https://help.salesforce.com/s/articleView?id=xcloud.security_overview.htm&type=5)  
- 🔗 [Salesforce Shield – Official Documentation](https://www.salesforce.com/platform/shield/)

---
