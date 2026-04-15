# 🛡️ Gestion des incidents & stratégie locale

![Status](https://img.shields.io/badge/status-complete-success)
![Type](https://img.shields.io/badge/type-school%20project-blue)
![Security](https://img.shields.io/badge/focus-cybersecurity-red)

---

## 📚 Sommaire

* [📌 Mission 1 — Analyse CERT-FR](#-mission-1--analyse-cert-fr)
* [⚙️ Mission 2 — Configuration Windows](#️-mission-2--configuration-windows)
* [🔒 Sécurisation du système](#-sécurisation-du-système)
* [🧠 Étude du BOOT](#-étude-du-boot)

---

# 📌 Mission 1 — Analyse CERT-FR

🔗 Source : https://www.cert.ssi.gouv.fr/

---

## ❓ Cibles des alertes récentes

| Alerte              | Cible                   | Description                                         |
| ------------------- | ----------------------- | --------------------------------------------------- |
| CERTFR-2026-ALE-004 | BIG-IP APM (F5)         | Exécution de code à distance (exploitée activement) |
| CERTFR-2026-ALE-003 | Messagerie instantanée  | Campagnes ciblant secteurs sensibles                |
| CERTFR-2026-ALE-001 | Ivanti EPMM             | Scripts de détection fournis                        |
| CERTFR-2025-ALE-014 | React Server Components | Vulnérabilité critique                              |
| CERTFR-2026-ALE-002 | Cisco SD-WAN            | Infrastructure réseau vulnérable                    |

---

## ❓ Logiciels et systèmes obsolètes

* SharePoint Enterprise Server 2016
* SharePoint Server 2019
* SonicWall (versions anciennes)
* Cisco ASA / FTD non patchés
* Windows Server Update Service (WSUS)

---

## ❓ Détection d’une intrusion

### 🔍 Analyse des indicateurs

* Journaux systèmes (SIEM, antivirus, EDR)
* Dysfonctionnements :

  * services arrêtés
  * fichiers supprimés ou corrompus
* Perturbations métiers

> ⚠️ **Important :** un comportement anormal (ralentissement, erreur, disparition de fichiers) peut indiquer une intrusion.

---

## ❓ Réaction en cas d’intrusion

### 🚨 Mesures immédiates

* Isolation des machines
* Coupure réseau
* Blocage des accès distants
* Sauvegarde des données

### 🧠 Gestion de l’incident

* Conservation des preuves (logs)
* Analyse du périmètre
* Mobilisation des équipes

---

## ⚖️ Aspects légaux

* 📢 Déclaration à l’ANSSI
* 📝 Dépôt de plainte
* 🔐 Déclaration CNIL (données personnelles)

---

## 🔄 Reprise après intrusion

* Gestion de crise
* Communication interne/externe
* Contact avec l’assureur

---

## 🛠️ Outils de sécurité

* SIEM
* Antivirus
* EDR / XDR
* Prestataires spécialisés (PRIS)

---

# ⚙️ Mission 2 — Configuration Windows

---

## 👤 Création d’un utilisateur

![Création utilisateur](./images/image_1_1.png)
![Création utilisateur](./images/image_1_2.png)

**Procédure :**

```bash
Clic droit menu Démarrer
→ Gestion de l’ordinateur
→ Utilisateurs et groupes locaux
→ Nouveau utilisateur
```

---

## 🖥️ Microsoft Management Console (MMC)

```bash
Windows + R
mmc.exe
```

![MMC](./images/image_2_1.png)

---

## 🔧 Ajout de composants

```bash
Fichier → Ajouter/Supprimer un composant logiciel enfichable
```

![Ajout composant](./images/image_3_1.png)

---

## 🧩 Stratégie de groupe

* Ajouter :

  * Éditeur d’objets de stratégie de groupe

![GPO](./images/image_4_1.png)

---

## 🔍 Sélection de l’utilisateur

* Parcourir
* Onglet **Utilisateurs**
* Sélection du compte

![Sélection utilisateur](./images/image_5_1.png)

---

## ⚙️ Script de connexion

Créer un fichier `.vbs` :

```vbscript
MsgBox "Coucou, bienvenue sur mon domaine informatique !", vbInformation, "Bienvenue"
```

![Script](./images/image_6_1.png)

---

# 🔒 Sécurisation du système

---

## 🚫 Restreindre le panneau de configuration

![Blocage panneau](./images/image_7_1.png)

---

## 🖼️ Bloquer le fond d’écran

![Blocage fond](./images/image_8_1.png)

---

## 🔄 Configuration des mises à jour

### Via interface Windows

![Windows Update](./images/image_9_1.png)

### Via PowerShell

```powershell
Get-WindowsUpdateLog
```

```powershell
Get-ChildItem "C:\Windows\Logs\WindowsUpdate" | Sort-Object LastWriteTime -Descending
```

---

# 🧠 Étude du BOOT

Analyse du gestionnaire de démarrage sur différents systèmes d’exploitation.

---

## 📁 Structure du projet

```bash
project/
│── README.md
│── images/
│   ├── image_1_1.png
│   ├── image_2_1.png
│   ├── image_3_1.png
│   ├── ...
```

---

## ✅ Conclusion

Ce projet met en évidence :

* l’importance de la **détection rapide des incidents**
* la mise en place de **stratégies de sécurité locales**
* le rôle clé de la **surveillance et des mises à jour**

---

## 👨‍💻 Auteur

Projet réalisé dans un cadre pédagogique.
