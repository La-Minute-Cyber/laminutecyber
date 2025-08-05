---
title: "🎯 CrowdStrike Threat Hunting Report 2025 : l’adversaire moderne, entre GenAI, attaques sans malware et espionnage ultra-ciblé"
date: 2025-08-05
showHero: true
hero: "images/hero-threat-report.png"
tags: ["CrowdStrike", "Threat Intelligence", "Cybersécurité", "GenAI", "Ransomware", "Cloud"]
summary: "CrowdStrike dévoile son rapport 2025 : industrialisation des attaques, IA générative, fileless, cloud et espionnage étatique. Une lecture essentielle pour comprendre les menaces de demain."
authors:
  - "lucas"
---

CrowdStrike vient de publier son très attendu Threat Hunting Report 2025, synthèse des observations de son équipe Counter Adversary Operations sur l’année 2024. Le rapport révèle un paysage des menaces radicalement transformé, dominé par des adversaires agissant comme des entreprises, exploitant l’IA générative, et maîtrisant à la perfection les attaques sans malware.

Voici les tendances majeures et données techniques clés à retenir de ce rapport incontournable.

---

## ⚙️ Des adversaires industrialisés : vitesse, précision, automatisation

Les acteurs malveillants opèrent désormais avec un niveau d’industrialisation jamais vu :

- ⏱️ Temps moyen de propagation : **48 minutes**, avec une intrusion record en **51 secondes** seulement.
- 🔐 **79 %** des intrusions initiales sont sans malware, reposant sur des **identifiants valides** et des **outils système légitimes**.
- 🧑‍💻 Multiplication des **Access Brokers** (+50 % d’annonces en un an), qui vendent des accès initiaux à des groupes spécialisés (ransomware, espionnage, etc.).

{{< figure src="./scattered_spider.png" alt="Exemple d'une attaque de Scattered Spider" caption="🎯 Exemple : attaque rapide et furtive par le groupe Scattered Spider" >}}

---

## 🧠 L’IA générative (GenAI) au service de la cybercriminalité

L’année 2024 a marqué une bascule majeure : l'IA générative n'est plus un buzzword, c’est une **arme offensive**.

- 📞 **+442 %** d’attaques par **vishing** entre le premier et le second semestre 2024.
- 🧑‍💼 Utilisation de **deepfakes vocaux** pour imiter des cadres ou des techniciens support.
- 📧 Génération automatique d’e-mails **BEC**, de **scripts de phishing** ou de **landing pages convaincantes**, augmentant significativement le taux de clic.

{{< figure src="./vishing.png" alt="Vishing" caption="🔥 Augmentation significative du Vishing en 2025">}}

---

## 🔒 Attaques sans malware : l’ère du « living-off-the-land »

L'approche **fileless** domine :

- 🔧 Utilisation d’outils comme PowerShell, WMI, RMM, PSExec, ou encore WinRM.
- 🎮 Implantations manuelles, sessions interactives par les attaquants via **mains sur clavier**, pour des mouvements latéraux discrets.
- 🧊 Moins de déclencheurs pour les solutions EDR : les actions malveillantes sont **camouflées dans le bruit légitime**.

---

## ☁️ Le Cloud sous pression constante

Les environnements **Cloud et SaaS** sont devenus des cibles stratégiques :

- ☁️ **+26 %** d’intrusions cloud non attribuées.
- 🔑 **35 %** des incidents impliquent un accès via **compte valide** (ex : token SSO, OAuth compromis).
- ⚙️ Exploitation de failles de configuration IAM, de **CLI cloud (Azure, AWS)**, et de **chaînes de dépendances SaaS** pour mouvements latéraux et exfiltration.

---

## 🔍 Exploit chaining et attaque périphérique

L’accès initial s’appuie souvent sur un enchaînement de vulnérabilités (**exploit chaining**) visant des systèmes exposés :

- 🧱 **52 %** des vulnérabilités exploitées sont liées à l’accès initial.
- 🔄 Combinaisons de **CVE non patchées** et d’**erreurs de configuration** sur des appliances réseau ou interfaces web exposées.

{{< figure src="./heatmap_MITRE.png" alt="Heat Map MITRE ATT&CK" caption="🔥 Visualisation des techniques utilisées via MITRE ATT&CK" >}}

---

## 🕵️ Espionnage étatique : la Chine en tête, la Corée du Nord intensifie les attaques internes

### 🇨🇳 Chine (China-nexus)

- 📈 **+150 % d’activité offensive**.
- 🏭 Cibles : **finance**, **médias**, **manufacturing**, avec des pics jusqu’à **+300 %** selon les secteurs.
- 🐼 **7 nouveaux groupes** identifiés en 2024, dont **VAULT PANDA** et **LIMINAL PANDA**.

### 🇰🇵 Corée du Nord

- 🕵️‍♂️ **FAMOUS CHOLLIMA** responsable de **304 incidents** en 2024.
- 👥 **40 %** impliquent des **menaces internes** ou des comptes compromis mimant des employés légitimes.

---

## 📊 En chiffres : synthèse rapide

| Tendance                        | Donnée technique                          |
|--------------------------------|--------------------------------------------|
| Attaques sans malware          | 79 % des intrusions initiales             |
| Temps moyen de breakout        | 48 minutes (record : 51 sec)              |
| GenAI & vishing                | +442 % entre H1 et H2 2024                |
| Intrusions cloud               | +26 % ; 35 % avec comptes valides         |
| Activité China-nexus           | +150 % (jusqu’à +300 % sur certaines industries) |
| Access Brokers                 | +50 % d’activité                          |
| Exploit chaining               | 52 % des failles = accès initial          |
| Activité de FAMOUS CHOLLIMA    | 304 incidents ; 40 % impliquant des insiders |

---

## 🧩 Conclusion

Le rapport 2025 de CrowdStrike confirme ce que beaucoup pressentaient : les cybermenaces sont **plus rapides, silencieuses, coordonnées et intelligentes que jamais**.  
Dans ce nouvel écosystème, la **maîtrise des accès**, l’**analyse comportementale** et la **visibilité cloud** deviennent absolument vitales.

Ce document est une lecture **indispensable** pour comprendre les TTP (Tactiques, Techniques, Procédures) des acteurs majeurs, mais surtout **anticiper leurs évolutions**.

📖 Rapport complet (EN) : [CrowdStrike 2025 Global Threat Report](https://www.crowdstrike.com/fr-fr/global-threat-report/)
