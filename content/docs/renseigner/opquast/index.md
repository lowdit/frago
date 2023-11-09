---
title: 'Audit Opquast'
weight: 3
summary: 'Renseigner un audit Opquast avec FRAGO'
---

Les audits de *conformité* sont présents dans le répertoire `content/audits/nomduservicenumerique/opquast/`.

## Démarrage

### Architecture de contenu

```
.
├── config.toml
└── content
    └── audits
         ├── projet1
         │     ├── index.md // Ajouter un entête avec le titre de la démarche
         │     └── opquast
         │          ├── 2023-10-15.csv
         │          └── 2023-11-15.csv
         └── projet2
                ├── index.md // Ajouter un entête avec le titre de la démarche
                └── opquast
                    ├── 2023-10-15.csv
                    └── 2023-10-15.csv
```

### Tableau de grille de critères

| Règles | Évaluation |
| :----: | :--------: |
|    3   |      C     |
|    7   |     NC     |
|   15   |      C     |
|   16   |     NA     |
|    …   |      …     |
|   105  |      C     |

Accéder au fichier exemple de [Grille critères Opquast vierge](https://raw.githubusercontent.com/lowdit/frago/master/exampleSite/exampleFiles/grille-criteres-opquast-1.0.csv)

Accéder à un exemple de [Synthèse Opquast](https://frago-sandbox.netlify.app/audits/contributions-indirectes-en-ligne/recommendation)
