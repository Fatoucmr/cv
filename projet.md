Projet - Attrape les étoiles

Je vais créer un petit jeu en HTML, CSS et JavaScript, en utilisant Anime.js.
Des étoiles apparaîtront à l’écran et se déplaceront grâce à des animations.
Le joueur devra cliquer sur les étoiles pour les attraper avant qu’elles ne disparaissent.
Lors du clic sur une étoile, une petite animation (disparition ou changement de couleur) se déclenchera.
Chaque étoile attrapée ajoutera un point au compteur affiché à l’écran.

Pour la verion 0, j’ai d’abord utilisé l’IA (gemini et chatgpt) afin de générer une base de code en HTML, CSS et JavaScript, avec l’ajout de la librairie Anime.js. J’ai formulé un prompt décrivant le jeu que je voulais créer : des étoiles apparaissant à l’écran, se déplaçant grâce à des animations, et que le joueur doit cliquer pour les attraper et gagner des points. L’IA m’a fourni une première version fonctionnelle du code, que j’ai ensuite relue. J’ai ensuite modifié moi-même les couleurs en m’aidant du site web "palettedecouleur", afin de choisir celles qui me correspondaient le mieux.

Pour la version 1, je me suis appuyé sur la version 0 générée par l’IA, puis j’ai ajouté plusieurs améliorations personnelles. J’ai intégré un effet sonore lors du clic sur les étoiles en utilisant un exemple déjà existant de Tone.js (le code « hello tone »). J’ai également modifié les couleurs du fond et des étoiles, ainsi que le style de l’écriture. Enfin, j’ai ajouté un timer, dont j’ai trouvé le code dans la documentation de Phaser, dans la partie consacrée au Timer.
