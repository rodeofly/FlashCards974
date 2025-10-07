Flashcards SRS
Démonstration en ligne : https://rodeofly.github.io/FlashCards974/

Une application de flashcards minimaliste conçue pour un apprentissage efficace grâce au principe de la répétition espacée (Spaced Repetition System - SRS). L'application est entièrement contenue dans un unique fichier HTML, ne nécessite aucun serveur, et est pensée pour être hébergée simplement sur GitHub Pages.

Le moteur de répétition est inspiré par les conclusions de l'étude de Nate Kornell (2009) sur l'efficacité de l'espacement par rapport au bachotage.

✨ Fonctionnalités
100% Côté Client : L'application est un unique fichier index.html. Pas de serveur, pas de base de données, pas de compilation.

Algorithme SRS : Un système de répétition espacée simple mais efficace optimise votre apprentissage en vous présentant les cartes au bon moment.

Bibliothèque de Decks Permanents : Chargez des decks pré-configurés directement depuis le dépôt GitHub.

Import / Export CSV : Importez vos propres decks depuis un fichier CSV local et téléchargez votre progression à tout moment pour la sauvegarder.

Persistance Locale : Votre progression est automatiquement sauvegardée dans le localStorage de votre navigateur. Rechargez la page, vous reprenez où vous en étiez.

Raccourcis Clavier : Utilisez les touches Espace et 1-4 pour des sessions de révision rapides et fluides.

Mode Sombre : Thème clair ou sombre pour s'adapter à vos préférences.

🚀 Comment l'utiliser
Accédez à l'application via le lien de la démonstration.

Choisissez un deck :

Cliquez sur l'un des boutons "Charger..." pour utiliser un deck de la bibliothèque permanente.

Ou cliquez sur "Importer un CSV local..." pour charger votre propre fichier.

Étudiez :

Lisez la question, puis cliquez sur la carte (ou appuyez sur Espace) pour voir la réponse.

Évaluez votre réponse en utilisant les boutons ou les touches 1 (À revoir), 2 (Difficile), 3 (Correct), 4 (Facile).

Terminez la session :

Une fois toutes les cartes du jour révisées, un message s'affiche. Vous pouvez alors cliquer sur "Retourner à la bibliothèque" pour choisir un autre deck ou quitter.

Votre progression est sauvegardée automatiquement après chaque carte.

📚 Comment ajouter des decks permanents
N'importe qui peut enrichir la bibliothèque de l'application en suivant ces étapes simples :

Créez un fichier .json pour votre nouveau deck à l'intérieur du dossier /decks/. Le fichier doit contenir un tableau d'objets avec les clés Question et Réponse.

Exemple : nouveau-deck.json

JSON

[
  {
    "Question": "Quelle est la vitesse de la lumière ?",
    "Réponse": "Environ 299 792 458 m/s"
  },
  {
    "Question": "Qui a peint la Joconde ?",
    "Réponse": "Léonard de Vinci"
  }
]
Mettez à jour le catalogue en modifiant le fichier decks/manifest.json. Ajoutez une nouvelle entrée pour votre deck en respectant le format :

JSON

[
  {
    "nom": "Vocabulaire Anglais",
    "fichier": "anglais.json"
  },
  {
    "nom": "Capitales du Monde",
    "fichier": "capitales.json"
  },
  {
    "nom": "Mon Nouveau Deck",
    "fichier": "nouveau-deck.json"
  }
]
Envoyez vos modifications sur GitHub (Commit & Push). L'application affichera dynamiquement le nouveau deck sur la page d'accueil.

📄 Format des fichiers CSV locaux
Pour importer vos propres decks, le fichier .csv doit respecter une structure simple :

La première ligne doit être l'en-tête.

Il doit contenir au minimum les colonnes Question et Réponse.

Exemple :

Extrait de code

Question,Réponse
Quelle est la capitale de l'Italie ?,Rome
Combien de côtés a un hexagone ?,6
🛠️ Principe Technique
L'application repose sur trois piliers :

Un fichier index.html unique qui contient toute la structure (HTML), le style (CSS) et la logique (JavaScript).

Le localStorage du navigateur, utilisé pour stocker et persister l'état de la session de l'utilisateur (le deck en cours et sa progression).

L'API fetch de JavaScript, utilisée pour charger dynamiquement la liste des decks (manifest.json) et le contenu des decks permanents depuis le dépôt GitHub.

📜 Licence
Ce projet est sous licence MIT.
