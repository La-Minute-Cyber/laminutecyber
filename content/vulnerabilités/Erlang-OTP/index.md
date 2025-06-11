---
title: "🚨 CVE-2025-32433 — Vulnérabilité critique RCE sur Erlang/OTP (CVSS 10)"
date: 2025-06-10
showHero: false
tags: ["CVE", "Erlang", "KEV"]
summary: "Une vulnérabilité critique dans le serveur SSH d’Erlang/OTP permet une exécution de code à distance sans authentification. Déjà exploitée, elle menace de nombreuses infrastructures distribuées."
authors:
  - "lucas"
---

> **CVE-2025-32433** | **CVSS 10.0 – Gravité maximale** | **EUVD-2025-11793**  
> 🛡️ *Exécution de code à distance via SSH intégré d’Erlang/OTP*  
> ⚠️ *Déjà exploitée — ajoutée au CISA KEV le 9 juin 2025*

---

## 🔍 Contexte

Le 9 juin 2025, la vulnérabilité **CVE-2025-32433** a été inscrite dans le catalogue [CISA Known Exploited Vulnerabilities (KEV)](https://www.cisa.gov/known-exploited-vulnerabilities-catalog), signalant une **exploitation active**.

Elle affecte le **serveur SSH intégré d’Erlang/OTP**, largement utilisé dans des systèmes distribués critiques : plateformes de messagerie, systèmes IoT, télécoms, bases de données temps réel, etc.

🎯 **Impact** : Exécution de code arbitraire à distance sans authentification (RCE), avec **prise de contrôle totale** possible.

---

## 🖥️ Produits vulnérables

| Produit       | Versions vulnérables                |
|---------------|-------------------------------------|
| Erlang/OTP 27 | OTP-27.0-rc1 à < OTP-27.3.3         |
| Erlang/OTP 26 | OTP-26.0-rc1 à < OTP-26.2.5.11      |
| Erlang/OTP 25 | < OTP-25.3.2.20                     |

✅ **Versions corrigées** :

- OTP-27.3.3
- OTP-26.2.5.11
- OTP-25.3.2.20  
🔗 [Patchs GitHub officiels](https://github.com/erlang/otp)

---

## 🎯 Nature de la vulnérabilité

- 💥 **Cause** : mauvaise gestion des messages SSH par le serveur intégré.
- 🚫 **Pas d’authentification requise** pour exploiter la faille.
- 🧨 **Conséquence** : exécution de code à distance (RCE), **compromission complète du système**.

🔒 Aucune mitigation fiable autre que :

- Appliquer les patchs
- Désactiver le serveur SSH intégré
- Restreindre l’accès réseau au serveur SSH via firewall

---

## 🚨 Exploitation active

- ➕ Présente dans le catalogue CISA KEV
- 📈 Score EPSS (Exploit Prediction Scoring System) : **51,57 %**
- 🕵️ Des POC circulent déjà sur **des forums privés** et **le darkweb**

---

## 🌍 Menace globale

Cette vulnérabilité est particulièrement dangereuse car :

- **Non authentifiée** et **accessible via le réseau** 
- Présente dans **de nombreux systèmes critiques** (messageries, télécoms, edge computing, etc.) 
- Potentiellement **oubliée ou mal configurée** dans des systèmes de production

⚠️ **Risques majeurs** :

- Prise de contrôle du serveur
- Mouvement latéral dans le SI
- Déploiement de ransomwares ou botnets

---

## 🛡️ Recommandations immédiates

- ✅ **Patch** vers les versions fixes : OTP-27.3.3 / OTP-26.2.5.11 / OTP-25.3.2.20
- ⛔ **Désactiver temporairement** le serveur SSH intégré si patch non possible
- 🔥 **Limiter strictement** les flux SSH par segmentation réseau / firewall
- 🔍 **Auditer vos environnements** à la recherche d’instances OTP exposées
- 🧠 **Surveillance IDS/IPS** accrue sur les connexions SSH suspectes

---

## 🔗 Sources officielles

- [Advisory officiel GitHub](https://github.com/erlang/otp/releases)
- [Commits de correctif GitHub](https://github.com/erlang/otp/commits/master)
- [CISA KEV](https://www.cisa.gov/known-exploited-vulnerabilities-catalog)
- [CVE-2025-32433 sur NVD](https://nvd.nist.gov/vuln/detail/CVE-2025-32433)
- [Exploit Prediction Scoring System (EPSS)](https://www.first.org/epss/)

---

🚨 **Vous utilisez Erlang/OTP ?** Patchez immédiatement ou isolez vos serveurs SSH. L’exploitation est active, la menace réelle.

