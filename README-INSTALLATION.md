# 🔒 Installation de Cabinet Manager (Usage Personnel)

Cette application est développée pour un **usage personnel** et n'est **pas signée numériquement** par un certificat Microsoft reconnu. Cela peut déclencher des avertissements de sécurité Windows.

## ⚠️ Avertissement Windows SmartScreen

Lors de l'installation ou de la mise à jour, vous verrez probablement ce message :

> "Windows a protégé votre PC"
> "L'exécution de cette application a été bloquée"

**C'est normal et attendu** pour une application non signée.

---

## 🛠️ Comment installer malgré l'avertissement

### Méthode 1 : Contourner SmartScreen (Recommandé)

1. **Au premier lancement**, Windows affiche : "Windows a protégé votre PC"
2. Cliquez sur **"Informations complémentaires"**
3. Cliquez sur **"Exécuter quand même"**
4. L'application s'installe normalement

![Windows SmartScreen](https://user-images.githubusercontent.com/example.png)

### Méthode 2 : Désactiver temporairement SmartScreen (Déconseillé)

⚠️ **Attention** : Cette méthode désactive une protection Windows. Utilisez-la uniquement si vous êtes sûr de la source.

1. Ouvrir **Paramètres Windows**
2. Aller dans **Sécurité Windows** → **Contrôle des applications et navigateur**
3. Sous **Vérifier les applications et fichiers**, sélectionner **Désactivé**
4. Installer l'application
5. **IMPORTANT** : Réactiver SmartScreen après l'installation

---

## 🔄 Mises à jour automatiques

L'application vérifie automatiquement les mises à jour via GitHub. Lors d'une mise à jour :

1. Une notification apparaît dans l'application
2. Cliquez sur **"Télécharger"**
3. Une fois téléchargé, cliquez sur **"Redémarrer maintenant"**
4. **Si Windows bloque** : Suivez les mêmes étapes que pour l'installation initiale

---

## 💡 Pourquoi cette application n'est-elle pas signée ?

La signature d'une application Windows nécessite :
- Un **certificat de signature de code** (300-500€/an)
- Un processus de validation d'identité
- Renouvellement annuel

Pour une application **personnelle** utilisée par 2 personnes, ce coût n'est pas justifié.

---

## ✅ Cette application est-elle sûre ?

**OUI**, pour plusieurs raisons :

1. **Open Source** : Le code source est disponible sur GitHub
2. **Développée par Malcolm** : Pour son usage personnel
3. **Pas de collecte de données** : Toutes les données restent en local
4. **Hébergée sur GitHub** : Plateforme de confiance pour les développeurs

---

## 🆘 Problèmes fréquents

### "L'application ne se lance pas après installation"

**Solution** : 
1. Clic droit sur l'exécutable → **Propriétés**
2. Cochez **"Débloquer"** en bas de la fenêtre
3. Cliquez **"Appliquer"** puis **"OK"**
4. Relancez l'application

### "Windows Defender bloque l'installation"

**Solution** :
1. Ouvrir **Sécurité Windows**
2. Aller dans **Protection contre les virus et menaces**
3. Cliquer sur **"Gérer les paramètres"**
4. Sous **"Exclusions"**, ajouter le dossier d'installation de Cabinet Manager

### "L'auto-update ne fonctionne pas"

**Solution** :
1. Télécharger manuellement la dernière version depuis GitHub
2. Désinstaller l'ancienne version
3. Installer la nouvelle version en suivant les instructions ci-dessus

---

## 📞 Support

Pour toute question ou problème :
- Ouvrir une **Issue** sur GitHub : [cabinet-manager-autoupdater/issues](https://github.com/Malcolm0609/cabinet-manager-autoupdater/issues)
- Contacter directement Malcolm

---

## 📄 Licence

Cette application est destinée à un **usage personnel** uniquement.

© 2025 Malcolm - Cabinet Manager