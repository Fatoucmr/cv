Projet - Attrape les étoiles

Je vais créer un petit jeu en HTML, CSS et JavaScript, en utilisant Anime.js.
Des étoiles apparaîtront à l’écran et se déplaceront grâce à des animations.
Le joueur devra cliquer sur les étoiles pour les attraper avant qu’elles ne disparaissent.
Lors du clic sur une étoile, une petite animation (disparition ou changement de couleur) se déclenchera.
Chaque étoile attrapée ajoutera un point au compteur affiché à l’écran.

Pour la verion 0, j’ai d’abord utilisé l’IA (gemini et chatgpt) afin de générer une base de code en HTML, CSS et JavaScript, avec l’ajout de la librairie Anime.js. J’ai formulé un prompt décrivant le jeu que je voulais créer : des étoiles apparaissant à l’écran, se déplaçant grâce à des animations, et que le joueur doit cliquer pour les attraper et gagner des points. L’IA m’a fourni une première version fonctionnelle du code, que j’ai ensuite relue. J’ai ensuite modifié moi-même les couleurs en m’aidant du site web "palettedecouleur", afin de choisir celles qui me correspondaient le mieux.

Pour la version 1, je me suis appuyé sur la version 0 générée par l’IA, puis j’ai ajouté plusieurs améliorations personnelles. J’ai intégré un effet sonore lors du clic sur les étoiles en utilisant un exemple déjà existant de Tone.js (le code « hello tone »). J’ai également modifié les couleurs du fond et des étoiles, ainsi que le style de l’écriture. Enfin, j’ai ajouté un timer, que j’ai trouvé sur "easytimer.js", le Countdown Timer. Ensuite, j'ai demandé un exemeple de code à l'IA pour les boutons start et restart, que j'ai ajouté, ainsi qu'un encadré qui encadre le jeu.

Pour la version 2, j’ai demandé à Gemini d’ajouter au jeu que, lorsque le minuteur se termine, on voie directement le score final réalisé, ainsi qu’un tableau affichant les scores précédents pour suivre l’historique des parties. Ensuite, j’ai personnalisé ce tableau des scores en le renommant Tableau de Chasse aux Étoiles, et j’ai remplacé l’en-tête du rang par “N° Partie” pour qu’il corresponde mieux au thème du jeu. Et j'ai modifié la couleur, afin que le tableau soit rose.
