# VERSION 3

Par rapport à la version 2, cette version introduit un **système de niveaux** qui structure davantage le jeu et augmente progressivement la difficulté.

J’ai demandé à l’IA Gemini d’ajouter **trois niveaux**, chacun avec une durée spécifique :

- **Niveau 1** : 60 secondes
- **Niveau 2** : 40 secondes
- **Niveau 3** : 20 secondes

J’ai également demandé la création de **deux tableaux distincts** :

- Un **premier tableau affiché au début du jeu**, présentant les différents niveaux et leur durée.
- Un **second tableau affiché à la fin**, récapitulant le score obtenu pour chaque niveau.

La progression entre les niveaux est conditionnée par la réussite du niveau précédent :

- Pour valider le niveau 1, le joueur doit attraper au minimum **20 étoiles**.
- Pour le niveau 2, un minimum de **40 étoiles** est requis.
- Pour le niveau 3, il faut attraper au minimum **60 étoiles**.

Afin de renforcer la lisibilité et l’immersion, j’ai également demandé que **les étoiles aient une couleur différente selon le niveau**. Enfin, après l’intégration de ces éléments, j’ai retravaillé certains aspects du projet (couleurs, textes et espacements) afin d’obtenir un rendu visuel plus cohérent et conforme à mes attentes.

## Diagramme de flux testprojet3

```mermaid
flowchart TB
    A@{ label: "Je vois 'Démarrer' et le Tableau des Niveaux/Durées" } --> B@{ label: "Je clique sur 'Démarrer'" }
    B --> C1["Démarrage Niveau 1 Timer 60s"]
    C1 --> D1{"Temps écoulé ?"}
    D1 -- Non --> D1
    D1 -- Oui --> E1{"Score Niveau 1 >= 20 ?"}
    E1 -- Non --> F1["Échec Niveau 1"]
    F1 --> G1{"Que veux-je faire ?"}
    G1 -- Recommencer Niveau 1 --> C1
    G1 -- Tout Recommencer --> B
    E1 -- Oui --> H1["Réussite Niveau 1"]
    H1 --> C2["Démarrage Niveau 2 Timer 40s"]
    C2 --> D2{"Temps écoulé ?"}
    D2 -- Oui --> E2{"Score Niveau 2 >= 40 ?"}
    E2 -- Non --> F2["Échec Niveau 2"]
    F2 --> G2{"Que veux-je faire ?"}
    G2 -- Recommencer Niveau 2 --> C2
    G2 -- Tout Recommencer --> B
    E2 -- Oui --> H2["Réussite Niveau 2"]
    H2 --> C3["Démarrage Niveau 3 Timer 20s"]
    C3 --> D3{"Temps écoulé ?"}
    D3 -- Oui --> E3{"Score Niveau 3 >= 60 ?"}
    E3 -- Non --> F3["Échec Niveau 3"]
    F3 --> G3{"Que veux-je faire ?"}
    G3 -- Recommencer Niveau 3 --> C3
    G3 -- Tout Recommencer --> B
    E3 -- Oui --> I["Réussite Finale"]
    I --> J["Le Panneau de Contrôle réapparaît"]
    J --> K["Affichage du Tableau Récapitulatif des Scores par Niveau"]
    K --> L{"Je veux rejouer entièrement ?"}
    L -- Oui --> B
    L -- Non --> M["Je quitte la page"]

    A@{ shape: rect}
    B@{ shape: rounded}
    style A color:#000000
    style C1 fill:#FFCDD2
    style D1 color:#000000,fill:#FFCDD2
    style E1 fill:#FFCDD2
    style F1 color:#000000,fill:#BBDEFB
    style G1 fill:#FFE0B2
    style H1 fill:#FFCDD2
    style C2 fill:#C8E6C9
    style D2 fill:#C8E6C9
    style E2 fill:#C8E6C9
    style F2 color:#000000,fill:#BBDEFB
    style G2 fill:#FFE0B2
    style H2 fill:#C8E6C9
    style C3 fill:#FFF9C4
    style D3 color:#000000,fill:#FFF9C4
    style E3 fill:#FFF9C4
    style F3 fill:#BBDEFB
    style G3 fill:#FFE0B2
    style I fill:#FFF9C4
    style J fill:#FFF9C4
    style K fill:#FFF9C4
    style L color:#000000,fill:#FFE0B2
    style M fill:transparent
```
