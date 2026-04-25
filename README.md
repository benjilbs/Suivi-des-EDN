[README.md](https://github.com/user-attachments/files/27082051/README.md)
# 📚 EDN Planner

> Application macOS de suivi et de révision pour les EDN (Épreuves Dématérialisées Nationales.

![Platform](https://img.shields.io/badge/platform-macOS-blue)
![Swift](https://img.shields.io/badge/Swift-5.9%2B-orange)
![SwiftUI](https://img.shields.io/badge/UI-SwiftUI-purple)
![License](https://img.shields.io/badge/license-MIT-green)

---

## 📸 Aperçu

> _Screenshots à venir_

---

## 🎯 À propos

**EDN Planner** est une application native macOS conçue pour les étudiants en médecine qui préparent les EDN (anciennement ECN). Elle permet de suivre sa progression sur les 367 items du programme R2C, d'organiser ses révisions selon un système de répétition espacée, et de planifier ses sessions de travail au quotidien.

Créé par Benjamin avec l'aide de Claude 🤝

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
- Nettoyage automatique des dates orphelines

### 🔍 Filtres & tri
- Filtre **"Tous"** / **"À réviser"** (retard de révision + items flaggés manuellement)
- **Filtres par spécialité** : UE11, Ortho-Traumato, MIR-URG, Gynéco-Obs, Thérapeutique, Rhumatologie, HGE, Oncologie
- **Tris** : par numéro, vus en premier, non vus, étoiles ↑↓, passages ↑↓, QCM ↑↓
- **Recherche textuelle** (numéro, nom, mnémotechnique)
- Mise en avant automatique des items prioritaires

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
- Xcode 15 ou supérieur
- Swift 5.9+

### Depuis les sources

```bash
# 1. Cloner le dépôt
git clone https://github.com/TON_USERNAME/EDNPlanner.git
cd EDNPlanner

# 2. Ouvrir dans Xcode
open EDNPlanner.xcodeproj

# 3. Sélectionner ton équipe de signature dans Xcode
# Xcode > Signing & Capabilities > Team

# 4. Compiler et lancer (⌘R)
```

> Aucune dépendance externe. Tout est natif Swift / SwiftUI / AppKit.

---

## 📂 Structure du projet

```
EDNPlanner/
├── Item.swift                 # Modèle de données (Item, QCMSession, StarHistory)
├── ItemStore.swift            # Store principal, persistance, logique métier
├── ContentView.swift          # Vue principale (NavigationSplitView, filtres, tri)
├── DashboardView.swift        # Dashboard (streak, stats du jour)
├── DayPlanSectionView.swift   # Programme du jour et du lendemain
├── DayPlanManager.swift       # Gestionnaire du programme journalier
├── CalendarView.swift         # Calendrier de révisions
├── ItemDetailView.swift       # Détail d'un item (étoiles, QCM, DP, fichiers)
├── StatisticsView.swift       # Statistiques par spécialité
├── ReviewIntervalsView.swift  # Configuration des intervalles de répétition espacée
├── QCMHistoryView.swift       # Historique des sessions QCM
├── RichTextEditor.swift       # Éditeur RTF pour les mnémotechniques
├── StreakManager.swift        # Gestion du streak de révision
├── PDFExporter.swift          # Export PDF de la progression
├── Constants.swift            # Ensembles d'items par spécialité
└── Suivi_des_EDNApp.swift     # Point d'entrée de l'application
```

---

## 🗂️ Données & persistance

Les données sont sauvegardées dans :
```
~/Library/Application Support/EDNPlanner/
├── edn_backup.json              ← Sauvegarde principale
├── edn_daily_YYYY-MM-DD.json   ← Sauvegardes quotidiennes (7 derniers jours)
├── edn_emergency_*.json        ← Sauvegardes d'urgence (si erreur de décodage)
├── pdf_<id>_<nom>.pdf          ← PDFs associés aux items
└── img_<id>_<nom>.png          ← Images associées aux items
```

Les **mnémotechniques, PDFs et images** ne sont jamais effacés lors d'une réinitialisation de la progression.

---

## 🩺 Spécialités disponibles

| Spécialité | Nombre d'items |
|---|---|
| UE11 | 39 |
| Ortho - Traumato | 16 |
| MIR - URG | 58 |
| Gynéco - Obs | 35 |
| Thérapeutique | 10 |
| Rhumatologie | 31 |
| HGE | 25 |
| Oncologie | 25 |

> Un item peut appartenir à plusieurs spécialités.

---

## 🤝 Contribuer

Les contributions sont les bienvenues ! Pour proposer une amélioration :

1. Forker le dépôt
2. Créer une branche (`git checkout -b feature/ma-fonctionnalite`)
3. Committer les changements (`git commit -m 'Ajout de ma fonctionnalité'`)
4. Pousser la branche (`git push origin feature/ma-fonctionnalite`)
5. Ouvrir une Pull Request

---

## 📄 Licence

Ce projet est distribué sous licence **MIT**. Voir le fichier [LICENSE](LICENSE) pour plus d'informations.

---

## ⚠️ Avertissement

Cette application est un **outil d'organisation personnelle**. Elle ne remplace pas les ressources officielles de préparation aux EDN (cours, référentiels R2C, annales).

Les items correspondent au programme **R2C** (Réforme du 2e Cycle) en vigueur pour les EDN.

---

_Bon courage pour tes révisions ! 💪_
