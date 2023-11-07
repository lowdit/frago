---
title: Arborescence
---

## Architecture simplifiée

Arborescence avec génération des pages d’audit auto-générées. L'utilisateur n’a pas besoin de créer une page pour chaque type d’audit et par projet.

```
.
├── config.toml
└── content
    ├── _index.md // page d’accueil du site :: ⚠️ Ajouter `type: projects` dans l'entête du fichier en cas de mono projet => va afficher directement la page de synthèse de tous les audits
    ├── audits // Type de contenu audits, les projets doivent être dans un répertoire avec le nom audits
    │     ├── projet1
    │     │    ├── index.md // ⚠️  Page intermédiaire qui liste les sous rapports (accessibilité, performance…)
    │     │    ├── accessibility
    │     │    │   ├── 2020-10-15.csv
    │     │    │   ├── 2020-11-15.csv
    │     │    │   └── context.yml // Déclarer le contexte ce chaque audit
    │     │    ├── lighthouse
    │     │    │   ├── 2020-10-15.json
    │     │    │   └── 2020-11-15.json
    │     │    └── recommendation
    │     │        ├── 2020-10-15.yml
    │     │        └── 2020-11-15.yml
    │     │
    │     └── projet2
    │          ├── index.md
    │          ├── accessibility
    │          │   ├── 2020-10-15.csv
    │          │   ├── 2020-11-15.csv
    │          │   └── context.yml // Déclarer le contexte ce chaque audit
    │          ├── lighthouse
    │          │   ├── 2020-10-15.json
    │          │   └── 2020-11-15.json
    │          └── recommendation
    │              ├── 2020-10-15.yml
    │              └── 2020-11-15.yml
    ┋
    ┋ ⚠️ Autre choix d’arborescence avec un seul projet ⚠️
    ┋
    └── audits // Les pages pour afficher les audits (accessibilité, qualité, performance…)
          ├── index.md
          ├── accessibility
          │   ├── 2020-10-15.csv
          │   └── 2020-11-15.csv
          │   └── context.yml // Déclarer le contexte ce chaque audit
          ├── lighthouse
          │   ├── 2020-10-15.json
          │   └── 2020-11-15.json
          └── recommendation
              ├── 2020-10-15.yml
              └── 2020-11-15.yml
```
