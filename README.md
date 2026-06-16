# 📝 Cours et Compilation LaTeX

Ce dépôt contient des cours de mathématiques au format LaTeX. La génération des PDF est automatisée grâce à GitHub Actions. Il n'est pas nécessaire d'installer une distribution LaTeX locale pour compiler les documents.

## 🏗️ Structure du dépôt

Pour que la compilation fonctionne correctement, il est impératif de respecter cette arborescence (les chemins relatifs sont codés en dur dans les fichiers `.tex`) :

* `00 - Modules latex communs/` : Contient les préambules et réglages généraux.
* `[Année] [Niveau]/` : Dossier parent d'une classe (ex : `25 - 26 6ème`).
    * `00 - Automatismes/` : Exercices d'automatismes (non compilés en mode niveau complet).
    * `00 - DM/` : Devoirs maison (non compilés en mode niveau complet).
    * `00 - Interro/` : Interrogations (non compilées en mode niveau complet).
    * `00 - Modules latex/` : Préambules spécifiques à ce niveau (non compilés).
    * `[Numéro] - [Nom du chapitre]/` : Dossier de travail d'un chapitre.

## 📄 Convention de nommage des fichiers `.tex`

> ⚠️ **Règle impérative à respecter pour que la compilation automatique fonctionne.**

Dans chaque dossier de chapitre, il peut y avoir plusieurs fichiers `.tex` (cours, bilans, exercices...). Le workflow les distingue ainsi :

| Type de fichier | Convention de nommage | Exemple |
|---|---|---|
| **Fichier principal** (cours) | **Sans underscore** `_` dans le nom | `Fractions.tex` |
| Fichiers secondaires (bilans, exercices...) | Avec underscore `_` dans le nom | `Fractions_02_Bilan.tex` |

Le mode **"Tout un niveau"** compile **uniquement le fichier principal** (sans underscore) de chaque chapitre.

## 🚀 Comment générer un PDF ?

La compilation est **manuelle** pour éviter de lancer des opérations à chaque petite modification de texte.

### Mode 1 — Un seul chapitre

1. Cliquez sur l'onglet **Actions** en haut de la page du dépôt GitHub.
2. Dans le menu de gauche, sélectionnez **Compile LaTeX Document**.
3. Cliquez sur le menu déroulant gris **Run workflow**.
4. Choisissez le mode **"Un seul chapitre"** et renseignez :
    * **Dossier du niveau :** *(ex : `25 - 26 6ème`)*
    * **Nom du sous-dossier :** *(ex : `07 - Les fractions`)*
    * **Nom du fichier .tex :** *(ex : `Fractions.tex`)*
5. Cliquez sur **Run workflow**.

### Mode 2 — Tout un niveau

1. Cliquez sur l'onglet **Actions**.
2. Sélectionnez **Compile LaTeX Document**.
3. Cliquez sur **Run workflow**.
4. Choisissez le mode **"Tout un niveau"** et renseignez :
    * **Dossier du niveau :** *(ex : `25 - 26 4ème`)*
5. Cliquez sur **Run workflow**.

> Tous les chapitres (dossiers `01` et au-delà) sont compilés **en parallèle**. Si un chapitre échoue, les autres continuent. Le résultat de chaque chapitre est visible individuellement dans l'onglet Actions.

## 📥 Récupérer le résultat

Une fois la compilation terminée (le point de l'action passe au vert) :

1. Retournez sur la page d'accueil de ce dépôt (onglet **Code**).
2. Ouvrez le dossier **`pdf/`** situé à la racine.
3. Vous y trouverez vos documents au format `<Niveau>_<NomDuFichier>.pdf` *(ex : `4ème_Fractions.pdf`)*.
