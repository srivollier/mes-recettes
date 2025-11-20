# 🍳 Mes Recettes

Une GitHub Page élégante pour référencer et afficher vos recettes stockées dans un Google Spreadsheet.

## 📋 Vue d'ensemble

Ce projet vous permet de :
- 📝 Gérer vos recettes dans Google Sheets (une feuille = une recette)
- 🌐 Les afficher automatiquement sur une belle page web
- 🔍 Rechercher et filtrer vos recettes par catégorie
- 📱 Accéder à vos recettes depuis n'importe quel appareil

## 🚀 Configuration rapide

### Étape 1 : Préparer votre Google Spreadsheet

1. **Créez un nouveau Google Spreadsheet** ou utilisez-en un existant
2. **Nommez-le** (par exemple : "Mes Recettes")

### Étape 2 : Configurer Google Apps Script

1. Dans votre spreadsheet, allez dans **Extensions > Apps Script**
2. Copiez le contenu du fichier `Code.gs` de ce repository
3. Collez-le dans l'éditeur Apps Script
4. *(Optionnel)* Exécutez la fonction `createTemplateSheet()` pour créer une feuille modèle :
   - Cliquez sur la fonction dans la liste déroulante
   - Cliquez sur le bouton "Exécuter" (▶️)
   - Autorisez les permissions si demandé

### Étape 3 : Créer vos recettes

#### Structure d'une feuille de recette

Chaque feuille représente une recette avec support des **sections flexibles** :

| Colonne A (Champ) | Colonne B (Valeur) |
|-------------------|-------------------|
| **Nom** | Quiche Lorraine maison |
| **Catégorie** | Plat principal |
| **Portions** | 6 personnes |
| **Temps de préparation** | 30 min |
| **Temps de cuisson** | 35 min |
| **Difficulté** | Moyen |
| *(ligne vide)* | |
| **Ingrédients - Pâte** | - 250g de farine<br>- 125g de beurre<br>- 1 œuf |
| **Ingrédients - Garniture** | - 200g de lardons<br>- 3 œufs<br>- 20cl de crème<br>- 100g de gruyère |
| *(ligne vide)* | |
| **Préparation - Pâte** | 1. Mélanger farine et beurre<br>2. Former une boule<br>3. Réfrigérer 30 min |
| **Préparation - Garniture** | 1. Faire revenir les lardons<br>2. Battre les œufs avec la crème |
| **Préparation - Assemblage** | 1. Étaler la pâte<br>2. Garnir de lardons<br>3. Verser l'appareil<br>4. Enfourner 35 min |
| *(ligne vide)* | |
| **Notes** | Peut être préparé la veille |
| **Source** | Recette familiale |

**✨ Nouveau : Sections flexibles !**

Vous pouvez organiser vos ingrédients et préparations en sections avec des noms libres :
- Format : `Ingrédients - [Nom de votre section]` (ex: "Ingrédients - Pour la pâte à tarte")
- Format : `Préparation - [Nom de votre section]` (ex: "Préparation - Assemblage et cuisson")
- Idéal pour les recettes complexes (tartes, pâtisseries, plats en plusieurs étapes)

#### Champs reconnus

Le script reconnaît automatiquement ces champs :
- **Nom** / Titre / Recette
- **Catégorie** / Type
- **Ingrédients**
- **Préparation** / Instructions / Description
- **Temps de préparation** / Temps prep
- **Temps de cuisson** / Cuisson
- **Difficulté** / Niveau
- **Portions** / Personnes / Pour
- **Notes** / Remarques / Conseils
- **Source** / Origine

#### Feuilles ignorées

Ces noms de feuilles seront automatiquement ignorés :
- Index
- Config
- Template
- Modèle

### Étape 4 : Déployer la Web App

1. Dans l'éditeur Apps Script, cliquez sur **Déployer > Nouveau déploiement**
2. Cliquez sur l'icône ⚙️ et sélectionnez **Application Web**
3. Configurez :
   - **Description** : "API Recettes"
   - **Exécuter en tant que** : **Moi**
   - **Qui a accès** : **Tout le monde**
4. Cliquez sur **Déployer**
5. **Copiez l'URL de déploiement** (elle ressemble à `https://script.google.com/macros/s/AKfycby.../exec`)
6. Cliquez sur **OK**

