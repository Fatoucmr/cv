# VERSION 4 - testprojet4

Par rapport à la version 3, cette version apporte **une modification importante de la structure du jeu**, en laissant au joueur la liberté de **choisir directement le niveau** dès le lancement de la partie.

J’ai demandé à l’IA **Gemini** d’ajouter un **menu de sélection des niveaux**, permettant de choisir librement entre les trois niveaux existants. J’ai également demandé l’ajout d’un **niveau spécial**, dont la règle est différente : pour qu’une étoile soit comptabilisée, le joueur doit cliquer dessus uniquement lorsque sa couleur correspond à celle de la bordure du score. Cette couleur change toutes les 3 secondes. Le timer de ce niveau spécial est fixé à 60 secondes.

J’ai aussi demandé que chaque **bouton de niveau possède une couleur spécifique** afin de faciliter la compréhension :

- **Niveau 1** : vert
- **Niveau 2** : jaune
- **Niveau 3** : orange
- **Niveau spécial** : rouge
  
Une **phrase explicative** a également été ajoutée sur le côté de l’écran afin de clarifier la règle du niveau spécial pour le joueur.

Concernant les scores, j’ai demandé l’ajout d’un tableau de score affichant le meilleur score par niveau, qui apparaît uniquement à la fin de chaque partie. 

En parallèle, j’ai supprimé la condition de progression obligatoire entre les niveaux, ainsi que les tableaux qui s’affichaient avant le début du jeu, afin de simplifier l’expérience utilisateur.

Après la génération du code, j’ai apporté plusieurs modifications personnelles, j’ai ajusté les couleurs du niveau spécial en m’appuyant sur le site **palettesdecouleurs**, puis retravaillé le style général et les titres pour qu’ils correspondent à l’esthétique souhaitée.

Enfin, j’ai modifié la gestion du son, j’ai remplacé le son déclenché lors du clic sur une étoile par **Tone.Synth**, et ajouté un son différent (**Samples**) lorsqu’une erreur est commise dans le niveau spécial. Ces deux sons proviennent de la bibliothèque **Tone.js**.

## Diagramme de flux testprojet4

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
