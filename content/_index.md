---
title: Accueil Audits
outputs:
  - html
  - json
disableKinds:
  - RSS
  - taxonomy
  - taxonomyTerm
  - accessibility
cascade:
- _target:
    path: /audits/**/
  outputs:
    - html
    - json
    - declaration
    - declarationpage
    - declarationeco
    - declarationecopage
    - accessibility
    - ecoconception
    - opquast
    - publishing
    - quality
    - recommendation
    - performance
    - accessibilitypage
    - rawebpage
    - ecoindexpage
    - ecoconceptionpage
    - opquastpage
    - publishingpage
    - qualitypage
    - recommendationpage
    - performancepage
- _target:
    path: /audits/**/
  outputs:
    - html
    - json
    - declaration
    - declarationpage
    - declarationeco
    - declarationecopage
- _target:
    path: /audits/**
  outputs:
    - html
    - json
    - declaration
    - declarationpage
    - declarationeco
    - declarationecopage
    - accessibility
    - raweb
    - ecoindex
    - ecoconception
    - opquast
    - publishing
    - quality
    - recommendation
    - performance
    - accessibilitypage
    - rawebpage
    - ecoindexpage
    - ecoconceptionpage
    - opquastpage
    - publishingpage
    - qualitypage
    - recommendationpage
    - performancepage
- _target:
    path: /audits/
  type: "audits"
- _target:
    path: /organism/**
    kind: section
  outputs:
    - html
    - json
    - accessibilitypage
    - rawebpage
    - ecoindexpage
    - ecoconceptionpage
    - opquastpage
    - publishingpage
    - greenit
    - greenitpage
    - cigref
    - cigrefpage
---
