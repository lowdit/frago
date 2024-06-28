---
title: Accueil Audits
outputs:
  - html
  - json
disableKinds:
  - RSS
  - taxonomy
  - taxonomyTerm
cascade:
- _target:
    type: organism
    path: /organism
  outputs:
    - html
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
- _target:
    path: /audits/*
    type: audits
  outputs:
    - html
    - json
    - declaration
    - declarationpage
    - declarationeco
    - declarationecopage
    - accessibility
    - raweb
    - ecoconception
    - opquast
    - publishing
    - recommendation
    - performance
    - accessibilitypage
    - rawebpage
    - ecoindexpage
    - ecoconceptionpage
    - opquastpage
    - publishingpage
    - recommendationpage
    - performancepage
- _target:
    path: /audits/*/*/
    type: audits
  outputs:
    - html
    - json
    - declaration
    - declarationpage
    - declarationeco
    - declarationecopage
---
