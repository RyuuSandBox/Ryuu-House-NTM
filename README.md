# Les guides de Ryuu — AION 2

Un seul dépôt pour la page d'accueil et les trois guides. Site statique, aucun
build, aucune dépendance. On pousse, GitHub Pages sert.

## Ce que ça donne en ligne

| Adresse | Page |
|---|---|
| `/` | la page d'accueil |
| `/codex/` | le Codex d'Atreia |
| `/assassin/` | le guide Assassin |
| `/gladiator/` | le guide Gladiator |

## L'arborescence

```
.
├─ index.html          la page d'accueil
├─ art/                ses fonds et ses images  (fond1..3, carte, logo)
├─ Faction icons/      les blasons Elyos et Asmodien
├─ Symbole class/      les symboles de classe
│
├─ codex/index.html
├─ assassin/index.html
├─ assassin/icons/     les png de sorts du guide Assassin
├─ gladiator/index.html
├─ gladiator/icons/    les png de sorts du guide Gladiator
│
└─ .nojekyll           dit à GitHub de servir les fichiers tels quels
```

Chaque guide garde son dossier `icons/` **à côté de son `index.html`**. C'est ce
qui fait que les chemins d'images à l'intérieur des guides n'ont pas eu besoin
d'être retouchés.

## Ajouter un guide de classe

1. Créer un dossier à son nom, par exemple `ranger/`.
2. Y mettre `index.html` et son dossier `icons/`.
3. Dans `index.html` de la racine, ajouter l'entrée dans `GUIDES` et sa carte.

## Les liens sont relatifs

La page d'accueil pointe vers `codex/`, `assassin/`, `gladiator/`, sans nom de
domaine ni nom de dépôt. Le site marche donc tel quel qu'il soit servi sur
`ryuusandbox.github.io/Ryuu-House-for-us/` ou à la racine d'un domaine. Le jour
où le dépôt est renommé, ou où le site passe sur un autre hébergeur, il n'y a
rien à changer.

## Les anciens dépôts

Les trois dépôts d'avant (`codex-atreia-de-ryuu-for-us`,
`Assassin-guide-de-Ryuu-for-us`, `Gladiator-guide-de-Ryuu-for-us`) ne servent
plus à rien une fois ce dépôt en ligne. Les liens qui pointaient dessus ont été
retirés, ils peuvent être supprimés ou archivés.

## Les images

Chaque image est cherchée dans une liste de chemins, le premier trouvé gagne.
La page écrit dans la console du navigateur une ligne par image manquante, avec
tous les chemins essayés. En cas de doute, F12.

Attention à la casse, GitHub Pages distingue `art/` de `Art/`.
