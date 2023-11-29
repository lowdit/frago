---
title: 'Audit d’accessibilité'
weight: 3
summary: 'Renseigner un audit d’accessibilité avec FRAGO'
---

Les audits de *conformité* sont présents dans le répertoire `content/audits/nomduservicenumerique/accessibility/`.

L’audit d’*accompagnement* a pour but de lister tous les types d’erreurs afin de faire un suivi des éléments à corriger avec une équipe de développement. Il sera présent dans le répertoire `content/audits/nomduservicenumerique/recommendation/`.

#### Accessibilité

Éditer : `content/audits/nomduservicenumerique/accessibility/YYYY-MM-JJ.csv`

L'audit accessibilité est généré à partir d‘un `.csv` (fichier à plat). Les données relatives au test (optionnelles) peuvent être indiquées dans le fichier `content/audits/nomduservicenumerique/accessibility/context.yml`.

```yaml
website: "amendes.gouv.fr"
contacts:
    email: stap-amendes@dgfip.finances.gouv.fr
    address : 139 rue de Bercy, 75572 Paris, Cedex 12
audits:
    2021-03-05: # ⚠️ bien respecter la date de chaque fichier csv d’audit déjà présent dans `content/audits/nomduservicenumerique/accessibility/`
      guidelines: "RGAA 4.1.2"
      condition: "Auto-évaluation"
      technologies: ["HTML", "CSS", "JS", "PDF"]
      tools: ["Wave", "AXE", "Web Developper","Usability Hike","Heading Maps"]
      environment:
        - OS: Windows 11
          screenreader: NVDA (dernière version)
          browser: Firefox
          type: desktop
        - OS: "MacOS"
          screenreader: VoiceOver (dernière version)
          browser: Safari
          type: desktop
        - OS: "Androïd natif"
          screenreader: TalkBack (dernière version)
          browser: Chrome
          type: mobile
        - OS: "iOS"
          screenreader: VoiceOver (dernière version)
          browser: Safari
    2020-10-12:
      guidelines: "RGAA 4.0"
      condition: "Auto-évaluation"
      technologies: ["HTML", "CSS", "JS", "PDF"]
      tools: ["Wave", "AXE", "Web Developper","Usability Hike","Heading Maps"]
      environment: ["MacOS", "Firefox", "Chrome", "ChromeVox"]
```
