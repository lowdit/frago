---
title: 'Audit Sobriété Éditoriale'
weight: 4
summary: 'Renseigner un audit éditorial avec FRAGO'
---

Les audits de *conformité* sont présents dans le répertoire `content/audits/nomduservicenumerique/publishing/`.


## Démarrage

### Architecture de contenu

```
.
├── config.toml
└── content
    └── audits
         ├── projet1
         │     ├── index.md // Ajouter un entête avec le titre de la démarche
         │     └── publishing
         │          ├── 2023-10-15.csv
         │          └── 2023-11-15.csv
         └── projet2
                ├── index.md // Ajouter un entête avec le titre de la démarche
                └── publishing
                    ├── 2023-10-15.csv
                    └── 2023-10-15.csv
```

### Tableau de grille de critères

| Thématiques | Cyclop | GreenITfr | Evaluation |
| :---------: | :----: | :-------: | :--------: |
|      1      |    9   |    5101   |     NC     |
|      1      |   10   |    5102   |      C     |
|      1      |   11   |    5103   |     NC     |
|      1      |   12   |    5104   |      C     |
|      1      |   34   |    5105   |     NA     |
|      …      |    …   |     …     |      …     |
|      8      |   50   |    5806   |     NA     |

Accéder au fichier exemple de [Grille critères Sobriété Éditoriale vierge](https://raw.githubusercontent.com/lowdit/frago/master/exampleSite/exampleFiles/grille-criteres-edito-1.0.csv).
