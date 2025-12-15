# VERSION 1 - testprojet1

Par rapport à la version 0 générée par l’IA (Gemini), cette version apporte principalement des améliorations esthétiques et fonctionnelles.

J’ai d’abord repris la base fournie par Gemini, puis j’ai effectué plusieurs modifications personnelles. J’ai ajouté **un effet sonore lors du clic sur les étoiles**, en utilisant un exemple existant de la bibliothèque **Tone.js** (le code « hello tone »).

Sur le plan visuel, j’ai modifié les **couleurs du fond**, en optant pour un bleu plus foncé, ainsi que celles **des étoiles**, désormais roses. J’ai également changé la **police d’écriture** pour Helvetica Neue, afin d’obtenir un rendu plus moderne et cohérent.

Enfin, j’ai demandé à **Gemini** d’ajouter de nouvelles fonctionnalités : un timer, un bouton Start (démarrer) et un bouton Restart (redémarrer). Après leur intégration, j’ai retravaillé leur style graphique (couleurs, encadrés) pour qu’ils correspondent à l’esthétique générale du projet.

## Diagramme de flux testprojet1

```mermaid
flowchart TB
    A@{ label: "J'arrive sur la page et je vois le bouton Démarrer'" } --> B@{ label: "Je clique sur 'Démarrer'" }
    B --> C@{ label: "L'écran de jeu s'active, le Timer 60s et les Étoiles commencent à apparaître" }
    C --> D{"Je vois une Étoile ?"}
    D -- Oui --> E@{ label: "J'arrive à cliquer dessus à temps ?" }
    E -- Oui --> F["Mon Score augmente"]
    E -- Non --> G@{ label: "L'étoile disparaît" }
    F --> H{"Le Timer est à 0s ?"}
    G --> H
    H -- Oui --> I["Fin du Jeu : Le temps est écoulé"]
    I --> J["Le score final apparait"]
    J --> K{"Je veux rejouer ?"}
    K -- Oui --> B
    K -- Non --> L["Je quitte la page"]

    A@{ shape: rect}
    B@{ shape: rounded}
    C@{ shape: rect}
    E@{ shape: diamond}
    G@{ shape: rect}
   ```
