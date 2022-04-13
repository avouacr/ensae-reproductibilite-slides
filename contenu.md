# Qui sommes-nous ?

- Des data scientists de l'Insee
    - obsédés par la notion de **reproductibilité**
    - frustrés par l'approche souvent purement technique de la data science
    - convaincus que les **bonnes pratiques** valent à être enseignées

<romain.avouac@insee.fr>, <lino.galiana@insee.fr>

---

# Introduction

----

### Disclaimers

- Contenu en construction : 

https://hungry-hodgkin-0a5a81.netlify.app

- Programme large

- Applications guidées

----

### Vue d'ensemble

- **Public visé** : praticiens de la data science

- **But** : répondre à des sujets pratiques
    - travail collaboratif
    - partage de code
    - mise en production
    - valoriser un modèle de data science
    - automatiser et industrialiser

- **Horizon** : un rôle d'interface entre le métier et la technique

----

### La notion de bonnes pratiques

- **Origine** : communauté des développeurs logiciels

- **Constats** :
    - le code est plus souvent lu qu'écrit
    - la maintenance d'un code est très coûteuse

- **Conséquence** : ensemble de **règles informelles**, conventionnellement acceptées comme produisant des logiciels **fiables**, **évolutifs** et **maintenables**

----

### Pourquoi s'intéresser aux bonnes pratiques ?

- L'activité du data scientist tent à se rapprocher de celle du développeur :
    - projets intenses en code
    - **projets collaboratifs** et de grande envergure
    - **complexification** des données et donc des **infrastructures**
    - **déploiement** d'applications pour valoriser les analyses

----

### Bonnes pratiques et reproductibilité

![](img/reprospectrum.png)

**Source** : Peng R., Reproducible Research in Computational Science, Science (2011)

----

### Contenu du cours

- Voir le code comme un **outil de communication**
    - Structure des projets et qualité du code
    - Contrôle de version avec Git

- **Travail collaboratif** avec Git et GitHub

- Maximiser la **portabilité**

- **Déployer** et **valoriser** un projet de data science

- Outils techniques

----

### Approche pédagogique

- **Langages** :
    - Principes agnostiques au langage 
    - Exemples en **Python** et **R**

- **Environnement** : https://datalab.sspcloud.fr/
    - environnement de développement **normalisé**
    - simule un **environnement de production** réel
    - acquérir les **bonnes pratiques** de manière organique
        - conteneurisation
        - séparation code / données / environnement

---

# Qualité du code

----

### Enjeux 

- D'une vision utilitariste du code à une vision du code comme **outil de communication**

- Favoriser la **maintenabilité**

- Adopter les **standards communautaires** du langage

----

### Principes généraux

- Améliorer la **lisibilité**

- Favoriser la **concision**

- Assurer la **cohérence** interne

- Limiter la redondance

- **Documenter** son code

----

### Standards communautaires

