---
title: Personnalisation du thème
---

Hugo permet de surcharger les fichiers présents dans le thème, la condition est de respecter la même arborescence. Ainsi pour surcharger un thème avec :

 * Sa police
 * Son logo
 * Ses couleurs
 * …

Il suffit de créer tous ces fichiers dans le répertoire `static`. Le thème appelle automatiquement les polices contenues dans le répertoire `static/assets/fonts` (à la place de la police Marianne).

```
static
└── assets
    ├── css
    │   ├── fonts.css
    │   └── main.css
    ├── favicons
    │   ├── android-chrome-192x192.png
    │   ├── android-chrome-512x512.png
    │   ├── apple-touch-icon.png
    │   ├── favicon-16x16.png
    │   ├── favicon-32x32.png
    │   ├── favicon.ico
    │   └── site.webmanifest
    ├── fonts
    │   ├── open-sans-bold.woff2
    │   └── open-sans-regular.woff2
    └── images
        ├── logo.svg
        └── logodark.svg
```

## Arborescence

### Architecture simplifiée

```
.
├── config.toml
└── content
    ├── _index.md // page d’accueil du site
    └── audits // Type de contenu audits, les projets doivent être dans un répertoire avec le nom audits
          ├── projet1
          │    ├── index.md // ⚠️  Page intermédiaire qui liste les sous rapports (accessibilité, performance…)
          │    ├── accessibility
          │    │   ├── 2020-10-15.csv
          │    │   ├── 2020-11-15.csv
          │    │   └── context.yml // Déclarer le contexte ce chaque audit
          │    ├── lighthouse
          │    │   ├── 2020-10-15.json
          │    │   └── 2020-11-15.json
          │    └── recommendation
          │        ├── 2020-10-15.yml
          │        └── 2020-11-15.yml
          │
          └── projet2
               ├── index.md
               ├── accessibility
               │   ├── 2020-10-15.csv
               │   ├── 2020-11-15.csv
               │   └── context.yml // Déclarer le contexte ce chaque audit
               ├── lighthouse
               │   ├── 2020-10-15.json
               │   └── 2020-11-15.json
               └── recommendation
                   ├── 2020-10-15.yml
                   └── 2020-11-15.yml
```

### Architecture complète

```txt
.
├── config.toml
├── content
│   ├── _index.md // page d’accueil du site :: ⚠️ Ajouter `type: projects` dans l’entête du fichier en cas de mono projet => va afficher directement la page de synthèse de tous les audits
│   ├── audits // Les pages pour afficher les audits (accessibilité, recommandation, performance…) pour chaque projet
│   │    ├── projet1 // Doit reprendre le nom du répertoire donné au projet dans `static`
│   │    │     └── index.md // ⚠️  pour avoir lister les pages sur l’accueil et avoir la page intermédiaire qui liste tous les rapports
│   │    └── projet2 // Doit reprendre le nom du répertoire donné au projet dans `static`
│   │          └── index.md
│   ├── meetings
│   │    ├── _index.md // liste les réunions
│   │    └── 2020-10-22-reunion1.md // On indique la date dans le nom de fichier pour ranger les fichiers visuellement, il faut la répéter dans l’entête YML du fichier pour afficher les réunions sur la page dans un ordre par date.
│   └── personas // ⚠️ Ne fonctionne pas en mono projet
│        ├── _index.md // Liste tous les personas
│        ├── simon.md
│        ├── annie.md
│        └── projet1
│             ├── _index.md // liste tous les personas
│             ├── simon.md
│             └── annie.md
└── static
    ┋
    ├── usertests // Ne fonctionne pas en mono projet
    │    ├── test1.json
    │    └── test2.json
    ├── directory.json // Annuaire de contacts
    └── images
         ├── projet1 // Doit reprendre le nom du répertoire donné au projet dans `static`
         │    ├── benchmark
         │    │    ├── titresiteweb-titreelementacomparer.png // nommage précis disponible sur la page rapport générée par Hugo
         │    │    ├── ojdcourtsepay.tylerhost.net-navigation-step.png
         │    │    ├── pages.fivepointpayments.com-navigation-step.png
         │    │    └── finepayment.saskatchewan.ca-navigation-step.png
         │    └── recommendation
         │         └── 2020-10-16 // Les titres formant les noms d’images doivent correspondre à des termes existant dans le fichier `.yml`
         │             ├── titrepage-[before ou after].png
         │             ├── titrepage-titrebloc-titreerreur-[before ou after].png
         │             ├── accueil-before.png
         │             ├── accueil-after.png
         │             ├── accueil-banniere-titres-before.png
         │             └── accueil-banniere-titres-after.png
         ├── projet2
         └── personas

```
