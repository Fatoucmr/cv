# VERSION 5

Par rapport à la version 4, cette version apporte une amélioration visuelle de la page de démarrage ainsi qu’un nouvel élément sonore.

J’ai utilisé l’IA **Gemini** pour ajouter un encadré sur la page de démarrage, afin d’améliorer l’esthétique générale et d’éviter que la page du jeu soit visible en arrière-plan avant le lancement d’une partie.

J’ai également ajouter le son **Instruments de la bibliothèque Tone.js**, qui se déclenche au démarrage d’une partie, renforçant ainsi l’immersion du joueur dès le début du jeu.

## Diagramme de flux testprojet5

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
