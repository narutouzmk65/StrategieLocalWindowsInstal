# 🛡️ Gestion des Incidents de Sécurité & Politique de Configuration

> **Compte Rendu** — BTS SIO | Cybersécurité & Administration Windows
> Référence : CERT-FR · ANSSI · CNIL

---

## 📋 Table des matières

* Mission 1 — Analyse CERT-FR
* Mission 2 — Politique de configuration locale

---

# 🔍 Mission 1 — Analyse CERT-FR

---

## 🎯 Question 1 — Cibles des cinq alertes les plus récentes

| # | Référence           | Cible                       | Risque                                             |
| - | ------------------- | --------------------------- | -------------------------------------------------- |
| 1 | CERTFR-2026-ALE-004 | **BIG-IP APM — F5**         | Exécution de code à distance sans authentification |
| 2 | CERTFR-2026-ALE-003 | **Messagerie instantanée**  | Campagnes ciblées (secteurs sensibles)             |
| 3 | CERTFR-2026-ALE-001 | **Ivanti EPMM**             | Scripts IoC disponibles                            |
| 4 | CERTFR-2025-ALE-014 | **React Server Components** | Vulnérabilité critique                             |
| 5 | CERTFR-2026-ALE-002 | **Cisco SD-WAN**            | Compromission réseau                               |

---

## 🗂️ Question 2 — Logiciels ou systèmes obsolètes

| # | Système            | Détail                |
| - | ------------------ | --------------------- |
| 1 | SharePoint 2016    | Faille path traversal |
| 2 | SharePoint 2019    | Toujours vulnérable   |
| 3 | SonicWall (ancien) | Exploitation active   |
| 4 | Cisco ASA / FTD    | DoS à distance        |
| 5 | WSUS               | Exécution de code     |

---

## 🔎 Question 3 — Détecter une intrusion

```
OBSERVER → ANALYSER → DÉLIMITER
```

### 🔍 Observer

* Logs / SIEM → anomalies
* Antivirus / EDR → alertes
* Dysfonctionnements système
* Impact métier

### 📌 Délimiter

* Nombre de machines touchées
* Propagation éventuelle
* Origine probable

---

## 🚨 Question 4 — Réagir à une intrusion

### 🧱 1. Endiguer

```
Isoler réseau → Bloquer accès → Éteindre machines
```

### 💾 2. Préserver les preuves

* Sauvegarder logs hors ligne
* Étendre la rétention
* Conserver traces système

### 👥 3. Organiser

* Informer équipes
* Identifier responsables
* Coordonner actions

---

## ⚖️ Question 5 — Obligations légales

### 📌 3 actions principales

1. **ANSSI**

   * OSE / OIV
   * Données sensibles

2. **Plainte**

   * Trace légale
   * Enquête
   * Responsabilité

3. **CNIL**

   * Données personnelles
   * ⏱️ 72h max

---

## 🔄 Question 6 — Reprise après incident

### 🧠 Gestion de crise

* Décisions rapides
* Communication maîtrisée
* Éviter blocages

### 🛡️ Assurance

* Contacter rapidement
* Activer couverture
* Identifier prestataires

---

## 🛠️ Question 7 — Outils de sécurité

| Type             | Solution          |
| ---------------- | ----------------- |
| Grande structure | Prestataire PRIS  |
| PME              | Cybermalveillance |
| Tous             | SIEM / EDR / XDR  |

---

# ⚙️ Mission 2 — Politique de configuration locale

---

## 👤 Partie 1 — Créer un utilisateur

```
Démarrer → Gestion de l’ordinateur
→ Utilisateurs et groupes locaux
→ Utilisateurs → Nouveau
```

⚠️ Désactiver :

> "L'utilisateur doit changer le mot de passe"

---

## 💻 Partie 2 — Ouvrir MMC

```
Windows + R → mmc.exe
```

---

## 🔌 Partie 3 — Ajouter un composant

```
Fichier → Ajouter/Supprimer un composant
```

---

## 📋 Partie 4 — Stratégie de groupe

* Ajouter : **Éditeur d’objets de stratégie**
* Cliquer sur **Ajouter**

---

## 📂 Partie 5 — Sélection utilisateur

```
Parcourir → Onglet Utilisateurs → Choisir utilisateur
```

---

## 📝 Partie 6 — Configuration

### 🖼️ Fond d’écran

```
Configuration utilisateur
→ Modèles admin
→ Bureau → Papier peint
```

Exemples :

```
C:\Windows\Web\Wallpaper
\\Serveur\Partage\image.jpg
```

---

### 📜 Script de connexion

```vbscript
MsgBox "Bienvenue sur le domaine !", vbInformation, "Connexion"
```

Associer :

```
Scripts ouverture session → Ajouter
```

---

## 🚫 Restriction panneau de config

```
Configuration utilisateur
→ Modèles admin
→ Panneau de config → Interdire accès
```

---

## 🖼️ Bloquer fond d’écran

```
Configuration utilisateur
→ Personnalisation
→ Empêcher modification
```

---

## 🔄 Windows Update

### Interface :

```
Paramètres → Windows Update
```

### PowerShell :

```powershell
Get-WindowsUpdateLog
```

---

## 🖥️ BOOT (msconfig)

| Onglet    | Rôle                 |
| --------- | -------------------- |
| Général   | Mode démarrage       |
| Boot      | OS / Mode sans échec |
| Services  | Gestion services     |
| Démarrage | Apps lancement       |
| Outils    | Accès outils système |

---

## 📎 Ressources

* CERT-FR
* ANSSI
* CNIL
* Cybermalveillance

---

<div align="center">

**Compte rendu BTS SIO — Gestion des Incidents**

</div>