⚠️ **Important** : Vous devrez peut-être autoriser l'accès la première fois. Suivez les instructions à l'écran.

### Étape 5 : Activer GitHub Pages

1. Allez sur votre repository GitHub : https://github.com/srivollier/mes-recettes
2. Cliquez sur **Settings** (⚙️)
3. Dans le menu de gauche, cliquez sur **Pages**
4. Sous "Source", sélectionnez :
   - **Branch** : `main`
   - **Folder** : `/ (root)`
5. Cliquez sur **Save**
6. Attendez quelques minutes que GitHub déploie votre site

Votre site sera accessible à : **https://srivollier.github.io/mes-recettes/**

### Étape 6 : Configurer l'URL de votre Web App

**Option A : Configuration dans le code (recommandée)**

1. Ouvrez le fichier `index.html`
2. Trouvez la ligne (environ ligne 419) :
   ```javascript
   const DEFAULT_WEB_APP_URL = 'VOTRE_URL_ICI';
   ```
3. Remplacez `'VOTRE_URL_ICI'` par l'URL de votre Web App (de l'étape 4)
4. Sauvegardez et poussez vers GitHub
5. Vos recettes se chargeront automatiquement ! 🎉

**Option B : Configuration via l'interface**

1. Ouvrez votre GitHub Page : https://srivollier.github.io/mes-recettes/
2. Cliquez sur "⚙️ Configurer l'URL"
3. Collez l'URL de votre Web App
4. Cliquez sur **Enregistrer**

**Plus de détails :** Consultez `CONFIGURATION.md`

## 📝 Utilisation quotidienne

### Ajouter une nouvelle recette

1. **Méthode 1 - Depuis le site web (⭐ Recommandé)**
   - Allez sur votre site de recettes
   - Cliquez sur le bouton "➕ Ajouter une recette"
   - Demandez au ChatGPT de générer votre recette au format CSV
   - Copiez et collez le CSV complet dans le champ
   - Cliquez sur "Importer la recette"
   - ✅ La recette apparaît immédiatement sur le site !

2. **Méthode 2** : Dupliquer la feuille Template
   - Faites un clic droit sur la feuille "Template"
   - Sélectionnez "Dupliquer"
   - Renommez la feuille avec le nom de votre recette
   - Remplissez les informations

3. **Méthode 3** : Créer une nouvelle feuille
   - Créez une nouvelle feuille (bouton + en bas)
   - Nommez-la avec le nom de votre recette
   - Ajoutez les champs en colonne A et les valeurs en colonne B

### Modifier une recette

Modifiez directement les valeurs dans la feuille correspondante. Les changements seront visibles instantanément sur votre site (après un rechargement de la page).

### Supprimer une recette

Supprimez simplement la feuille correspondante dans votre spreadsheet.

## 🎨 Fonctionnalités

