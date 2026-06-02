---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "PReQual : Quand la qualité du code redéfinit la gestion des Pull Requests sur GitHub"
subtitle: ""
summary: ""
authors:
    - xavier-devroey
    - benoit-vanderose
    - jerome-maquoi
tags: 
  - Education
  - Software Development
  - Pull Request
  - Code Review
  - Software Engineering
categories: []
date: 2026-05-17T14:40:00+02:00
lastmod: 2026-06-02T00:00:00+02:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

Dans le paysage actuel du développement logiciel, les Pull Requests (PRs), également appelées merge requests, constituent un pilier central de l'intégration continue. Elles permettent de séparer clairement l'effort de développement de l'intégration dans la base de code principale. Ce processus repose sur une étape cruciale : la revue de code, menée par un.e développeur.euse distinct de l'auteur des changements, afin de prévenir les défauts, d’améliorer la lisibilité et de partager les connaissances. C'est dans ce contexte que s'inscrit le projet PReQual, réalisé par les étudiants Mallory Bouchard, Hugo Raskin, Arthur Smoos et Taj Eddine Temsamani Bouazza du cours de Test et Qualité 2026, en collaboration avec l'équipe de recherche SNAIL.

## Continuité avec PRECOG : Une recherche en évolution

Le projet PReQual s'inscrit dans la continuité directe des travaux de recherche sur la priorisation des Pull Requests initiés par l'équipe SNAIL. En particulier, il prolonge les investigations menées dans le cadre de [PRECOG](https://snail.info.unamur.be/publication/raskin-2025/), un plugin Visual Studio Code développé par Hugo Raskin, présenté à la conférence SANER 2026. PRECOG vise à aider les relecteurs à sélectionner la PR appropriée en offrant une visualisation radar de la difficulté de chaque PR et un classement automatique basé sur des métriques logicielles.

L'évaluation utilisateur de PRECOG, réalisée auprès de neuf développeur.euse.s sur le framework Java Spring, a montré que malgré des divergences dans les classements subjectifs, tous les participants ont reconnu la valeur ajoutée de la vue synthétique fournie par l'outil pour prendre des décisions rapides et éclairées. Ces résultats positifs ont motivé le développement de PReQual, qui vise à créer le jeu de données nécessaire pour alimenter et étendre les fonctionnalités de ce type d'outils.

## La problématique : Objectiver la revue de code

L’hypothèse de départ du projet, « La qualité du code influe sur la gestion des pull requests sur GitHub », vise à explorer comment des facteurs objectifs peuvent aider les relecteurs dans leur travail quotidien. Les étudiants se sont interrogés sur la manière dont des métriques logicielles précises peuvent indiquer le niveau de complexité, le volume, la criticité ou les défauts de conception potentiels du code soumis dans une PR. L'objectif est d'aider les relecteurs à choisir la PR la plus appropriée à examiner parmi un ensemble de demandes qui leur ont été préassignées, en s'appuyant sur des données tangibles plutôt que sur une simple intuition.
Pour étayer cette hypothèse, le groupe s'est appuyé sur l'étude PRECOG, ainsi que sur des ressources communautaires comme la liste [Awesome Empirical Software Engineering](https://github.com/dspinellis/awesome-msr).

## Un outil d'extraction automatisé et conteneurisé

Pour répondre à cette problématique, le groupe a conçu et développé un outil d'extraction en Go, entièrement automatisé et conteneurisé. L'architecture repose sur une orchestration Docker comprenant trois composants clés : une instance de SonarQube pour le calcul des métriques de qualité, le scanner SonarQube en ligne de commande pour l'analyse effective du code source, et une base de données MongoDB pour le stockage structuré des résultats.

L'utilisation de cet outil nécessite une configuration. Une fois lancé, le script permet de cibler des dépôts GitHub spécifiques, de définir une plage de PRs à analyser et de sélectionner les métriques à collecter. Par défaut, l'outil calcule la complexité cyclomatique et la complexité cognitive, mais il est configurable pour inclure d'autres indicateurs tels que le nombre de lignes de code non commentées (NCLOC), les code smells, les lignes dupliquées, le coût estimé de développement et le rating de maintenabilité. Cette flexibilité permet d'adapter l'analyse aux besoins spécifiques de la recherche.

## Composition et structure du dataset produit

Le résultat concret de ce travail est un jeu de données (dataset) complet et structuré, analysé entre mars et avril 2026. Ce dataset reprend l'historique du code entourant chaque Pull Request, incluant le code source des branches source (head) et cible (merge base), ainsi que les mesures logicielles calculées sur ces différentes versions via SonarCloud.

Chaque entrée du dataset est un objet JSON contenant :

- Les métadonnées GitHub : Identifiants, titres, corps des messages, statuts (ouvert, fermé, fusionné), et dates de vie de la PR.
- Les interactions : La liste complète des commentaires et des revues de code, distinguant les auteurs humains des bots, avec leurs statuts de validation.
- Les métriques techniques : Des objets détaillés pour la branche cible et la branche source, présentant la complexité, les défauts de conception et la maintenabilité.
- Les statistiques : Des mesures de taille relative et de durée.
Les données brutes sont également disponibles sous forme de dump MongoDB, facilitant leur restauration et leur exploration.

## Choix méthodologiques et défis techniques

Les dépôts analysés à ce jour incluent les projets Flask et Falcon, deux références majeures de l'écosystème Python. Ce choix de langage n'est pas anodin. Comme l'ont souligné les étudiants, le système de build de Python se révèle plus simple et rapide que celui des projets Java, où la compilation et le build prennent davantage de temps et posent des problèmes de reproductibilité. Cette décision a permis de garantir une exécution fluide des analyses et une collecte de données fiable.
La réussite de ce projet repose sur la qualité de ce dataset ouvert, notamment sa représentativité des projets existants, le nombre de PRs analysées et le strict respect des principes FAIR (Findable, Accessible, Interoperable, Reusable). En complément de la collecte de données, les étudiants ont développé une visualisation via un dashboard, ce qui permet une meilleure interprétation des résultats.

## Accès aux résultats et perspectives

L'ensemble du travail est désormais accessible à la communauté scientifique et aux développeur.euse.s. Le [dataset est hébergé sur Zenodo](https://doi.org/10.5281/zenodo.19354720), tandis que le code source de l'[outil d'analyse est disponible sur un autre dépôt](https://github.com/snail-unamur/PReQual-script). Ces ressources offrent une base solide pour de futures recherches sur l'optimisation des processus de revue de code et sur l'impact de la qualité logicielle sur la gestion collaborative du développement.

À terme, ce dataset pourrait alimenter des outils comme PRECOG, permettant d'affiner les algorithmes de classement et d'enrichir les visualisations de la difficulté des PRs. Les étudiants ont également identifié des pistes d'amélioration, notamment l'intégration de facteurs subjectifs liés à l'expérience des développeur.euse.s et la prise en compte de dimensions supplémentaires, telles que la dispersion des changements ou la couverture des spécifications.
