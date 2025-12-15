# VERSION 2 - testprojet2

Par rapport à la version 1, cette version introduit de nouvelles fonctionnalités liées au score et à la fin de la partie.

J’ai demandé à l’IA **Gemini** d’ajouter **l’affichage du score final** lorsque le timer arrive à son terme, ainsi qu’un **tableau récapitulatif des scores précédents**. Dans la version générée, le tableau apparaissait à la fois au début et à la fin de la partie.

J’ai donc modifié le code manuellement afin que ce **tableau ne s’affiche uniquement à la fin du jeu**, en supprimant les éléments que je ne souhaitais pas conserver. Enfin, j’ai ajusté **l’apparence du tableau**, notamment sa couleur, que j’ai changée en rose afin qu’elle soit cohérente avec l’esthétique générale du jeu.

## Diagramme de flux testprojet2

```mermaid
flowchart TB
    A@{ label: "J'arrive sur la page et je vois le bouton Démarrer" } --> B@{ label: "Je clique sur Démarrer"}
    B --> C@{ label: "L'écran de jeu s'active, le timer 60s et les étoiles commencent à apparaître" }
    C --> D{"Je vois des étoiles ?"}
    D -- Oui --> E@{ label: "J'arrive à cliquer dessus à temps ?" }
    E -- Oui --> F["Mon score augmente"]
    E -- Non --> G@{ label: "L'étoile disparaît" }
    F --> H{"Le Timer est à 0s ?"}
    G --> H
    H -- Oui --> I["Fin du Jeu, le temps est écoulé"]
    I --> J["Le score final apparait"]
    J --> J_V2_Table["Le tableau des scores précédents apparaît"]
    J_V2_Table --> K{"Je veux rejouer ?"}
    K -- Oui --> B
    K -- Non --> L["Je quitte la page"]

    A@{ shape: rect}
    B@{ shape: rounded}
    C@{ shape: rect}
    E@{ shape: diamond}
    G@{ shape: rect}
```
