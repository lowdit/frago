---
title: 'Installer Hugo'
weight: 1
---

Comprendre comment installer goHugo sur sa machine ou le configurer sur un système de déploiement automatisé (site en ligne).
⚠️ Nécessite de savoir ouvrir un terminal, un petit peu de manip, mais une fois réalisé, on a l’impression d’être un DEV 😁.

> Hugo est un exécutable qui fonctionne sur tous les systèmes d’exploitation. Il ne dépend d’aucune autre technologie à installer au préalable (à part les systèmes de gestions d’installation type : `Brew`, `Chocolatey`, `pkg`). Il est sensé fonctionner sur toutes les machines existantes.

## Utiliser le Terminal

Utiliser `Frago` demande de savoir lancer une commande dans le terminal. Le terminal est une fenêtre (sur votre machine) avec laquelle on communique avec sa machine (en mode texte) ; on lance des commandes à la machine.

Pour utiliser `goHugo`, il faut :

  1. Ouvrir un terminal ;
  1. Installer goHugo, ex : `brew install hugo` ;
  1. Aller dans le répertoire où `goHugo` est installé ;
  1. Lancer la commande `Hugo`, ex : `Hugo serve` ;
  1. Ouvrir l’url de test (copier/coller l’url donnée par le terminal, vers la barre d’adresse de son navigateur).

⚠️ Il est possible d’utiliser le terminal à partir d’un éditeur de code (ex. [https://vscodium.com/](https://vscodium.com/)). C'est très pratique, car la commande sera lancée dans le bon répertoire de travail. Celui dans lequel vous allez éditer les fichiers pour `Frago`.

Pour cela, il faut ouvrir son éditeur ; ouvrir le répertoire de travail ; lancer le terminal à partir de l'éditeur (disponible dans la barre de menu supérieure) ; lancer la commande `hugo serve`.




### MacOs

* [Premiers pas avec Terminal sur Mac](https://support.apple.com/fr-fr/guide/terminal/pht23b129fed/2.14/mac/14.0)

### Linux

 * [Comment ouvrir un terminal ?](https://doc.ubuntu-fr.org/terminal)
 * [Le terminal Linux pour débutants](https://www.jetestelinux.com/le-terminal-linux-pour-debutants)

### Windows

 * [Installer Hugo sur windows](/frago/docs/demarrer/installer-hugo-windows/)

## Installer & Mettre à jour

### Installer goHugo

 * <https://gohugo.io/getting-started/installing/>
 * <https://learn.netlify.app/fr/basics/installation/>
 * [Howto: Install Hugo on Windows](https://discourse.gohugo.io/t/howto-install-hugo-on-windows/741)

#### Installer Homebrew (MacOs et Linux)

À copier dans votre terminal.

```bash
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Lien vers le système de gestion de paquets (logiciel de gestion de paquets et applications) : [https://brew.sh/](https://brew.sh/).

#### Exemple le plus courant d’installation avec `Brew`

```bash
$ brew install hugo
```

#### Exemple le plus courant de mise à jour avec `Brew`

```bash
brew upgrade hugo
```

## Héberger

#### Héberger avec `Github`

Consulter la page [Host on GitHub](https://gohugo.io/hosting-and-deployment/hosting-on-github/) pour plus d’informations.

Github utilise son système interne GitHub Action. Un exemple de fichier de configuration est disponible : [gh-pages.yml](https://github.com/lowdit/frago/blob/master/exampleSite/exampleFiles/.github/workflows/gh-pages.yml).

#### Héberger avec `Gitlab`

Consulter la page [Host on Gitlab](https://gohugo.io/hosting-and-deployment/hosting-on-gitlab/) pour plus d’informations.

Github utilise son système interne Gitlab CI. Un exemple de fichier de configuration est disponible : [.gitlab-ci.yml](https://github.com/lowdit/frago/blob/master/exampleSite/exampleFiles/.gitlab-ci.yml).

#### Héberger sans `GO`

Il est possible que votre plateforme de génération ne supporte pas Go (ou une version de goHugo `non « extended »`). Dans ce cas, il faut télécharger le thème juste avant de construire le site (build Hugo). On utilisera par example une commande `git`.

Vous pouvez ajouter le répertoire `themes` à votre `.gitignore` pour ne pas le pousser dans votre dépôt `.git` de contenu (celui de vos données Frago).

Au moment de la génération en `production`, vous appelez le thème grâce à un submodule `Git` (ce sera fait à chaque génération). Attention : il appellera la dernière version du thème.

```bash
git submodule add -f https://github.com/lowdit/frago.git/ themes/frago && git submodule update --init --recursive && hugo --gc --minify --buildFuture
```
