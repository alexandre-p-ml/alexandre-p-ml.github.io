# Portfolio MVA — site Quarto

Squelette de site web pour présenter des projets ML/maths avec téléchargements
de notebooks et PDF.

## Structure

```
.
├── _quarto.yml           # config + navbar
├── styles.css            # retouches CSS
├── index.qmd             # page d'accueil
├── projets/              # une page par projet
│   ├── 3dgs.qmd
│   ├── prior-networks.qmd
│   ├── raidium.qmd
│   └── parkinson.qmd
├── files/                # PDF et .ipynb téléchargeables (à remplir)
└── img/                  # images embarquées dans les pages (à remplir)
```

## Prérequis

Installer Quarto : <https://quarto.org/docs/get-started/>

```bash
quarto --version   # vérifier
```

## Prévisualiser en local

```bash
quarto preview
```

Ouvre le site sur `http://localhost:xxxx` avec auto-reload.

## Build statique

```bash
quarto render
```

Produit le site dans `_site/`.

## Déployer sur GitHub Pages

Une fois le repo poussé sur GitHub :

```bash
quarto publish gh-pages
```

Cette commande crée/met à jour la branche `gh-pages` et active GitHub Pages.
URL finale : `https://<ton-username>.github.io/<nom-du-repo>/`.

Pour un déploiement automatique à chaque push, ajouter un workflow
`.github/workflows/publish.yml` (voir doc Quarto).

## Personnaliser

- **Ajouter un projet** : créer `projets/mon-projet.qmd`, ajouter une entrée
  dans le menu `_quarto.yml`, et une carte sur `index.qmd`.
- **Rendre un notebook directement comme page** : référencer le `.ipynb`
  dans la navbar (`href: projets/mon-notebook.ipynb`) ; Quarto le rendra
  comme une page HTML avec code + sorties.
- **Bouton "download .ipynb" en haut de la page** : déjà activé via
  `code-tools: true` dans le YAML.
- **Thème** : changer `theme: cosmo` dans `_quarto.yml`. Liste complète :
  <https://quarto.org/docs/output-formats/html-themes.html>.

## Ce qu'il reste à faire

1. Remplir `files/` avec tes vrais PDF et notebooks.
2. Mettre des vraies images dans `img/`.
3. Mettre à jour le contact et l'URL GitHub dans `_quarto.yml` et `index.qmd`.
