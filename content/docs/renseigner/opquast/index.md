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
         │          ├── 2023-11-15.csv
         │          └── context.yml // Déclarer le contexte de chaque audit
         └── projet2
                ├── index.md // Ajouter un entête avec le titre de la démarche
                └── opquast
                    ├── 2023-10-15.csv
                    ├── 2023-10-15.csv
                    └── context.yml // Déclarer le contexte de chaque audit
```
