---
title: 'Renseigner des recommandations'
weight: 4
summary: 'Renseigner des préconisations et les affecter à des lots de correction'
---

Affiche les données du fichier plus récent dans `content/audits/nomdelademarche/recommendation/YYYY-MM-JJ.yml`.

Le fichier de recommandation est fastidieux à remplir, mais permet de suivre des corrections de manière sereine avec une synthèse disponible sous format `HTML` et plus facilement que dans un `.doc`.

## Exemple de fichier

```yaml
- pages:
  - name: Global au site
    blocks:
    - name: Gabarit
      errors:
      - name: Adresse de navigation # Titre de l’erreur
        description: L’adresse de navigation ne change pas en fonction des pages.
      - name: Code invalide
        description: "Le code comporte des erreurs quand on passe le validateur : https://validator.w3.org/." # Description longue
        criterion: 8.2, 8.4 # Critères RGAA concernées :: si erreur lié à un critère, l'erreur sera reporté dans la déclaration générée
        status: moindre # Criticité : critique, important, moindre
        delivery: lot 1 # Possibilité de regrouper des erreurs dans les lots en haut de page (l'intitulé du champ est libre)
      - name: Titre invalide
        description: Les titres (`<title>`) de page ne changent pas en fonction des pages et ne sont pas pertinents.
        criterion: 4.1, 8.6
        delivery: lot 1 # Lot 1
      - name: Hiérarchie des titres
        description: Il n’existe parfois aucun titre dans les pages. Passer certains titres (haut de page)`<h3>` en `<h1>` ou ajouter des `<h1>` à toutes les pages.
        criterion: 9.1
        status: important # Criticité : critique, important, moindre
        delivery: lot 2 # Lot 2
    - name: Saisie de la déclaration # Nom de la page
      errors:
      - name: Label
        path: /html/body/div[2]/div[2]/div/div/div/div/div/div[3]/table/tbody[1]/tr/td[3]/div/input
        description: Certains champs `input` n’ont pas de `label`.
      - name: Label + Input liés
        path: /html/body/div[2]/div[2]/div/div/div/div/div/div[5]/div/div/div/div/div[2]/div[6]/label # Xpath
        description: Aucun champs `input` n'est relié avec son `label` avec une attribut `for`.
        delivery: lot 3 # Lot 3
        status: critique # Criticité : critique, important, moindre
        criterion: 11.1
        checked: true # Si l'erreur est corrigée
        codebefore: |- # Code présent sur le site audité
          <div class="form-group">
            <label class="col-md-2 control-label">Année (AAAA) </label>
            <div class="col-lg-1 col-md-2"><input type="text" class="form-control"></div>
          </div>
        codeafter: |- # Proposition de code pour que le critère soit conforme
          <div class="form-group">
            <label class="col-md-2 control-label" for="year">Année (AAAA) </label>
            <div class="col-lg-1 col-md-2"><input type="text" class="form-control" id="year"></div>
          </div>
```

![Qualité](/frago/images/qualite.png)

## Captures d’écran

Chaque erreur peut être enrichie d'une capture d’écran du site audité. Ces images doivent être
déposées dans le dossier `static/images/${slug_projet}/recommendation/${date_audit}/` où ${slug_projet}
réfère au nom du dossier dans lequel sont archivées les feuilles d’audit et ${date_audit}, au nom
du fichier d’audit (sous forme de date yyyy-mm-dd).

Afin de lier chaque capture d'écran à l’erreur, un nom d'image est généré automatiquement pour chaque
erreur. Ce nom est affiché à côté de l’erreur lorsque le site est en cours d’élaboration (`hugo serve`).

![Exemple de nom d'image généré automatiquement](/frago/images/nom-capture-recommandation.png)
