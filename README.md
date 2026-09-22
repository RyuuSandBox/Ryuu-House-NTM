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

## Le dossier est dans OneDrive

`C:\Users\rlope\OneDrive\Bureau\Workspace\`. Ça marche, mais deux outils
synchronisent le même dossier en même temps, et ils ne se parlent pas.

OneDrive recopie aussi le dossier caché `.git`, qui pèse déjà une vingtaine de
mégaoctets et change à chaque commit. Dans le pire des cas il verrouille un
fichier pendant que git écrit dedans, ou il pose une copie de conflit à côté.
Le `.gitignore` écarte les copies de conflit, mais il ne peut rien contre un
verrou.

Le jour où ça coince, la solution est de sortir le dossier de OneDrive, par
exemple dans `C:\Users\rlope\Projets\`, et de poser un raccourci sur le Bureau.
Il faudra alors reconnecter ce nouveau dossier à Claude pour que je continue à
écrire dedans.

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
