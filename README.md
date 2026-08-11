# Recipe Planner PWA V0.1

Première PWA testable de Recipe Planner.

Fonctions : filtres, recette unique, Extra exclusif, agenda, liste de courses par catégories avec cases à cocher, ajout manuel, IndexedDB, ajout de recettes, export/import JSON et Service Worker hors ligne.

## Test sur Windows

Dans le dossier `V0.1`, ouvrir PowerShell puis :

```bash
python -m http.server 8000
```

Ouvrir ensuite :

```text
http://localhost:8000
```

Ne pas ouvrir `index.html` directement avec `file://`.

Pour l'iPad, on fera ensuite l'hébergement HTTPS afin de pouvoir l'ajouter proprement à l'écran d'accueil.

## V0.2 — Mise à jour de la base

Ajout du bouton `Mettre à jour les recettes` dans l'onglet Données.

Il :
- télécharge la dernière version de `data/recettes.json` ;
- contourne le cache lors de cette vérification ;
- ajoute les nouvelles recettes ;
- met à jour celles qui possèdent déjà le même `id` ;
- conserve les recettes créées manuellement si leur `id` n'existe pas sur le serveur ;
- ne touche ni à l'agenda, ni aux Extras, ni à la liste de courses.

Cette archive inclut également la base actuelle convertie depuis les fichiers TXT reçus.


## V0.2.1 — Correction des mises à jour PWA

- Supprime automatiquement les anciens caches `recipe-planner-*`.
- `skipWaiting()` active immédiatement le nouveau Service Worker.
- `clients.claim()` lui donne immédiatement le contrôle des pages ouvertes.
- Le navigateur tente d'abord le réseau puis utilise le cache hors ligne.
- Lorsqu'un nouveau Service Worker prend le contrôle, la page se recharge une fois.
- La version `V0.2.1` est affichée sous le titre pour vérifier immédiatement que le déploiement GitHub est bien celui attendu.


## V0.2.2 — Origines synchronisées avec la base

Le menu `Origine` est entièrement construit à partir des recettes réellement présentes.

Lors de `Mettre à jour les recettes` :
- le JSON serveur devient la source officielle des recettes serveur ;
- les nouvelles recettes sont ajoutées ;
- les recettes existantes sont mises à jour ;
- les recettes serveur supprimées du JSON disparaissent aussi localement ;
- les recettes ajoutées manuellement sont conservées ;
- le menu Origine est reconstruit immédiatement.

Ainsi, une origine absente de la base officielle disparaît du menu après synchronisation.
