---
title: "Une porte dérobée critique dans XZ Utils menace la sécurité des systèmes Linux"
date: 2025-05-19
draft: false
description: "En mars 2024, une porte dérobée sophistiquée a été découverte dans XZ Utils, un outil de compression largement utilisé sur les systèmes Linux. Cette faille, introduite par un mainteneur malveillant, permettait une exécution de code à distance via SSH, compromettant potentiellement des millions de machines."
tags: ["XZUtils", "CVE-2024-3094"]
summary: "Une backdoor dans XZ Utils (CVE-2024-3094) permettait une exécution de code à distance via SSH sur Linux."
authors:
    - "gabin"
---

## 🧩 Contexte

Le 29 mars 2024, Andres Freund, ingénieur chez Microsoft, a découvert une anomalie de performance en testant PostgreSQL. En analysant plus en profondeur, il a mis en lumière une porte dérobée dans XZ Utils — un outil de compression fondamental utilisé par de nombreuses distributions Linux.

## 🐛 Détails techniques

- **Identifiant** : CVE-2024-3094  
- **Versions concernées** : 5.6.0 et 5.6.1 de XZ Utils  
- **Impact** : Possibilité de prise de contrôle à distance via SSH sur les systèmes affectés  
- **Mécanisme** : Du code malveillant a été injecté dans les scripts de compilation (`configure`) et dans `liblzma`, permettant la manipulation de processus SSH pour exécuter du code arbitraire.

## 🕵️‍♂️ Origine de l’attaque

La backdoor a été introduite par un contributeur actif, connu sous le pseudonyme "JiaT75", qui était devenu mainteneur officiel après plusieurs mois de contributions crédibles. Ce scénario démontre une attaque de type “subversion de la chaîne d'approvisionnement open source”.

## 🛡️ Réactions et mesures de mitigation

- Les versions malveillantes ont été supprimées des dépôts Linux.
- Fedora et Debian ont désactivé les mises à jour vers les versions compromises.
- L’incident a entraîné une prise de conscience accrue autour de la gouvernance des projets open source.

## ⚠️ Implications

Cette attaque est l’une des plus graves jamais enregistrées dans l’écosystème open source. Elle démontre que même des composants apparemment anodins peuvent devenir des vecteurs de compromission à grande échelle.

## 🔗 Sources recommandées

- [NVD CVE-2024-3094](https://nvd.nist.gov/vuln/detail/CVE-2024-3094)
- [Wikipedia - Attaque de XZ Utils](https://fr.wikipedia.org/wiki/Attaque_de_XZ_Utils_par_porte_d%C3%A9rob%C3%A9e)
- [Analyse sur BleepingComputer](https://www.bleepingcomputer.com/news/security/backdoor-found-in-xz-utils-affecting-ssh-on-multiple-linux-distros/)

---

> 🧠 **Conseil** : Vérifiez vos systèmes et assurez-vous de ne pas utiliser les versions affectées. Appliquez immédiatement les correctifs de vos distributions.
