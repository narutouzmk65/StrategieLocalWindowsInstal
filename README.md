# 🌍 WorldTour — README (TP WordPress) | Guide simple + technique

Site WordPress du projet **WorldTour** (agence de voyage nationale).  
➡️ Site en ligne : https://blog27143.wordpress.com/  

📌 Ce README sert de **documentation de TP** : il explique **comment accéder au site**, **comprendre la structure**, et **mettre à jour le contenu**.

> ⚠️ Important : sur ce TP, le contenu est géré **avec les blocs WordPress (éditeur)**.  
> Les manipulations décrites ci-dessous restent valables même si on n’est pas “informatique”.

---

## 📚 Sommaire (cliquable)

- [1. Objectif du TP](#1-objectif-du-tp)
- [2. Prérequis](#2-prérequis)
- [3. Accès au site](#3-accès-au-site)
  - [3.1 Site en ligne (WordPress.com)](#31-site-en-ligne-wordpresscom)
  - [3.2 Site local (srv-lamp)](#32-site-local-srv-lamp)
- [4. Structure du site WorldTour (pages et menus)](#4-structure-du-site-worldtour-pages-et-menus)
  - [4.1 Pages principales](#41-pages-principales)
  - [4.2 Menu de navigation](#42-menu-de-navigation)
  - [4.3 Rôles et accès](#43-rôles-et-accès)
- [5. Mettre à jour le contenu (avec les blocs)](#5-mettre-à-jour-le-contenu-avec-les-blocs)
  - [5.1 Modifier une page existante](#51-modifier-une-page-existante)
  - [5.2 Ajouter un nouveau voyage](#52-ajouter-un-nouveau-voyage)
  - [5.3 Ajouter une nouvelle antenne](#53-ajouter-une-nouvelle-antenne)
- [6. Points d’attention (erreurs fréquentes)](#6-points-dattention-erreurs-fréquentes)
- [7. Support](#7-support)

---

## 1. Objectif du TP

Ce TP consiste à :
- mettre en place un site WordPress WorldTour (en ligne + en local),
- organiser les pages (antennes / voyages),
- permettre des mises à jour simples du contenu (textes, photos, tarifs),
- publier proprement une vitrine d’agence de voyage.

---

## 2. Prérequis

Avant de commencer, il faut avoir :  
- un navigateur récent (Chrome, Firefox ou Edge)  
- un accès Internet (pour la version en ligne)  
- un serveur local **srv-lamp** (IP : 192.168.1.103) avec Apache/PHP/MySQL  
- WinSCP (accès sFTP) et PuTTY (accès SSH)  
- des identifiants d’équipe (ga26 à gh26, mot de passe = identifiant par défaut)  

---

## 3. Accès au site

### 3.1 Site en ligne (WordPress.com)

Le site public du projet est accessible ici :  
https://blog27143.wordpress.com/

➡️ La version en ligne sert de **vitrine** : on y publie la version “propre”.  
💡 Conseil TP : tester d’abord en local, puis publier en ligne.

---

### 3.2 Site local (srv-lamp)

La version locale sert à travailler / tester sans casser le site public.

#### a) Configuration proxy (si nécessaire)
Pour accéder à `srv-lamp` depuis un poste, il peut être nécessaire d’ajouter une **exception proxy** pour le domaine `srv-lamp` dans les paramètres réseau du navigateur.

#### b) Connexion au serveur (SSH)
1. Ouvrir **PuTTY**
2. Dans “Host Name” : `srv-lamp` ou `192.168.1.103`
3. Port : `22` | Type : `SSH`
4. “Open”
5. Se connecter avec l’identifiant d’équipe

⚠️ Note TP important : changer le mot de passe avec la commande :
`passwd`

> ⚠️ Attention : le mot de passe administrateur WordPress ne peut pas être réinitialisé.  
> Il doit être noté immédiatement (ex : Trello).

#### c) Lancer l’installation WordPress en local
1. Se connecter en sFTP avec **WinSCP**
2. Aller dans : `public_html/wordpress/`
3. Ouvrir le navigateur et aller sur :  
   `http://srv-lamp/~ga26/` (remplacer `ga26` par l’identifiant)

Ensuite, l’assistant WordPress s’affiche :
- Langue : Français
- Base de données :
  - Nom : `ga26_wp` (selon identifiant)
  - Identifiant : identifiant d’équipe
  - Mot de passe : mot de passe d’équipe
  - Serveur : `localhost`
  - Préfixe : `wp_` (par défaut)

✅ Une fois terminé, WordPress est installé.

#### d) Accès base de données (si besoin TP)
phpMyAdmin :  
`http://srv-lamp/phpmyadmin/`

---

## 4. Structure du site WorldTour (pages et menus)

### 4.1 Pages principales

Le site est organisé en pages “logiques” :

- **Accueil** : présentation générale de l’agence
- **Antennes** :
  - Antenne Tarbes
  - Antenne Toulouse
  - Antenne Auch  
  (présentation, responsables, employés, informations)
- **Les Voyages** : liste de toutes les destinations
  - Dubaï
  - Islande
  - République Dominicaine  
  (description, photos, tarifs, départs, contact)
- **Contact** : page utile pour joindre l’agence

---

### 4.2 Menu de navigation

Le menu est réglé dans :  
**Apparence > Menus**

Il contient généralement :
- Accueil
- Nos Antennes (menu déroulant)
- Nos Voyages (menu déroulant)
- Contact

➡️ But TP : que l’utilisateur trouve tout en 2 clics max.

---

### 4.3 Rôles et accès

Deux rôles simples :
- **Administrateur** : accès complet (installation, configuration)
- **Éditeur WorldTour** : modification du contenu (pages, textes, photos)

Création d’un compte éditeur :  
Tableau de bord > Utilisateurs > Ajouter > Rôle : Éditeur

---

## 5. Mettre à jour le contenu (avec les blocs)

Le site se modifie via des “blocs” (texte, image, galerie, tableau…).  
➡️ On clique sur un bloc → on modifie → on met à jour la page.

### 5.1 Modifier une page existante

1. Tableau de bord WordPress
2. **Pages > Toutes les pages**
3. Cliquer sur la page (ex : “Islande”)
4. Modifier le texte / photo / tableau
5. Cliquer sur **Mettre à jour** (ou Publier)

✅ La modification est enregistrée.

---

### 5.2 Ajouter un nouveau voyage

Méthode TP conseillée (simple + propre) :
1. Pages > Toutes les pages
2. Ouvrir une page voyage existante (ex : Dubaï)
3. Dupliquer / recréer sur le même modèle
4. Remplacer :
   - titre (nom du pays)
   - descriptif
   - galerie photo (minimum 4 photos)
   - tarifs (tableau)
   - lieux de départ
5. Vérifier la mise en page
6. Publier
7. Ajouter le voyage dans le menu “Nos Voyages”

💡 Conseil : garder la même structure pour tous les voyages.

---

### 5.3 Ajouter une nouvelle antenne

1. Pages > Toutes les pages
2. Dupliquer une antenne existante (ex : Tarbes)
3. Remplacer :
   - nom de la ville
   - adresse / contact
   - responsables
   - employés
   - photos
4. Publier
5. Ajouter l’antenne dans “Nos Antennes” (menu)

---

## 6. Points d’attention (erreurs fréquentes)

- ✅ Toujours cliquer sur **Mettre à jour** avant de quitter
- ❌ Ne pas supprimer une page si on n’est pas sûr
- ✅ Garder une structure identique entre voyages (plus facile à maintenir)
- ✅ Tester en local si possible avant de modifier le site en ligne
- ⚠️ Les mots de passe doivent être notés : pas de réinitialisation admin facile

---

## 7. Support

Documentation WordPress : https://fr.wordpress.org/support/  
Contact projet : f.bravais@gmail.com

