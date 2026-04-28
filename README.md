[README.md](https://github.com/user-attachments/files/27082051/README.md)
# 📚 Suivi des EDN

> Application macOS de suivi et de révision pour les EDN (Épreuves Dématérialisées Nationales).

![Platform](https://img.shields.io/badge/platform-macOS-blue)
![Swift](https://img.shields.io/badge/Swift-5.9%2B-orange)
![SwiftUI](https://img.shields.io/badge/UI-SwiftUI-purple)

---

## 🎯 À propos

**Suivi des EDN** est une application native macOS conçue pour les étudiants en médecine qui préparent les EDN. Elle permet de suivre sa progression sur les 367 items du programme R2C, d'organiser ses révisions selon un système de répétition espacée, et de planifier ses sessions de travail au quotidien.

Créé par Benjamin avec l'IA Claude

## ⬇️ Téléchargement

[**Télécharger Suivi des EDN v1.0**](https://github.com/benjilbs/Suivi-des-EDN/releases/tag/v1.0)

> Dézipper et glisser SuividesEDN.app dans ton dossier Applications ou sur le bureau.

---

## ✨ Fonctionnalités

### 🗂️ Gestion des items
- Liste complète des **367 items EDN** avec numéro, nom et badges de spécialité
- Marquage **vu / non vu** par item
- Compteur de **passages** avec annulation du dernier passage
- Compteur de **dossiers progressifs (DP)** avec annulation
- Toggle **"Pas de DP requis"** pour les items sans DP associé
- **Alerte automatique** si ≥ 2 passages effectués sans DP fait 🚨
- Marquage manuel **"À revoir"** (flag jaune ⚠️)

### ⭐ Système d'étoiles & QCM
- Notation de **1 à 5 étoiles** (manuelle ou automatique via score QCM)
- Saisie d'un **score QCM (0–100%)** avec conversion automatique en étoiles
- **Historique complet** des sessions QCM par item (date, score, étoiles)
- Suppression d'une session QCM individuelle
- Détection des items **"fragiles"** (ayant régressé dans leur historique d'étoiles)

### 🧠 Répétition espacée
- Calcul automatique de la **prochaine date de révision** selon le niveau d'étoiles
- **Intervalles configurables** par niveau (1★ à 5★) via une vue dédiée
- Réinitialisation des intervalles aux valeurs par défaut

### 🔍 Filtres & tri
- Filtre **"Tous"** / **"À réviser"** (retard de révision + items flaggés manuellement)
- **Filtres par spécialité**
- **Tris** : par numéro, vus en premier, non vus, étoiles ↑↓, passages ↑↓, QCM ↑↓
- **Recherche textuelle** (numéro, nom, mnémotechnique)
- Mise en avant automatique des items prioritaires
- PS: les filtres ne concerne pas le collège de référence mais plutôt dans quel collège peut-on trouver tel ou tel item.

### 📊 Dashboard
- Salutation contextuelle selon l'heure
- **Streak de révision** actuel et record personnel 🔥
- Visualisation des **14 derniers jours** d'activité
- Statistiques du jour : items validés, sessions QCM, score moyen

### 📅 Programme du jour & du lendemain
- **Suggestions automatiques** (items en retard, fragiles, à revoir)
- Ajout manuel au programme via une sheet filtrée
- Marquage automatique **"fait"** lors de la validation d'un item
- **Programme du lendemain** : préparation à l'avance avec report automatique

### 📆 Calendrier de révisions
- Vue calendrier mensuelle avec navigation
- **Code couleur** par densité de révisions (vert / orange / rouge)
- Affichage des items **en retard** avec nombre de jours de retard
- Détail des items à réviser par jour sélectionné

### 📈 Statistiques par spécialité
- Progression en **anneau (ring chart)** par spécialité
- Nombre d'items maîtrisés, vus, et **moyenne d'étoiles**
- Vue **accordéon** avec liste détaillée par item

### 📝 Mnémotechniques
- **Éditeur de texte riche (RTF)** intégré par item
- Support **gras** (⌘B), **italique** (⌘I), **souligné** (⌘U)
- Normalisation automatique de la police au collage

### 📑 Fiches & images
- Ajout de **PDFs** par item (sélecteur de fichier ou glisser-déposer)
- Ajout d'**images** par item (sélecteur de fichier ou glisser-déposer)
- Ouverture directe des PDFs dans le lecteur système
- Suppression individuelle des fichiers

### 💾 Sauvegarde & export
- **Sauvegarde automatique** à chaque modification (UserDefaults + fichier JSON)
- **Sauvegarde versionnée quotidienne** (conservation des 7 derniers jours)
- Sauvegarde d'urgence horodatée en cas d'erreur de décodage
- Export / Import manuel de la sauvegarde (JSON)
- Raccourci vers le **dossier de sauvegarde** dans le Finder
- **Export PDF complet** : progression, étoiles, passages, mnémotechniques, statistiques par spécialité

### ⚙️ Paramètres
- Choix du **thème** : Système / Clair / Sombre
- **Réinitialisation** de la progression (étoiles, passages, vus) avec conservation des mnémotechniques, PDFs et images
- **Barre de progression globale** dans la sidebar

---

## 🚀 Installation

### Prérequis
- macOS 13.0 (Ventura) ou supérieur

## 🗂️ Données & persistance

Les **mnémotechniques, PDFs et images** ne sont jamais effacés lors d'une réinitialisation de la progression.

## 🩺 Retours à faire

Hésitez pas à me faire des retours si vous avez installé l'application. Mon instagram: benji_lbs

## ⚠️ Avertissement

Cette application est un **outil d'organisation personnelle**. 
Les items correspondent au programme **R2C** (Réforme du 2e Cycle) en vigueur pour les EDN lorsque l'application a été créée (2026).

---

_Bon courage pour tes révisions ! 💪_
