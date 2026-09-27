# Forge à titres

Générateur de titres en blocs, dans le style des logos d'événements Minecraft (lettres épaisses, liseré clair, dessous en 3D, gros contour noir).

Tu tapes ton texte, le logo se dessine tout seul, et tu le télécharges en PNG avec un fond transparent.

## Utilisation

Ouvre `index.html` dans un navigateur, ou utilise la version en ligne (voir plus bas).

- **Texte** : jusqu'à 3 lignes. Lettres A–Z, chiffres, espaces et `! ? . - : ' + / ( )`. Les accents sont retirés automatiquement.
- **Matière** : Pierre, Or, Diamant, Émeraude, Redstone, Bois, Améthyste, Neige, ou une couleur perso.
- **Réglages** : largeur de l'image, profondeur 3D, inclinaison, épaisseur du contour, espace entre les lettres.
- **Télécharger le PNG** ou **Copier l'image**.

## Mettre le site en ligne avec GitHub Pages

1. Crée un dépôt sur GitHub et envoie-y `index.html` et `README.md`.
2. Dans le dépôt : **Settings → Pages**.
3. Dans **Source**, choisis **Deploy from a branch**, puis la branche `main` et le dossier `/ (root)`, et clique sur **Save**.
4. Après une minute, le site est disponible à l'adresse `https://<ton-pseudo>.github.io/<nom-du-depot>/`.

## Comment ça marche

Tout tient dans `index.html`, sans dépendance ni installation :

- Chaque lettre est définie comme une petite grille de blocs (`#` = plein, `.` = vide), dans l'objet `G` du script. Certaines lettres ont des largeurs de colonnes et des hauteurs de lignes sur mesure (`cols`, `rowH`) pour coller aux logos d'origine.
- Le rendu se fait sur un `<canvas>` : face avant en dégradé, liseré clair, dessous en 3D sous le bas des lettres, puis contour noir obtenu en élargissant la silhouette.

### Modifier une lettre

Dans `index.html`, cherche la ligne de la lettre dans `const G = {...}`. Exemple pour le N :

```js
N:{rows:["#..#","##.#","####","#.##","#..#"],cols:[1.8,0.6,0.6,1.85],rowH:[0.95,1,0.5,1.05,1.5]},
```

- `rows` : les lignes de haut en bas.
- `cols` : la largeur de chaque colonne (facultatif).
- `rowH` : la hauteur de chaque ligne, le total doit faire 5 (facultatif).

## Crédits

Les formes des lettres sont redessinées à la main pour imiter le style du logo Minecraft. Aucun fichier de police n'est inclus. Projet non officiel, sans lien avec Mojang ou Microsoft.
