# 📝 Cours et Compilation LaTeX

Ce dépôt contient des cours de mathématiques au format LaTeX. La génération des PDF est automatisée grâce à GitHub Actions. Il n'est pas nécessaire d'installer une distribution LaTeX locale pour compiler les documents.

## 🏗️ Structure du dépôt

Pour que la compilation fonctionne correctement, il est impératif de respecter cette arborescence (les chemins relatifs sont codés en dur dans les fichiers `.tex`) :

* `00 - Modules latex communs/` : Contient les préambules et réglages généraux.
* `[Année] [Niveau]/` : Dossier parent d'une classe (ex : `25 - 26 6ème`).
    * `00 - Modules latex/` : Préambules spécifiques à ce niveau.
    * `[Numéro] - [Nom du chapitre]/` : Dossier de travail du chapitre contenant le `.tex` et les images.

## 🚀 Comment générer un PDF ?

La compilation est **manuelle** pour éviter de lancer des opérations à chaque petite modification de texte. Voici les étapes pour compiler un chapitre :

1. Cliquez sur l'onglet **Actions** en haut de la page du dépôt GitHub.
2. Dans le menu de gauche, sélectionnez **Compile LaTeX Document**.
3. Sur la droite de l'écran, cliquez sur le menu déroulant gris **Run workflow**.
4. Renseignez les deux champs avec précision :
    * **Chemin du dossier :** Le chemin exact depuis la racine. *(Exemple : `25 - 26 6ème/15 - Figures usuelles et aires`)*
    * **Nom du fichier .tex :** Le nom exact du fichier à l'intérieur de ce dossier. *(Exemple : `FiguresUsuelles_Aires.tex`)*
5. Cliquez sur le bouton vert **Run workflow** pour lancer le script.

## 📥 Récupérer le résultat

Une fois la compilation terminée (le point de l'action passe au vert), le script se charge d'enregistrer le document directement dans les fichiers du dépôt :

1. Retournez sur la page d'accueil de ce dépôt (onglet **Code**).
2. Ouvrez le dossier **`pdf/`** situé à la racine.
3. Vous y trouverez votre document prêt à être consulté ou téléchargé d'un simple clic !

💡 *Note d'organisation : Le script récupère automatiquement le niveau depuis le nom du dossier parent et renomme le fichier final pour un tri optimal. Vous obtiendrez un fichier formaté ainsi : `<Niveau>_<NomDuFichier>.pdf` (ex : `6ème_FiguresUsuelles_Aires.pdf`).*
