# Calendrier Facture - Application de Gestion de Cabinet de Psychologie

Une application desktop complète pour la gestion d'un cabinet de psychologie, développée avec Next.js et Electron, fonctionnant entièrement en local avec sauvegarde automatique sur fichier JSON.

## 📋 À quoi sert l'application

**Calendrier Facture** est une solution complète pour les psychologues spécialisés (enfants, adolescents, adultes, thérapie EMDR) permettant de gérer efficacement :

### 👥 Gestion des Patients
- Fiche patient complète (informations personnelles, type, motif de consultation)
- Catégorisation par âge : Enfant, Adolescent, Adulte
- Suivi de l'évolution avec historique des rendez-vous
- Statistiques par patient

### 📅 Planning et Rendez-vous
- Vue calendrier : jour, semaine, mois
- Création de rendez-vous avec validation des conflits horaires
- Durées adaptables (15min, 30min, 45min, 1h, 1h30)
- Statuts : Programmé, Confirmé, Terminé, Annulé
- Affichage optimisé avec créneaux de 30 minutes

### 💰 Facturation Automatique
- Numérotation automatique conforme à la loi (FAC2024-0001)
- Génération PDF avec informations légales (SIRET, adresse, TVA)
- Suivi des factures (émise, payée, annulée)
- Historique complet des factures

### 🏥 Spécialisation EMDR
- Types de consultation spécialisés
- Suivi des objectifs et résultats thérapeutiques
- Notes et observations détaillées

### 💾 Stockage Local Sécurisé
- **Sauvegarde automatique** à chaque modification dans un fichier JSON
- **Aucune donnée sur internet** - tout reste sur votre PC
- Export/Import JSON pour sauvegarde externe
- Export CSV/Excel pour analyse des données

## 🛠️ Prérequis

- **Node.js** : 18.0.0 ou supérieur
- **npm** : 9.0.0 ou supérieur
- **Système** : Windows 10+, macOS 10.14+, ou Linux Ubuntu 18.04+

## 🚀 Installation

### Étape 1 : Télécharger le projet
- Cliquez sur les 3 points en haut à droite de v0
- Sélectionnez "Download ZIP"
- Décompressez le fichier sur votre PC

### Étape 2 : Installation des dépendances
Ouvrez un terminal dans le dossier du projet :
\`\`\`bash
npm install
\`\`\`

### Étape 3 : Configuration initiale
1. **Première utilisation** : Lancez l'application
2. **Configuration du Cabinet** : Renseignez vos informations (nom, adresse, SIRET) dans Paramètres
3. **Ajout de Patients** : Créez vos premiers patients
4. **Planification** : Organisez vos rendez-vous

## 🖥️ Lancement de l'application

### Mode Développement (recommandé)
\`\`\`bash
npm run electron-dev
\`\`\`
✅ Application desktop native
✅ Sauvegarde automatique sur fichier JSON
✅ Hot reload pour les modifications

### Mode Web (test uniquement)
\`\`\`bash
npm run dev
\`\`\`
⚠️ Utilise le cache navigateur (données perdues si cache vidé)

## 📦 Création de l'exécutable

### Build pour votre système
\`\`\`bash
# Windows (.exe)
npm run dist -- --win

# macOS (.app)
npm run dist -- --mac

# Linux (.AppImage)
npm run dist -- --linux

# Tous les systèmes
npm run dist
\`\`\`

L'exécutable sera créé dans le dossier `dist/` et pourra être installé sur n'importe quel PC.

## 💾 Gestion des données

### Emplacement du fichier JSON
Le fichier `cabinet-data.json` est automatiquement créé dans :
- **Windows** : `%USERPROFILE%/Documents/cabinet-data.json`
- **Mac** : `~/Documents/cabinet-data.json`
- **Linux** : `~/Documents/cabinet-data.json`

### Vérification de la sauvegarde
1. Lancez l'application via `npm run electron-dev`
2. Ouvrez la console de développement (F12)
3. Créez un nouveau patient
4. Vérifiez les logs :
   - ✅ `isElectron: true`
   - ✅ `electronAPI: [object Object]`
   - ✅ `Sauvegarde via ElectronStorage`

### Types de données stockées
- **Patients** : Informations personnelles, historique
- **Rendez-vous** : Planning, statuts, notes thérapeutiques
- **Factures** : Numérotation, montants, statuts
- **Paramètres** : Configuration du cabinet

## 📱 Interface Responsive

L'application s'adapte automatiquement à tous les écrans :
- **Desktop** : Interface complète avec sidebar
- **Tablet** : Layout adaptatif avec navigation optimisée
- **Mobile** : Menu hamburger, modals plein écran
- **Petits écrans** : Scroll horizontal pour les tableaux

## ⚖️ Conformité Légale

### Facturation
- Numérotation séquentielle obligatoire
- Remise à zéro annuelle automatique
- Mentions légales complètes (SIRET, TVA)
- Format PDF professionnel

### Protection des Données
- Stockage 100% local (RGPD compliant)
- Aucune transmission de données
- Contrôle total de l'utilisateur
- Export/sauvegarde sécurisés

## 🔧 Dépannage

### L'application ne démarre pas
1. Vérifier Node.js 18+ : `node --version`
2. Supprimer et réinstaller :
   \`\`\`bash
   rm -rf node_modules package-lock.json
   npm install
   \`\`\`

### La sauvegarde ne fonctionne pas
1. Vérifiez que vous lancez bien via `npm run electron-dev`
2. Ouvrez la console (F12) pour voir les logs
3. Vérifiez que le dossier Documents est accessible en écriture
4. Si `isElectron: false`, vous êtes en mode web (pas de sauvegarde JSON)

### Erreurs TypeScript
1. Rebuild complet :
   \`\`\`bash
   npm run build
   \`\`\`
2. Vérifier les logs de la console pour identifier les erreurs

## 📁 Structure du Projet

\`\`\`
calendrier-facture/
├── app/                    # Pages Next.js
│   ├── layout.tsx         # Layout principal
│   ├── page.tsx           # Navigation principale
│   └── globals.css        # Styles globaux
├── components/            # Composants React
│   ├── patients-view.tsx  # Gestion des patients
│   ├── appointments-view.tsx # Rendez-vous
│   ├── calendar-view.tsx  # Planning calendrier
│   ├── invoices-view.tsx  # Suivi des factures
│   └── settings-view.tsx  # Paramètres
├── lib/                   # Logique métier
│   ├── storage.ts         # Stockage principal
│   ├── electron-storage.ts # Stockage Electron
│   └── file-storage.ts    # Gestion fichiers
├── main.js               # Process principal Electron
├── preload.js            # Script de préchargement
└── package.json          # Configuration npm
\`\`\`

## 🎯 Utilisation Quotidienne

1. **Matin** : Consultez votre planning du jour
2. **Rendez-vous** : Marquez les consultations comme "Terminé" et remplissez les notes
3. **Facturation** : Générez automatiquement les factures PDF
4. **Suivi** : Consultez l'historique des patients et les statistiques

## 📞 Support

- **Console de développement** : F12 pour voir les erreurs
- **Logs détaillés** : Activés automatiquement pour le débogage
- **Sauvegarde manuelle** : Export JSON disponible dans Paramètres

---

**Version** : 1.0.0  
**Dernière mise à jour** : Janvier 2025  
**Licence** : Usage professionnel en cabinet de psychologie
\`\`\`

```typescriptreact file="GUIDE_ELECTRON.md" isDeleted="true"
...deleted...