### Site web
- ✅ Affichage en grille responsive (s'adapte à tous les écrans)
- ✅ Recherche en temps réel
- ✅ Filtrage par catégorie
- ✅ Compteur de recettes
- ✅ Design moderne avec animations
- ✅ Configuration facile de l'URL de l'API
- ✅ **Vue détaillée avec modal** pour chaque recette
- ✅ **Ajustement proportionnel intelligent** : éditez une quantité, tout s'ajuste automatiquement
- ✅ **Mise à jour automatique des portions** selon les quantités modifiées
- ✅ **Mode étape par étape** pour suivre les recettes en cuisinant
- ✅ **Import de recettes CSV** directement depuis le site web
- ✅ **Accès aux ingrédients** via panneau latéral en mode étape par étape

### Google Apps Script
- ✅ Menu personnalisé dans Google Sheets
- ✅ Import automatique intelligent (détecte si 1 ou plusieurs recettes)
- ✅ Import en masse ou unitaire
- ✅ **Import depuis le web** via API POST
- ✅ Génération de feuille Template
- ✅ Compteur et testeur intégrés
- ✅ **Support des sections flexibles** pour organiser recettes complexes

## 🔢 Ajusteur de portions

L'ajusteur de portions permet de modifier automatiquement toutes les quantités d'ingrédients selon le nombre de personnes désiré.

### Comment l'utiliser

1. **Cliquez sur une recette** pour ouvrir la vue détaillée
2. **Cliquez sur "🔢 Ajuster les quantités"** pour déplier le module (masqué par défaut pour économiser l'espace)
3. **Utilisez les boutons + et −** pour augmenter ou diminuer le nombre de portions
4. **Les quantités s'ajustent automatiquement** dans tous les ingrédients
5. **Cliquez sur "Réinitialiser"** pour revenir aux quantités originales

### Formats reconnus

L'ajusteur détecte et ajuste intelligemment :
- **Nombres entiers** : `250g` → `500g` (pour 2× portions)
- **Nombres décimaux** : `1.5 kg` → `3 kg`
- **Fractions** : `1/2 tasse` → `1 tasse` ou `1.5 tasse`
- **Fractions mixtes** : `1 1/2 tasse` → `3 tasse`
- **Unités variées** : g, kg, ml, l, cl, cuillères, sachets, pincées, pots...

**Note sur les fractions :** Le système essaie de préserver les fractions communes (1/2, 1/3, 1/4, 2/3, 3/4) dans l'affichage lorsque c'est pertinent. Les autres valeurs sont affichées en décimal avec arrondissage intelligent.

### Arrondissage intelligent

- **< 1** : 2 décimales (ex: `0.33 cuillère`)
- **1-10** : 1 décimale (ex: `2.5 g`)
- **> 10** : arrondi à l'entier (ex: `350 g`)

### Exemple

**Recette originale pour 4 personnes :**
- 200g de farine
- 1/2 sachet de levure
- 0.5 kg de beurre

**Ajusté pour 6 personnes (×1.5) :**
- **300g** de farine
- **3/4** sachet de levure (fraction préservée !)
- **0.75 kg** de beurre

### Ajustement proportionnel intelligent 🎯

Vous pouvez **éditer directement n'importe quelle quantité** et tout s'ajuste automatiquement :

1. **Cliquez sur "✏️ Modifier les quantités"** pour activer le mode édition
2. **Cliquez sur une quantité** (ex: "200g") dans n'importe quel ingrédient
3. **Modifiez la valeur** (ex: changez en "400g")
4. **Validez** avec Entrée ou en cliquant ailleurs
5. ✨ **Magie !** Tous les autres ingrédients s'ajustent proportionnellement
6. 📊 Le **nombre de portions** est aussi mis à jour automatiquement
7. 🔒 **Cliquez sur "Verrouiller les quantités"** pour désactiver le mode édition

**Exemple concret :**

Recette originale pour **4 personnes** :
- 200g de farine
- 3 œufs
- 500ml de lait

Vous modifiez la farine à **300g** (×1.5) → Tout devient :
- 300g de farine ✏️
- **4.5** œufs (arrondi automatique)
- **750ml** de lait
- Portions : **6 personnes**

**Avantages :**
- 🎯 **Intuitif** : Éditez directement comme dans un tableur
- 🔄 **Proportionnel** : Tous les ingrédients restent cohérents
- 👥 **Intelligent** : Le nombre de personnes suit automatiquement
- ⚡ **Rapide** : Un seul clic pour ajuster toute la recette
- ↩️ **Réversible** : Bouton "Réinitialiser" pour revenir à l'original
- 📱 **Universel** : Les ajustements s'appliquent au mode étape par étape et au drawer mobile
- 🔒 **Sécurisé** : Le mode édition évite les modifications accidentelles

**Raccourcis clavier :**
- **Entrée** : Valider le changement
- **Échap** : Annuler et restaurer la valeur précédente

**Synchronisation automatique :**
Les quantités ajustées sont automatiquement reflétées dans :
- 📋 Le **drawer mobile** des ingrédients
- 👨‍🍳 Le **mode étape par étape** (ingrédients par étape)
- 🍳 Le **drawer "tous les ingrédients"** du mode étape par étape

## 🎯 Utiliser les sections (pour recettes complexes)

### Pourquoi utiliser des sections ?

Les sections permettent d'organiser clairement les recettes complexes :
- **Tarte** : séparer la pâte, la garniture, la cuisson
- **Pâtisserie** : distinguer la génoise, la crème, le montage
- **Plats mijotés** : marinade, cuisson, finition
- **Recettes asiatiques** : sauce, viande, légumes, assemblage

### Comment créer une section

**Format simple :**
```
Ingrédients - [Nom libre de votre section]
Préparation - [Nom libre de votre section]
```

**Exemples de noms de sections :**

Pour les ingrédients :
- "Ingrédients - Pâte" / "Ingrédients - Pour la pâte à tarte"
- "Ingrédients - Garniture" / "Ingrédients - Pour la farce"
- "Ingrédients - Sauce" / "Ingrédients - Assaisonnement"
- "Ingrédients - Caramel" / "Ingrédients - Décoration"

Pour la préparation :
- "Préparation - Pâte" / "Préparation - Réalisation de la pâte"
- "Préparation - Garniture"
- "Préparation - Assemblage" / "Préparation - Assemblage et cuisson"
- "Préparation - Finition" / "Préparation - Service"

### Affichage sur le site

Les sections s'affichent de manière organisée avec :
- Un titre de section en couleur (violet)
- Une barre verticale à gauche pour visualiser la hiérarchie
- Un espacement clair entre chaque section

Exemple d'affichage :
```
📋 Ingrédients :

  Pâte :
  - 250g de farine
  - 125g de beurre

  Garniture :
  - 200g de lardons
  - 3 œufs

👨‍🍳 Préparation :

  Pâte :
  1. Mélanger farine et beurre
  2. Réfrigérer 30 min

  Assemblage :
  1. Étaler la pâte
  2. Garnir
  3. Enfourner
```

## 🔧 Personnalisation

### Modifier les couleurs

Éditez le fichier `index.html` et modifiez les couleurs dans la section `<style>` :

```css
/* Dégradé de fond */
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);

/* Couleur principale */
color: #667eea;
```

### Ajouter de nouveaux champs

1. Ajoutez le champ dans votre feuille Google Sheets
2. Ajoutez le mapping dans `Code.gs` dans la fonction `normalizeFieldName()`
3. Modifiez `index.html` pour afficher ce nouveau champ

## 🐛 Dépannage

### Mes recettes ne s'affichent pas

1. Vérifiez que votre Web App est bien déployée et l'URL est correcte
2. Assurez-vous que l'accès est configuré sur "Tout le monde"
3. Testez l'URL directement dans votre navigateur (vous devriez voir du JSON)
4. Vérifiez la console du navigateur (F12) pour voir les erreurs

### Erreur "Script function not found"

Assurez-vous d'avoir bien sauvegardé le script et redéployé la Web App après les modifications.

### Les nouveaux changements ne s'affichent pas

1. Rechargez la page avec Ctrl+F5 (ou Cmd+Shift+R sur Mac)
2. Vérifiez que vous avez bien sauvegardé vos modifications dans Google Sheets
3. Attendez quelques secondes que Google Sheets synchronise

### Problème d'autorisation

Si vous avez un message d'erreur lors du déploiement :
1. Cliquez sur "Paramètres avancés"
2. Cliquez sur "Accéder à [votre projet] (dangereux)"
3. Autorisez les permissions demandées

## 📁 Structure du projet

```
mes-recettes/
├── index.html          # Page web principale
├── Code.gs            # Script Google Apps Script (à copier dans Google Sheets)
└── README.md          # Ce fichier
```

## 🤝 Contribution

N'hésitez pas à :
- Signaler des bugs
- Proposer des améliorations
- Partager vos idées

## 📄 Licence

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

Ce projet est sous licence **Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)**.

### Vous êtes autorisé à :

- ✅ **Partager** — copier et redistribuer le matériel sous n'importe quel format
- ✅ **Adapter** — remixer, transformer et créer à partir du matériel

### Selon les conditions suivantes :

- **Attribution** — Vous devez créditer l'œuvre originale de manière appropriée
- **NonCommercial** — Vous ne pouvez pas utiliser ce projet à des fins commerciales
- **ShareAlike** — Si vous modifiez ou créez à partir de ce projet, vous devez distribuer vos contributions sous la même licence

Pour plus de détails, consultez le fichier [LICENSE](LICENSE) ou visitez [creativecommons.org/licenses/by-nc-sa/4.0/](https://creativecommons.org/licenses/by-nc-sa/4.0/)

## 🎯 Prochaines améliorations possibles

- [ ] Ajout de photos pour chaque recette
- [ ] Export des recettes en PDF
- [ ] Calcul automatique des portions
- [ ] Mode sombre
- [ ] Favoris
- [ ] Planificateur de menus
- [ ] Liste de courses automatique

---

**Bon appétit ! 🍽️**

Pour toute question : ouvrez une issue sur GitHub.

