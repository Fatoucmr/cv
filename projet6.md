# VERSION 6

Par rapport à la version 5, cette version apporte des ajustements visuels et ergonomiques, en particulier pour le niveau spécial, ainsi qu’un nouvel élément sonore.

J’ai demandé à l’IA **Gemini** de faire en sorte que les **encadrés du jeu**, pour chaque niveau, aient la **même couleur que celle représentant le niveau**, afin d’améliorer la cohérence visuelle. J’ai également demandé que, dans le niveau spécial, le message de consigne soit affiché au début du jeu, et non plus dans un encadré sur le côté.

Ensuite, j’ai demandé l’ajout d’un **message minimaliste indiquant la couleur à cliquer**, correspondant à la couleur de la bordure de l’encadré du score. Ce message est placé sous l’encadré du score, afin de rester visible sans gêner le jeu. J’ai aussi souhaité l’ajout d’un petit message d’avertissement indiquant une pénalité de –1 point lorsque le joueur se trompe.

Enfin, j’ai ajouté un son signalant la fin de la partie, en utilisant **le son Signals de la bibliothèque Tone.js**, afin d’informer clairement le joueur que le jeu est terminé, et j'ai fait quelques changements esthétiques (couleurs,texte).

# Conclusion

Au fil des différentes versions, le projet Attrape les étoiles a évolué de manière progressive et structurée, tant sur le plan technique qu’esthétique. La version 0, générée par l’IA Gemini, a servi de base fonctionnelle et m’a permis de comprendre la structure du code.

Chaque nouvelle version a introduit des améliorations précises : ajout de fonctionnalités (timer, boutons, scores, niveaux), enrichissement du gameplay avec un niveau spécial, choix libre des niveaux et ajout progressif d’effets sonores via Tone.js.

Tout au long du projet, j’ai utilisé l’IA comme un outil d’aide, tout en personnalisant, corrigeant et améliorant chaque élément pour développer ma compréhension du code. L’attention portée aux couleurs, aux messages et aux sons a permis d’améliorer la lisibilité, l’esthétique et l’immersion, tout en rendant le jeu agréable et fonctionnel.

## Diagramme de flux testprojet6

```mermaid
flowchart TB
    A@{ label: "Je vois le tableau des niveaux et scores et j'ai le choix entre les niveaux 1 2 3 ou 4 spécial" } --> B{"Quel Niveau choisir ?"}
    B -- Niveau 1, 2 ou 3 --> CN["Démarrage du niveau sélectionné"]
    CN --> DN{"Temps écoulé ?"}
    DN -- Oui --> EN{"Score du niveau sélectionné supérieur ou égal au nombre Requis ?"}
    EN -- Non --> FN["Échec du niveau sélectionné"]
    FN --> GN{"Que veux-je faire ?"}
    GN -- Recommencer Niveau N --> CN
    GN -- Changer de Niveau --> B
    EN -- Oui --> I["RÉUSSITE des autres niveaux ou niveau 4 fin du jeu"]
    B -- Niveau 4 Spécial --> C4S["Démarrage Niveau 4 Spécial Timer 60s"]
    C4S --> D4S["J'observe que la couleur étoile et bordure score changent"]
    D4S --> E4S{"Couleur étoile est égale à couleur bordure et je clique ?"}
    E4S -- Oui --> F4S["Mon Score augmente"]
    E4S -- Non --> G4S["Continuer la partie"]
    F4S --> H4S{"Temps écoulé ?"}
    G4S --> H4S
    H4S -- Oui --> I
    I --> K["Affichage du Tableau Récapitulatif des Scores"]
    K --> L{"Je veux refaire un Niveau ?"}
    L -- Oui --> B
    L -- Non --> M["Je quitte la page"]

    A@{ shape: rect}
    style B fill:#FFE0B2
    style CN color:#000000,fill:#C8E6C9
    style DN fill:#C8E6C9
    style EN fill:#C8E6C9
    style FN fill:#BBDEFB
    style GN color:#000000,fill:#FFE0B2
    style I fill:#C8E6C9
    style C4S fill:#FFCDD2
    style D4S fill:#FFCDD2
    style E4S fill:#FFCDD2
    style F4S fill:#FFCDD2
    style G4S fill:#FFCDD2
    style H4S fill:#FFE0B2
    style K fill:#C8E6C9
    style L fill:#FFE0B2
``` 
