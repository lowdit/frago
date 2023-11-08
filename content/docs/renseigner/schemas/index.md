---
title: 'Schéma pluri-annuel'
summary: 'Intégrer un schéma pluriannuel à pour un organisme'
---

⚠️  La possibilité de générer un schéma pluriannuel est en chantier. Si vous avez un besoin sur ce sujet, une simple demande pourra permettre d’engager des évolutions. ⚠️

La raison est que ce schéma pluri-annuel est le document propre à chaque organisme, il est sensé être très personnel. De plus certaines données à afficher ne proviennent pas directement des données par services.

## Architecture

```
.
├── config.toml
└── content
    ├── audits
    │   ├── projet1
    │   │     ├── index.md // Ajouter un entête avec le titre de la démarche
    │   │     └── accessibility
    │   │          ├── 2020-10-15.csv
    │   │          ├── 2020-11-15.csv
    │   │          └── context.yml // Déclarer le contexte de chaque audit
    │   └── projet2
    │          ├── index.md // Ajouter un entête avec le titre de la démarche
    │          └── accessibility
    │              ├── 2020-10-15.csv
    │              ├── 2020-10-15.csv
    │              └── context.yml // Déclarer le contexte de chaque audit
    ├── plans
    │   ├── 2023.md
    │   ├── 2024.md
    │   └── actions
    │       ├── 2023-01-15.csv
    │       └── 2024-02-10.csv
    └── schemas
        ├── 2021-2023.md // Page du plan d’action 2021-2023, le nom du fichier doit comporter les 2 années de début et fin
        └── 2024-2026.md
```

## En-tête de fichiers

Une passe doit être faites sur ce type de contenu pour voir comment sont gérées les données. Les données qui y figurent, peuvent être récupérées directement des projets : organisation, contacts, nombre de services audités… mais pas le nombre d’application, ni le nombre de personnes dans une équipe.

L’idée est que les données qu’on peut récupérer sont affichées, mais si elles sont incorrectes on peut les surcharger dans le fichier.

Pour le moment, les audits ne sont pas typés : pas de différences entre une borne interactive, une application ou un site web. Donc, on ne peut pas compter pour le moment.

```yml
---
organisation: Mon organisation
contacts:
  email: referent-accessibilite@organisme.finances.gouv.fr
  address: 11, rue des deux Communes, 93558 Montreuil, cedex FRANCE
services:
  website:
    number: 12
  application:
    number: 20
team:
  number: 18
---
```

## Résultat

Pour le moment, le schéma généré est indicatif car il se sert d’un modèle lambda avec, insérées automatiquement, les données nécessaires.

Cependant, cela reste très pratique, car il va lister :

 * L’ensemble des démarches
 * Les plans d’actions correspondants à l’interval d’années du schéma.

Ce schéma devrait être édité à partir de la rédaction de plusieurs paragraphes et l‘insertion de `shortcode`.

## Site portail

La publication d’un site portail a été développée. Un site portail est un site qui n’affiche que les documents légaux : schéma, plans et déclarations.

Ce mode de rendu se fait avec le même dépôt de contenu mais avec une configuration différente. Ce développement n'est pas encore terminé, notamment pour avoir un processus simple de mise en place.
