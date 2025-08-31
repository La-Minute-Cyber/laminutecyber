---
title: "🚨 PromptLock : le premier ransomware boosté à l’IA"
date: 2025-09-01
showHero: False
tags: ["Ransomware", "IA", "ESET", "Cybersécurité", "Malware"]
summary: "ESET a découvert PromptLock, un ransomware inédit qui utilise une IA locale pour générer son propre code malveillant. Un tournant : l’IA ne sert plus seulement de support, elle devient le moteur même de l’attaque."
authors:
    - "lucas"
---

> ESET a mis la main sur **PromptLock**, le premier ransomware documenté intégrant une **IA générative locale** pour créer du code malveillant.  
> Plus qu’un simple malware, il inaugure une nouvelle ère où l’IA est au cœur même des cyberattaques.

---

## 🤖 Une IA embarquée comme moteur

- Développé en **Golang**, PromptLock embarque le modèle **gpt-oss:20b** tournant via *Ollama*.  
- Contrairement aux malwares classiques, il ne dépend pas d’un service cloud → **pas de trace côté fournisseur d’IA**.  
- À partir de *prompts* codés en dur, l’IA génère en temps réel des **scripts Lua polymorphes** adaptés à l’environnement de la victime.  

👉 Chaque exécution produit un code unique, rendant les **indicateurs de compromission (IoC) quasi impossibles à fixer**.

---

## 🔎 Comment il s’adapte à sa cible

PromptLock ne suit pas un plan figé : il **observe son environnement** avant d’agir.

- 📂 Scan des fichiers pour détecter le type de données.  
- 🖥️ Distinction entre poste utilisateur, serveur critique ou système industriel.  
- 🛠️ Génération de scripts personnalisés :  
  - Exfiltration de bases de données.  
  - Chiffrement de documents bureautiques.  
  - Ciblage de systèmes industriels.  

---

## 💣 Capacités observées (et à venir)

D’après l’analyse d’ESET :  

- 🔐 **Chiffrement** via l’algorithme SPECK 128 bits.  
- 📤 **Exfiltration** des fichiers sensibles pour double extorsion.  
- 💥 **Suppression/destruction** de données (fonctionnalité en préparation).  
- 📝 **Notes de rançon personnalisées**, rédigées par IA, adaptées à la victime et au contexte.  

---

## 🧪 Encore un PoC… mais un signal fort

- Les artefacts PromptLock ont été **découverts sur VirusTotal le 25 août 2025 (USA)**.  
- Pas encore de propagation massive confirmée → considéré comme une **preuve de concept**.  
- Mais c’est un avertissement : **les cybercriminels savent désormais intégrer l’IA dans leurs ransomwares**.

---

## 🌍 Pourquoi c’est un tournant

Jusqu’ici, l’IA servait aux attaquants pour :  
- améliorer le phishing,  
- générer du code ponctuel,  
- automatiser l’ingénierie sociale.  

Avec PromptLock :  
- L’IA **devient le moteur** du malware, capable de générer des charges adaptatives et polymorphes.  
- Les conséquences côté défense :  
  - ❌ Signatures statiques : obsolètes.  
  - ⚠️ IoC classiques : de moins en moins fiables.  
  - ✅ Besoin de **détection comportementale avancée** (EDR, sandbox, corrélations réseau/hôte).  
- Une course **IA vs IA** s’annonce entre attaquants et défenseurs.  

---

## 🚨 Conclusion

PromptLock marque un **tournant majeur** :  

👉 Un ransomware qui **se génère lui-même via une IA locale**, qui **s’adapte à son environnement** et qui peut **chiffrer, voler ou détruire des données**.  

L’IA n’est plus un outil secondaire pour les cybercriminels.  
Elle devient un **composant central des malwares de demain**.
