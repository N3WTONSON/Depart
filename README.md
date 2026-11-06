# Décompte Jimmy - Sauvegarde Directe des Messages sur GitHub

Cette version permet de **sauvegarder et partager tous les mots doux directement sur GitHub** (dans un fichier `messages.json`), sans passer par Firebase.

## 🚀 Comment ça marche ?
Quand un collègue tape un message sur le site, la page web utilise l'API GitHub pour écrire automatiquement le message dans le fichier `messages.json` de votre dépôt. Ainsi, **tout le monde voit les messages de tout le monde en temps réel** !

---

## 🛠️ Configuration en 3 étapes :

### Étape 1 : Créer le Dépôt GitHub & Activer GitHub Pages
1. Connectez-vous sur **GitHub.com**.
2. Créez un nouveau dépôt public (ex: `depart-jimmy`).
3. Téléversez les fichiers `index.html` et `messages.json` (un fichier contenant uniquement `[]`).
4. Dans **Settings** > **Pages**, sélectionnez la branche `main` et sauvegardez pour mettre votre site en ligne.

### Étape 2 : Générer un Token GitHub (PAT)
Pour autoriser la page web à enregistrer des messages dans le dépôt :
1. Allez dans les paramètres de votre compte GitHub (en haut à droite sur votre avatar > **Settings**).
2. Tout en bas du menu de gauche, cliquez sur **Developer Settings**.
3. Allez dans **Personal access tokens** > **Tokens (classic)**.
4. Cliquez sur **Generate new token** (classic).
5. Donnez-lui une note (ex: `Teams Départ Jimmy`).
6. Cochez la case **`repo`** (accès complet aux dépôts).
7. Cliquez sur **Generate token** et **copiez le jeton** (il commence par `ghp_...`).

### Étape 3 : Configurer le fichier `index.html`
1. Ouvrez le fichier `index.html`.
2. Aux alentours de la ligne 200, remplissez l'objet `GITHUB_CONFIG` :
   ```javascript
   const GITHUB_CONFIG = {
       owner: "VOTRE_PSEUDO_GITHUB",    // ex: "jimmy34"
       repo: "VOTRE_NOM_DE_REPO",       // ex: "depart-jimmy"
       token: "ghp_xxxxxxxxxxxxxxxxx",   // Votre Token copié à l'étape 2
       filePath: "messages.json"
   };
   ```
3. Sauvegardez le fichier sur GitHub.

---

### 📲 Intégration dans Teams :
Copiez simplement l'URL de votre site GitHub Pages (ex: `https://votre-pseudo.github.io/depart-jimmy/`), et ajoutez-la en tant qu'onglet **"Site Web"** dans Teams !
