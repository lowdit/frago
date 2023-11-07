---
title: 'Configurer FRAGO'
weight: 3
---

Comprendre comment configurer FRAGO pour la génération de rapports de synthèse pour le suivi et l’amélioration de l’accessibilité web.


## Présentation

Le thème Frago a pour objectif d’aider à la génération de synthèses pour l’amélioration des démarches en ligne du gouvernement français..

> Attention, goHugo est très sensible à l’architecture des contenus. Si les contenus sont absents ou présentent des erreurs le site peut planter. Si l’architecture du thème change, de même, il n’est plus possible d’utiliser les dernières versions du thème (sans modifier l’architecture de contenu).

> Un maximum d’indications ont été ajoutés au code pour s’afficher dans la console (visible dans un terminal), si un cas mérite d’être signalé aller sur la page <https://github.com/lowdit/frago/issues>.

## Démarrage (Configuration simplifiée)

### Architecture de contenu

Exemple d'architecture d'un projet avec `goHugo`, voir : [L’exemple d’architecture sur Github](https://github.com/lowdit/frago/tree/master/exampleSite)

```
.
├── config.toml
└── content
    └── audits
         ├── projet1
         │     ├── index.md // Ajouter un entête avec le titre de la démarche
         │     └── accessibility ou rgaa
         │          ├── 2023-10-15.csv
         │          ├── 2023-11-15.csv
         │          └── context.yml // Déclarer le contexte de chaque audit
         └── projet2
                ├── index.md // Ajouter un entête avec le titre de la démarche
                └── accessibility ou rgaa
                    ├── 2023-10-15.csv
                    ├── 2023-10-15.csv
                    └── context.yml // Déclarer le contexte de chaque audit
```

Récupérer un exemple de structure de contenu : <https://github.com/lowdit/frago/tree/content>

### A. Installer le thème par téléchargement (plusieurs options)

Obtenir ce genre de structure de répertoire sur votre machine.

```
.
├── config.toml
├── content
│   └── audits
└── themes
    └── frago
```

#### 1. Télécharger le thème (pour un premier essai)

Télécharger le thème sur votre dépôt de contenu précédent dans `themes`: `themes/frago`.

Lien de la dernière version du thème au format `.zip` : <https://github.com/lowdit/frago/archive/refs/heads/master.zip>.

**Note :** Si vous le téléchargez, il ne sera pas synchronisé avec le dépôt GitHub, il faudra le mettre à jour à la main (en le re-téléchargeant). Pour le mettre à jour, supprimer, puis recréer le thème déjà initialement présent.

#### 2. Appeler le dépôt du thème Hugo avec `Git`

Option pour la synchronisation et mise à jour « automatiques ».

**Créer un répertoire themes**
```bash
mkdir themes // unix
```

**Accéder au répertoire themes**
```bash
cd themes
```

**Cloner le thème**
```bash
git clone https://github.com/lowdit/frago.git/
```

Le thème est présent dans le répertoire `themes/frago`. Vous pouvez le synchroniser avec `github` comme n'importe quel dépôt `.git`.


### Configuration

#### Ajouter le fichier : `config.toml`

```toml
baseURL = "/"
title = "Mon administration" # Ce qui s'affiche sur le site.
theme = "frago"

# Utilisés dans les documents légaux
[params]
  organisation = "Le nom complet de mon administration"
  [params.contacts]
    email = "referent-accessibilite@douane.finances.gouv.fr"
    address = "11, rue des deux Communes, 93558 Montreuil, cedex FRANCE"
```

### B. Installation et configuration (avec les Modules goHugo)

#### Appeler le thème Hugo pour synchronisation et mise à jour automatiques (avec le système de module `Go`)

⚠️ Le langage `Go` doit être installé sur le système d’exploitation. Installé sur `MacOS/Unix` ou `Linux`, mais difficile à installer sur `Windows` sans les droits administrateurs.

```toml
title = "Mon administration"

[module]
  [[module.imports]]
    path = "github.com/lowdit/frago"

# Utilisés dans les documents légaux
[params]
  organisation = "Le nom complet de mon administration"
  [params.contacts]
    email = "referent-accessibilite@douane.finances.gouv.fr"
    address = "11, rue des deux Communes, 93558 Montreuil, cedex FRANCE"
```

##### Créer le fichier `go.mod` (commande dans le terminal)

```bash
hugo mod init github.com/organisme/nomdepotgit
```

Vous pouvez mettre n’importe quoi comme nom de dépôt, c‘est juste une déclaration formelle pour déclarer le module à `Go`.

##### Créer le fichier `go.sum`  (commande dans le terminal)

```bash
hugo mod get github.com/lowdit/frago
```

C‘est l’adresse du dépôt Frago sur le site github.com.

##### Mettre à jour le thème le fichier `go.sum`  (commande dans le terminal)

```bash
hugo mod get -u
```

### Génération du site (mise en ligne)

Ligne de commande pour lancer le serveur en local sur votre machine

**Serveur local : mode auditeur**
```bash
hugo serve
```

Avec cette commande, la génération est en mode serveur. C'est à dire que les JSON de l’API ne sont pas générés (gain de performance).

**Serveur local : mode synthèse (pour tester en local l'environnement de production)**

```bash
HUGO_ENV="production" hugo serve --buildFuture --gc --minify
```

**Site généré : mode synthèse**

```bash
HUGO_ENV="production" hugo --buildFuture --gc --minify --cleanDestinationDir
```

**Site généré : mode portail (à venir)**
HUGO_ENV="portal" hugo --gc --minify --cleanDestinationDir

  * `HUGO_ENV="production"` lance l’environnement de production (sans les outils d’aide à l’audit, peut être lancé avec le mode serve).
  * `--buildFuture` Publier des éléments avec une date future. Ex: [phase](#phases) (optionnel) ou plan d’actions.
  * `--gc` met à jour le cache de goHugo à chaque re-génération.
  * `--cleanDestinationDir` nettoie le répertoire de génération du code (au cas où du code d’une précédente génération serait encore présent).
  * `--minify` permet ¨de compresser le code `HTML` en ligne.


