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
    path: /audits/**/index.md
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
    path: /audits/**/_index.md
  outputs:
    - html
    - json
    - declaration
    - declarationpage
    - declarationeco
    - declarationecopage
- _target:
    path: /audits/_index.md
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
    path: /audits/index.md
  type: "audits"
- _target:
    path: /organism/**/_index.md
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
