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
