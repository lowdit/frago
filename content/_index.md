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
    - declarationeco
- _target:
    path: /audits/**
  outputs:
    - html
    - json
    - declaration
    - declarationeco
    - accessibility
    - ecoindex
    - ecoconception
    - opquast
    - publishing
    - recommendation
    - performance
- _target:
    path: /audits/
  type: "audits"
- _target:
    path: /organism/
    kind: section
  outputs:
    - html
    - json
    - greenit
    - cigref
---
