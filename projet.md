# PROJET – VERSION 0 (GÉNÉRÉE PAR L’IA GEMINI)

## Description du projet – Attrape les étoiles

Le projet consiste à créer un petit jeu interactif en HTML, CSS et JavaScript, en utilisant la bibliothèque Anime.js. Des étoiles apparaissent à l’écran et se déplacent grâce à des animations. Le joueur doit cliquer sur les étoiles pour les attraper avant qu’elles ne disparaissent. Lors du clic sur une étoile, une animation se déclenche (disparition ou changement de couleur). Chaque étoile attrapée ajoute un point au compteur affiché à l’écran.

## Démarche de création

Pour cette version 0, j’ai copié-collé la consigne du projet et demandé à **l’IA Gemini** de générer le jeu. J’ai rédigé un prompt décrivant précisément le fonctionnement attendu : des étoiles animées apparaissant à l’écran, que le joueur doit cliquer pour gagner des points.

L’IA m’a alors fourni une première version fonctionnelle du code, servant de base au projet. Après avoir relu cette version, j’ai effectué quelques ajustements mineurs, notamment la modification de la couleur des étoiles et de l’encadré du score, en m’aidant du site palettedecouleur afin de choisir des couleurs correspondant davantage à mes goûts.

## Diagramme de flux testprojet (version 0)

flowchart TD
    A[Démarrage du Jeu] --> B(L'écran de jeu s'active);
    B --> C((Plusieurs étoiles aléatoires apparaissent à l'écran));
    C --> D{Le joueur clique sur l'Étoile ?};
    D -- Oui --> E[Le score augmente de 1];
    E --> F[L'étoile disparaît];
    F --> C;
    D -- Non --> G{Le temps de vie de l'Étoile est écoulé ?};
    G -- Oui --> H[L'étoile disparaît];
    H --> C;

    style A fill:#D0F0C0,stroke:#333,stroke-width:2px,color:#000
    style D fill:#C0E0F0,stroke:#333,stroke-width:2px,color:#000
    style G fill:#C0E0F0,stroke:#333,stroke-width:2px,color:#000
