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
    - ecoconception
    - opquast
    - publishing
    - quality
    - recommendation
    - performance
    - accessibilitypage
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
    - ecoconceptionpage
    - opquastpage
    - publishingpage
    - greenit
    - greenitpage
    - cigref
    - cigrefpage
---
