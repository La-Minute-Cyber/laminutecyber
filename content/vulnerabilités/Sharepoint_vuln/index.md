---
title: "🛡️ SharePoint piraté ? Une faille critique déjà exploitée (CVE‑2025‑53770)"
date: 2025-07-26
showHero: false
tags: ["SharePoint", "Microsoft", "CVE-2025-53770", "ZeroAuth", "Cyberattaque"]
summary: "Une vulnérabilité critique (CVSS 9.8) dans SharePoint Server permet l'exécution de code à distance sans authentification. Déjà exploitée dans la nature, cette faille menace les infrastructures internes non mises à jour."
authors:
  - "lucas"
---

> **CVE‑2025‑53770** | **CVSS 9.8 – Gravité critique**  
> 🛠️ *Faille d’exécution de code à distance dans Microsoft SharePoint Server*  
> ⚠️ **Exploit actif depuis mi-juillet 2025 sur des serveurs vulnérables**

---

## 💣 Qu’est-ce que la faille SharePoint de juillet 2025 ?

Microsoft a révélé une **faille critique** dans plusieurs versions de **SharePoint Server on-premises**.  
Nom de code : **CVE‑2025‑53770**. Score CVSS : **9.8 / 10**. Exploitation active confirmée.

☠️ Cette vulnérabilité permet l'exécution de code **sans authentification préalable** via une désérialisation non sécurisée.

Une seconde faille, **CVE‑2025‑53771**, permet la traversée de répertoires et l'usurpation réseau (CVSS 7.1).

---

## 🧠 Comment ça fonctionne ?

🧩 Un fichier piégé envoyé à SharePoint est interprété comme une commande système.

➡️ L’attaquant peut alors **exécuter du code arbitraire** avec les droits du serveur, **sans login**.

---

## 🔥 Pourquoi c’est urgent ?

- 💥 Exploitation en cours par des groupes malveillants
- ⏳ Patchs publiés tardivement (22 juillet)
- ⚠️ Certaines versions ne sont plus supportées (aucune protection possible)
- 🕵️ Traces d'intrusion observables dans les logs

---

## 📋 Versions concernées

| Version SharePoint              | Patch disponible ? | État de vulnérabilité |
|-------------------------------|---------------------|------------------------|
| SharePoint Server 2010        | ❌                  | Non patchable          |
| SharePoint Server 2013        | ❌                  | Non patchable          |
| SharePoint Server 2016        | ✅ (16.0.5513)       | Patch requis           |
| SharePoint Server 2019        | ✅ (16.0.10417)      | Patch requis           |
| SharePoint Subscription       | ✅ (16.0.18526)      | Patch requis           |
| SharePoint Online (M365)      | ✅                  | **Non concerné**       |

📌 Les versions 2010 et 2013 doivent être **migrées immédiatement** : aucun correctif ne sera publié.

---

## 🕵️ Comment détecter une compromission ?

Vérifie les **logs IIS** de SharePoint (entre le 7 et le 23 juillet) :

POST /_layouts/15/ToolPane.aspx?DisplayMode=Edit&a=/ToolPane.aspx


🔍 Surveille également :

Processus : w3wp.exe → powershell.exe ou cmd.exe


👀 Ces éléments signalent une possible exécution malveillante à distance.

---

## 🛡️ Que faire immédiatement ?

✅ Si ta version est supportée :

- Appliquer les **patchs de sécurité de juillet 2025**
- Modifier les **clés machineKey ASP.NET** (`web.config`)
- Redémarrer **IIS**

🔒 Pour renforcer la défense :

- Activer **AMSI en full mode**
- Intégrer avec **Microsoft Defender Antivirus**
- Utiliser **Defender for Endpoint** pour l’analyse comportementale

🛑 Si ta version est obsolète :

- Isoler les serveurs de l’accès Internet
- Restreindre l’accès via **VPN** ou **proxy**
- Envisager une **migration immédiate**

---

## 🧠 Cyber-leçon

> Une faille sur un outil “bureautique” peut devenir une **porte d’entrée réseau**.

SharePoint est souvent lié à :
- 📁 des documents confidentiels
- 👥 des identités AD
- 🔐 l’infrastructure interne

➡️ Cette faille peut servir de **pivot pour des attaques plus larges** : ransomware, vol de données, rebond latéral…

---

## 📌 Recommandations

✅ Appliquer les patchs MS de juillet 2025  
✅ Revoir les logs IIS de mi-juillet  
✅ Surveiller les comportements anormaux (Defender/EDR)  
✅ Migrer les versions non supportées (2010/2013)  
✅ Segmenter les accès réseau à SharePoint

---

## 🔗 Sources

- 🔍 [CERT-FR : Alerte CERTFR-2025-ALE-010](https://www.cert.ssi.gouv.fr/alerte/CERTFR-2025-ALE-010/)
- 🛡️ [Cybermalveillance.gouv.fr – Analyse complète](https://www.cybermalveillance.gouv.fr/tous-nos-contenus/actualites/alertecyber-failles-de-securite-critiques-dans-microsoft-sharepoint-202507)
- 📝 [Microsoft MSRC – CVE‑2025‑53770](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53770)


