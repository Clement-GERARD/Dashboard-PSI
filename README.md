# 📊 Dashboard PSI

Dashboard interactif pour la gestion et le suivi des candidatures PSI, connecté directement à un dépôt GitHub pour la persistance des données.

---

## 🚀 Configuration & Guide de démarrage

### Étape 1 : Forker le dépôt
1. Sur GitHub, cliquez sur le bouton **Fork** en haut à droite de cette page pour créer votre propre copie du dépôt sous votre compte.
2. Activez **GitHub Pages** dans les paramètres (*Settings > Pages*) de votre dépôt forké si vous souhaitez l'héberger gratuitement.

---

### Étape 2 : Générer un Personal Access Token (PAT) GitHub
Pour permettre au dashboard de lire et enregistrer vos candidatures dans votre dépôt :
1. Allez dans vos paramètres GitHub : **Settings > Developer Settings > Personal Access Tokens > Fine-grained tokens** (ou *Tokens (classic)*).
2. Cliquez sur **Generate new token**.
3. Donnez un nom au token (ex. `Dashboard-PSI-Token`).
4. Accordez l'accès au dépôt `dashboard-psi` et cochez les permissions **Contents (Read & Write)**.
5. Copiez la clé générée.

---

### Étape 3 : Configurer la synchronisation Git dans l'application
Lors de votre première ouverture de l'application (ou via le panneau **Paramètres / Configuration Git**) :

1. **Utilisateur / Dépôt (`owner/repo`)** : Entrez votre identifiant GitHub et le nom du dépôt (ex. `votre-utilisateur/dashboard-psi`).
2. **Chemin des données (`path`)** : Saisissez le chemin du fichier JSON de stockage, par défaut :
   ```text
   data/candidatures.json
   ```
3. **Configurer le Token GitHub :**
   - Renseignez le token dans votre variable de configuration ou via l'interface d'administration du Dashboard (si une boîte de dialogue d'authentification est prévue) :
   ```javascript
   const GITHUB_TOKEN = "votre_token_github_ici";
   ```

---

## 📁 Structure du projet

```text
.
├── index.html            # Interface principale de l'application
├── data/
│   └── candidatures.json # Fichier JSON contenant la liste des candidatures
└── README.md             # Documentation du projet
```

---

## 📝 TODO - Choses à développer et à améliorer

Voici la liste des fonctionnalités prévues et des pistes d'amélioration pour le projet :

### 🎨 Interface & UX
- [ ] **Statistiques & Graphiques :**
  - [ ] Graphique circulaire des candidatures par statut.
  - [ ] Graphique temporel des postulations par mois/semaine.
- [ ] **Pagination ou Scroll infini :** Optimiser l'affichage si le nombre de candidatures devient trop important.

### ⚙️ Fonctionnalités
- [ ] **Notifications / Rappels :** Ajouter un indicateur pour les candidatures nécessitant une relance (ex: > 14 jours sans réponse).
- [ ] **Mode Sombre / Clair :** Implémenter un sélecteur de thème pour le confort visuel.

## 👤 Auteur

Projet développé et maintenu par Clément Gérard.
