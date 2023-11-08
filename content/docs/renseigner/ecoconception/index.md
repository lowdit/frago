---
title: 'Audit d’Éco-conception'
weight: 3
summary: 'Renseigner un audit RGESN avec FRAGO'
---

Les audits de *conformité* sont présents dans le répertoire `content/audits/nomduservicenumerique/rgesn/`.


## Démarrage

### Architecture de contenu

```
.
├── config.toml
└── content
    └── audits
         ├── projet1
         │     ├── index.md // Ajouter un entête avec le titre de la démarche
         │     └── rgesn
         │          ├── 2023-10-15.csv
         │          └── 2023-11-15.csv
         └── projet2
                ├── index.md // Ajouter un entête avec le titre de la démarche
                └── rgesn
                    ├── 2023-10-15.csv
                    └── 2023-10-15.csv
```

### Tableau de grille de critères

| Thématiques | Critères | Évaluation |
| :---------: | :------: | :--------: |
|      1      |     1    |     nc     |
|      1      |     2    |      c     |
|      1      |     3    |     na     |
|      1      |     4    |     nt     |
|      …      |     …    |      …     |
|      8      |    12    |     nc     |

Accéder au fichier exemple de [Grille critères RGESN vierge](https://raw.githubusercontent.com/lowdit/frago/master/exampleSite/exampleFiles/grille-criteres-rgesn-1.0.csv)
