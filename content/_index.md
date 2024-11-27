---
title: Accueil Audits
outputs:
  _merge: deep
outputs:
  - html
  - json
disableKinds:
  - RSS
  - taxonomy
  - taxonomyTerm
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
    - ecoindex
    - ecoconception
    - opquast
    - publishing
    - quality
    - recommendation
    - performance
    - accessibilitypage
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
    path: /organism/
    kind: section
  outputs:
    - html
    - json
    - accessibilitypage
    - ecoindexpage
    - ecoconceptionpage
    - opquastpage
    - publishingpage
    - greenit
    - greenitpage
    - cigref
    - cigrefpage
---