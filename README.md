# 📊 Dashboard PSI - Suivi des Candidatures

Bienvenue sur le **Dashboard PSI**, une application web interactive permettant d'afficher, suivre et gérer la liste des candidatures en temps réel. Le projet s'appuie sur une structure légère basée sur du HTML/JavaScript et un fichier de données `data/candidatures.json`.

---

## 🚀 Guide d'installation et de configuration

Pour déployer et utiliser votre propre instance de ce tableau de bord, suivez les étapes ci-dessous.

### 1. Fork du dépôt
1. En haut à droite de cette page GitHub, cliquez sur le bouton **Fork**.
2. Sélectionnez le compte ou l'organisation dans lequel vous souhaitez copier le projet.
3. Conservez ou modifiez le nom du dépôt, puis validez en cliquant sur **Create fork**.

---

### 2. Création du Token d'accès GitHub (Personal Access Token)
Afin d'autoriser l'application web à lire ou écrire dans votre dépôt (par exemple pour mettre à jour automatiquement le fichier JSON), vous devez générer un Token GitHub :

1. Cliquez sur votre photo de profil (en haut à droite sur GitHub) > **Settings**.
2. Dans le menu de gauche, descendez tout en bas et cliquez sur **Developer settings**.
3. Allez dans **Personal access tokens** > **Tokens (classic)** (ou *Fine-grained tokens* selon votre usage).
4. Cliquez sur **Generate new token** (*Generate new token (classic)*).
5. Donnez un nom explicite à votre token (ex: `Dashboard-PSI-Token`).
6. Définissez la durée d'expiration (ex: 90 jours ou No expiration).
7. Cochez les permissions requises :
   - Pour un token classique : cochez **`repo`** (accès complet aux dépôts privés/publics).
8. Cliquez sur **Generate token** en bas de page.
9. **Copiez immédiatement le token généré** et conservez-le en lieu sûr (il ne sera plus affiché).

---

### 3. Configuration de l'application
Ouvrez le projet dans votre éditeur de code ou directement sur GitHub pour adapter les paramètres de configuration dans votre code JavaScript (souvent situé au début de `index.html` ou dans un fichier `app.js` / `config.js`) :

1. **Renseigner le nom du dépôt et de l'utilisateur :**
   ```javascript
   const GITHUB_USERNAME = "votre-nom-utilisateur";
   const REPO_NAME = "votre-nom-de-depot";
   ```
2. **Définir le chemin vers les données (`data path`) :**
   ```javascript
   const DATA_PATH = "data/candidatures.json";
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

### 🟢 Priorité Haute (Fonctionnalités de base)
- [ ] **Gestion des accès / Securité :** Éviter de stocker le token GitHub en clair dans le code client (passer par une authentification dynamique ou un formulaire de saisie locale dans le navigateur).
- [ ] **Formulaire d'ajout de candidature :** Permettre l'ajout d'une candidature directement depuis l'interface sans modifier à la main le fichier `candidatures.json`.
- [ ] **Édition et Suppression :** Ajouter des boutons d'action sur chaque ligne/carte pour modifier le statut ou supprimer une candidature.

### 🟡 Priorité Moyenne (Expérience Utilisateur & Visualisation)
- [ ] **Recherche et Filtres avancés :**
  - [ ] Recherche par mot-clé (nom d'entreprise, poste).
  - [ ] Filtres par statut (*En attente*, *Entretien*, *Refusé*, *Accepté*).
- [ ] **Statistiques & Graphiques :**
  - [ ] Graphique circulaire des candidatures par statut.
  - [ ] Graphique temporel des postulations par mois/semaine.
- [ ] **Pagination ou Scroll infini :** Optimiser l'affichage si le nombre de candidatures devient trop important.

### 🔵 Priorité Basse (Améliorations techniques)
- [ ] **Notifications / Rappels :** Ajouter un indicateur pour les candidatures nécessitant une relance (ex: > 14 jours sans réponse).
- [ ] **Export des données :** Ajouter un bouton pour exporter la liste au format CSV ou Excel.
- [ ] **Mode Sombre / Clair :** Implémenter un sélecteur de thème pour le confort visuel.
- [ ] **Déploiement GitHub Pages :** Configurer GitHub Pages dans les réglages du dépôt pour héberger l'application gratuitement.