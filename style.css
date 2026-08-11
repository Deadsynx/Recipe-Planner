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
