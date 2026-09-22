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
├─ art/                les fonds et les images  (fond, fond2, fond3, carte, logo,
│                      les blasons elyos et asmodien)
├─ Symbole class/      les symboles des huit classes
│
├─ codex/index.html
├─ assassin/index.html
├─ assassin/icons/     les png de sorts du guide Assassin
├─ gladiator/index.html
├─ gladiator/icons/    les png de sorts du guide Gladiator
│
├─ .nojekyll           dit à GitHub de servir les fichiers tels quels
├─ .gitignore          ce que git laisse sur le disque sans l'envoyer
└─ .gitattributes      les fins de ligne, pour éviter les faux changements
```

Chaque guide garde son dossier `icons/` **à côté de son `index.html`**. C'est ce
qui fait que les chemins d'images à l'intérieur des guides n'ont pas eu besoin
d'être retouchés.

## Le cycle de travail

Le dossier local et le dépôt GitHub sont la même chose, reliés par git. Trois
gestes, toujours les mêmes.

**Je modifie sur le PC.** Les fichiers changent dans le dossier. VS Code les
liste dans l'onglet *Source Control*, avec le détail ligne par ligne. On écrit
un message, on valide, on pousse. GitHub Pages reconstruit tout seul, il faut
compter une minute ou deux avant que le site change.

```
git add -A
git commit -m "ce que j'ai changé"
git push
```

**Je modifie sur github.com.** Le crayon sur un fichier, on édite, on valide en
bas de page. Le site se reconstruit pareil. Pour que le dossier du PC rattrape
la modification, une seule commande.

```
git pull
```

**Le réflexe qui évite les ennuis.** Toujours `git pull` avant de se mettre à
travailler sur le PC. Sans ça, une modification faite sur github.com et une
modification faite en local se retrouvent en conflit, et un conflit sur un
fichier de 285 000 octets n'est pas une partie de plaisir.

## Où vit le dépôt, et pourquoi pas ailleurs

`C:\Users\rlope\Projets\Ryuu-House-for-us`, en dehors de OneDrive, et c'est
volontaire.

Le dépôt a d'abord vécu dans `OneDrive\Bureau\Workspace`. Deux outils
synchronisaient le même dossier sans se parler. OneDrive recopiait aussi le
`.git`, une vingtaine de mégaoctets qui changent à chaque commit, et il lui
arrivait de restaurer une version qu'il avait en cache par-dessus un fichier
fraîchement écrit. Trois fichiers sont revenus en arrière tout seuls dans la
même journée. Rien n'a été perdu parce que tout était poussé sur GitHub, mais
c'est exactement le genre de panne qu'on ne voit pas passer.

Donc la règle, un dépôt git ne vit pas dans un dossier synchronisé. Ni OneDrive,
ni Dropbox, ni Google Drive. Si le dossier manque sur le Bureau, un raccourci
fait le travail sans rien synchroniser.

La sauvegarde, c'est GitHub. Un `git push` vaut mieux qu'un dossier recopié dans
le cloud, parce qu'il garde l'historique et qu'il ne se met jamais à écraser le
présent avec le passé.

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
plus à rien. Les liens qui pointaient dessus ont été retirés, ils peuvent être
supprimés ou archivés. Pareil pour les quatre anciens dossiers de `Workspace`,
`Codex Atreia`, `Guide Assassin`, `Guide Gladiator` et `Landing Page`, dont le
contenu est intégralement repris ici.

## Les images

Chaque image est cherchée dans une liste de chemins, le premier trouvé gagne.
La page écrit dans la console du navigateur une ligne par image manquante, avec
tous les chemins essayés. En cas de doute, F12.

Attention à la casse, GitHub Pages distingue `art/` de `Art/`.
