---
title: "🏆 Le Record du Monde de DDoS : 3,8 Tbit/s stoppés net"
date: 2025-07-17
showHero: false
tags: ["DDoS", "NTP", "Cloudflare", "Amplification", "Botnet", "Cybersécurité"]
summary: "Une attaque DDoS record de 3,8 Tbit/s a été stoppée par Cloudflare en 2024. Elle exploitait le protocole NTP pour amplifier massivement le trafic vers sa cible. Plongée dans une attaque à très haut débit."
authors:
  - "lucas"
---

> 💥 **3,8 Tbit/s** | Le plus gros DDoS jamais enregistré (2024)  
> 🕰️ *Technique utilisée : amplification NTP (Network Time Protocol)*  
> 🛡️ Défense : mitigation temps réel par Cloudflare sur leur réseau mondial

---

## 📈 L’attaque DDoS la plus puissante jamais vue

En 2024, **Cloudflare** a intercepté une attaque DDoS atteignant un pic de **3,8 térabits par seconde** (Tbps).  
🎯 La cible ? Un client dans le secteur du gaming ou de la finance (nom gardé confidentiel).  
Bonne nouvelle : l’attaque a été **contenue sans impact** visible pour l’utilisateur final.

---

## 🧠 Petit rappel : c’est quoi une attaque DDoS ?

Une attaque par **Déni de Service Distribué (DDoS)** vise à **saturer** les serveurs ou l’infrastructure d’une cible avec un volume énorme de trafic :

- 🌐 Soit par **volume** (Layer 3/4)
- 🧠 Soit par **ciblage applicatif** (Layer 7)
- 🔗 Ou en exploitant des **protocole mal configurés** (UDP Amplification)

---

## 🕰️ Pourquoi utiliser le protocole NTP ?

**NTP (Network Time Protocol)** permet de synchroniser les horloges entre machines.  
Mais mal configuré, il devient une **arme d’amplification massive**.

### 🔍 Fonctionnement de l’amplification NTP

- L’attaquant envoie une **petite requête UDP falsifiée** à un serveur NTP, en usurpant l’IP de la victime.
- Le serveur répond avec **beaucoup plus de données** directement vers cette victime.
- Résultat : un effet multiplicateur → **jusqu’à x500 d’amplification**.

> 📬 1 Ko envoyé → 200 à 500 Ko renvoyés vers la cible.  
> Imagine ça via **des milliers de serveurs publics**… et un botnet.

---

## ⚙️ Étapes de l’attaque par NTP Amplification

```text
1. Botnet (souvent IoT) envoie des requêtes "monlist" à des serveurs NTP ouverts
2. Adresse IP de la victime utilisée comme IP source
3. Les serveurs envoient une réponse énorme à la victime
4. La cible est submergée par un trafic massif, sans jamais avoir rien demandé
````

---

## 💣 Pourquoi c’est si dangereux ?

* Aucune interaction de la cible n’est nécessaire
* Difficile à tracer : le trafic semble venir de services légitimes
* Les firewalls classiques ne bloquent pas toujours UDP 123 (port NTP)
* L’effet d’amplification est énorme → idéal pour un **DDoS à moindre coût**

---

## 🛠️ Autres protocoles amplificateurs

| Protocole | Amplification | Port | Remarques                         |
| --------- | ------------- | ---- | --------------------------------- |
| **NTP**   | x200–x500     | 123  | Commande "monlist" exploitée      |
| **DNS**   | x30–x70       | 53   | Requêtes sur de gros domaines     |
| **SSDP**  | x30           | 1900 | UPnP mal configuré                |
| **CLDAP** | x55           | 389  | Utilisé dans les Active Directory |

---

## 🛡️ Comment Cloudflare a-t-il stoppé l’attaque ?

* 🌐 Réseau **Anycast mondial** pour répartir le trafic
* 🤖 **Détection comportementale automatisée**
* 🧱 **Blocage en périphérie** sur les datacenters (filtrage UDP/NTP)
* 🔎 Analyse des **entêtes IP** pour détecter du spoofing

> “Le pic de 3,8 Tbit/s n’a même pas atteint l’infrastructure du client.” — Cloudflare

---

## 📉 Protéger son infra contre ce type d’attaque

### Pour les sysadmins :

* 🔒 Bloquer la commande "monlist" dans `ntpd`
* 🚫 Interdire NTP public depuis l’extérieur
* 🔍 Auditer ses serveurs avec `ntpq`, `ntpdc`

### Pour les entreprises :

* 🛡️ Mettre en place une protection DDoS dédiée (Cloudflare, Akamai…)
* 📊 Activer des règles de détection de volume anormal
* 🔧 Filtrer les ports UDP en entrée (notamment 123, 53, 1900, 389)

---

## 🔭 Et demain ? Vers des attaques à 10 Tbit/s ?

➡️ Le record précédent était à **2,5 Tbit/s** (Google Cloud en 2022).
➡️ En 2025, les experts anticipent des attaques dépassant les **10 Tbit/s**, avec l’explosion de l’IoT et des services exposés.

> “Les DDoS ne sont plus une question de puissance, mais de **réaction en temps réel.**”

---

## 📚 Pour aller plus loin

* 📘 [Cloudflare – NTP Amplification Explained](https://www.cloudflare.com/fr-fr/learning/ddos/ntp-amplification-ddos-attack/)
* 📗 [IT-Connect – Le protocole NTP](https://www.it-connect.fr/quest-ce-que-le-protocole-ntp/)
* 📊 [Google Cloud – DDoS de 2,5 Tbit/s en 2022](https://cloud.google.com/blog/products/identity-security/google-cloud-mitigated-largest-ddos-attack)

---

## 🧠 TL;DR

> ⚠️ L’amplification NTP reste un outil puissant pour les attaques DDoS.
> 🎯 Cloudflare a stoppé un **record mondial de 3,8 Tbit/s** en 2024.
> 🔐 Des protections simples peuvent **éviter que vos serveurs deviennent complices**.