- **Python** : [PEP8](https://peps.python.org/pep-0008/), [PEP 257](https://peps.python.org/pep-0257/)

- **R** : [Tidyverse style guide](https://style.tidyverse.org/index.html), [Google style guide](https://google.github.io/styleguide/Rguide.html)

- La **cohérence intra-projet** doit toujours primer

----

### Outils

- **Linters** : diagnostic de qualité du code
    - Python : [Pylint](https://github.com/PyCQA/pylint)
    - R : [lintr](https://github.com/r-lib/lintr)

- **Formatters** : application automatique des standards
    - Python : [Black](https://github.com/psf/black)
    - R : [styler](https://github.com/r-lib/styler)

---

# Structure des projets

----

### Enjeux

- Favoriser la **lisibilité** et la **maintenabilité**

- Enjeux spécifiques à la data science
    - **Expérimentation**
    - **Non-linéarité**
    - **Reproductibilité**

- Adopter les **standards communautaires** d'architecture

----

### Principes généraux

- Les données sont **immuables**
    - Pas de modifications manuelles
    - **Stockage externe** (ex : S3)

- **Notebooks** : pour l'**exploration** et la **communication**
    - Reproductibilité limitée
    - Mal gérés par le contrôle de version

- **Packages** : pour formaliser un **pipeline**
    - Modularité : **fonctions** dans des **modules**
    - Gestion des **dépendances**

----

### Standards communautaires / outils

- **Python** : *Cookiecutters* ([Cookiecutter Data Science](https://drivendata.github.io/cookiecutter-data-science/))

- **R** : *Projets RStudio* ([R for Data Science](https://r4ds.had.co.nz/workflow-projects.html))

- La **cohérence intra-projet** doit toujours primer

---

# Git : rappels

----

### Pourquoi utiliser Git ?

[<img src="img/timeline.png" height="500"/>](img/timeline.png)

[Source](https://thinkr.fr/travailler-avec-git-via-rstudio-et-versionner-son-code/)

----

### Concepts essentiels

![](img/gitallinone.png)

[Source](http://fabacademy.org/2021/labs/bhubaneswar/students/deepak-chaudhry/ia_PPFP.html)

----

### Bonnes pratiques

- Que versionne-t-on ?
    - Essentiellement du **code source**
    - **Pas de données**
    - Pas d'informations locales / sensibles
    - Pas d'outputs

- **Fréquence** des commits : le plus souvent possible tout en restant pertinent

- **Messages** des commits : **le pourquoi plutôt que le comment**

----

### En pratique

- Git est un **logiciel**

- Utilisation en **ligne de commande**

- Ressources sur le site :
    - [Introduction au terminal Linux](https://hungry-hodgkin-0a5a81.netlify.app/linux-101/)
    - [Rappels des commandes de base de Git](https://hungry-hodgkin-0a5a81.netlify.app/git/)

---

# Travail collaboratif avec Git

----

### Des outils pour mieux collaborer 

- **Git** :
    - branches

- **GitHub / GitLab** :
    - pull requests
    - forks
    - issues

- Ne remplacent pas une bonne organisation du travail d'équipe

----

### Branches

![](img/branches.png)

[Présentation détaillée sur le site du cours](https://hungry-hodgkin-0a5a81.netlify.app/git/#branches)

----

### Un modèle : le GitHub flow

![](img/ghflow.png)

[Présentation détaillée sur le site du cours](https://hungry-hodgkin-0a5a81.netlify.app/git/#workflow-collaboratif)

----

### Contribuer à un projet open-source

- **Issues** : bugs, suggestions, etc.

- **Pull requests** : proposer du code

- Procédure : 
    - créer un **fork** du projet
    - créer une **branche**
    - add/commit/push les changements proposés
    - ouvrir une **pull request** sur le repo cible

- Toujours suivre les règles de contribution

---

# Portabilité

----

### "It works... on my machine"

- On a construit un projet
    - Lisible
    - Avec une structure normalisée
    - Versionné proprement avec Git

- Peut-on partager notre projet ?
    - En théorie, oui !
    - En pratique, c'est toujours plus compliqué...

![](img/IWOMM.jpg)

----

### L'enjeu de la portabilité

- Un code ne vit jamais dans une bulle isolée, il contient en général de nombreuses adhérences
    - Des dépendances dans le langage du projet ;
    - Des dépendances dans d'autres langages ;
    - Des librairies système.

- Un code est portable s'il peut être exécuté dans un environnement différent que celui du développement

- Il nous faut de nouveaux outils pour atteindre une portabilité forte

----

## Les environnements virtuels

----

### Introduction

- *Workflow* classique du data scientist qui commencerait ses premiers projets
    - Installer une distribution de `Python` sur son poste
    - Développer un projet en installant les packages nécessaires
    - Passer au projet suivant et ainsi de suite

- Quels problèmes peuvent se poser ?

----

### Enjeux

- **Conflits de version** : différents projets peuvent recquérir des versions différentes d'un même *package* ;
- **Version de Python fixe**, celle de l'installation système ;
- **Reproductibilité limitée** : difficile de dire quel projet nécessite quel package ;
- **Portabilité limitée** : difficile de fixer dans un fichier les dépendances spécifiques à un projet.

----

### Fonctionnement

- **Dossier auto-suffisant** qui contient :
    - Une installation de `Python` pour une version donnée ;
    - Des packages additionnels
et qui est **isolé** des autres environnements existants

- Développer dans des environnements virtuels vierges en début de projet est une bonne pratique pour la **reproductibilité**

----

### Implémentation

- Différentes implémentations en Python
    - L'implémentation standard est `venv`
    - L'implémentation la plus populaire en data science est `conda`

- `conda` est à la fois
    - Un *package manager* (comme `pip`)
    - Un gestionnaire d'environnements virtuels

----

### Installation

- `conda` est généralement installé dans le cadre de **distributions**
    - `Miniconda`
    - `Anaconda`

- `conda` est un outil en ligne de commandes (CLI)

![](img/conda-eco.png)

----

### Gérer ses environnements avec `Conda`

| Commande | Principe |
|----------|----------|
| `conda create -n <env_name> python=<python_version>` | Création d'un environnement nommé `<env_name>` dont la version de Python est `<python_version>` |
| `conda info --envs` | Lister les environnements |
| `conda activate <env_name>` | Utiliser l'environnement `<env_name>` pour la session du terminal |
| `conda list` | Lister les _packages_ dans l'environnement actif |
| `conda install <pkg>` | Installer le _package_ `<pkg>` dans l'environnement actif |
| `conda env export > environment.yml` | Exporter les spécifications de l’environnement dans un fichier `environment.yml` |



----

---

# Application

----

### Bonnes pratiques de la séance

- Utiliser un **linter** pour implémenter les standards de qualité de code

- Utiliser des **templates de projet** adaptés à la data science

- **Versionner** ses projets avec **Git**

- Collaborer de manière efficiente avec les **branches** et les **pull requests**

----

### Exercice guidé

- Dépôt GitHub : [https://github.com/avouacr/ensae-reproductibilite-projet](https://github.com/avouacr/ensae-reproductibilite-projet)

- Consignes en bas de la page [Code et Architecture](https://hungry-hodgkin-0a5a81.netlify.app/code-architecture/) du cours

- Au programme :
    - Modularisation : mise en fonctions et en modules
    - Nettoyage de code avec un *linter*
    - Adoption d'une architecture de projet normalisée
    - Git et GitHub
    - Environnements virtuels
    - Conteneurisation avec Docker
