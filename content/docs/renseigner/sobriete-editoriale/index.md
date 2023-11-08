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
         │          ├── 2023-11-15.csv
         │          └── context.yml // Déclarer le contexte de chaque audit
         └── projet2
                ├── index.md // Ajouter un entête avec le titre de la démarche
                └── publishing
                    ├── 2023-10-15.csv
                    ├── 2023-10-15.csv
                    └── context.yml // Déclarer le contexte de chaque audit
```
