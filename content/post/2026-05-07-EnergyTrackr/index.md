---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "EnergyTrackr : traquer les régressions énergétiques dans le code Java"
subtitle: ""
summary: ""
authors:
    - xavier-devroey
    - benoit-vanderose
    - jerome-maquoi
tags: 
  - Education
  - Energy Consumption
  - Sustainability
  - Green Coding
categories: []
date: 2026-05-17T14:20:00+02:00
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

La consommation énergétique est l'un des principaux enjeux liés à l'impact environnemental de l'IT. Si l'on pense souvent au hardware comme principal responsable, le software joue un rôle déterminant dans cette consommation. Dans ce contexte, l'évolution de l'impact énergétique d'un projet informatique est de plus en plus étudiée dans la littérature scientifique. C'est précisément cette problématique qui a motivé la création d'[EnergyTrackr](https://github.com/snail-unamur/energytrackr), un outil développé en 2025 par François Béchet, alors étudiant en dernière année de master réalisant son mémoire avec l’équipe SNAIL, lors de son stage de recherche à la TU Delft.

L'idée centrale est simple mais puissante : mesurer l'évolution de la consommation énergétique de différents projets informatiques en analysant un très grand nombre de modifications de code (commits). L'objectif est de signaler les commits qui augmentent ou diminuent de manière significative la consommation énergétique du projet. Une fois ces points critiques identifiés, il devient possible d'analyser le contenu de ces commits afin de comprendre pourquoi ils font varier la consommation, ouvrant ainsi la voie à des recommandations concrètes pour les développeur.euse.s.

## Une sélection rigoureuse pour des données fiables

Cependant, un outil de mesure n'a de valeur que s'il a été éprouvé sur des cas réels et représentatifs. L'outil EnergyTrackr doit être utilisé sur un certain nombre de projets afin de vérifier qu'il fonctionne correctement, puis d'analyser le contenu de ces commits flaggés. C'est dans cette optique que le cours de Test et Qualité 2026 a confié à une équipe d'étudiants, composée de Houria Ariouat, Louis Bomal, Thomas Busoni et Ilias Essarhiri, la mission de prendre en main cet outil et de le déployer sur des projets open source.

Les objectifs étaient clairs : trouver des projets pertinents à analyser, exécuter EnergyTrackr sur ces projets et récupérer toutes les données générées par l'outil. Pour garantir la pertinence et la fiabilité des données collectées, l'équipe a établi des critères de sélection stricts. Les projets retenus devaient impérativement être open source, développés et testés en Java, et structurés autour de Maven afin de faciliter l’exécution du pipeline d’analyse. Au-delà de la technologie, des seuils minimaux pour les caractéristiques du projet ont été fixés afin d’assurer la robustesse des mesures (une couverture de code supérieure ou égale à 60 %, un volume de code Java d’au moins 15 000 lignes et un historique important avec plus de 500 commits).

## La méthodologie de collecte et d'analyse

Pour identifier les dépôts pertinents, l'équipe s'est appuyée sur la liste communautaire [AwesomeJava](https://github.com/akullpp/awesome-java). Une fois les projets sélectionnés selon les critères définis, l'équipe a dû s'adapter à l'environnement d'EnergyTrackr, ce qui a nécessité une phase d'appropriation de l'outil. Des fichiers de configuration spécifiques ont été créés pour chaque dépôt retenu, conformément au format défini dans la documentation de l'outil. L'exécution de l'outil statistique EnergyTrackr a permis de mesurer la consommation énergétique des projets sélectionnés. Les résultats ont été générés sous forme de fichiers de mesures identifiés par la date d'exécution. Ces données brutes ont ensuite été triées à l'aide des commandes fournies par EnergyTrackr et visualisées sous forme de graphiques pour faciliter l'interprétation des tendances énergétiques.

## Une équipe à l'oeuvre sur trois projets

L'équipe a relevé le défi avec rigueur. Après une phase de sélection minutieuse et une exécution soignée des analyses, trois projets ont finalement été analysés. Les données collectées ont été [déposées sur GitHub](https://github.com/snail-unamur/energytrackr-data). Une pull request est actuellement en cours de review par François, l'auteur de l'outil, ce qui témoigne d'une démarche d'intégration progressive et collaborative au sein de l'écosystème de recherche.

La hot take du projet résume parfaitement l'esprit de cette initiative : « L'évolution de la consommation énergétique nous renseigne sur ce qu'il faut éviter de faire. » En effet, chaque commit marqué comme une régression énergétique représente une opportunité d'apprentissage pour la communauté des développeur.euse.s.

## Vers une ingénierie logicielle plus durable

Le travail réalisé par l'équipe s'inscrit dans une démarche de recherche appliquée où l'outil n'est qu'un moyen, et non une fin. EnergyTrackr permet de générer des données précises sur l'évolution énergétique des projets. L'analyse de ces données permettra, à terme, de formuler des recommandations concrètes destinées aux développeur.euse.s. Quels patterns de code sont les plus énergivores ? Quels refactorings permettent de réduire la consommation ? Autant de questions auxquelles les datasets produits pourront contribuer à répondre.

En rendant visibles les régressions énergétiques, EnergyTrackr offre aux développeur.euse.s un moyen de surveiller l'impact de leurs choix de conception et d'optimiser leur code afin de réduire la consommation énergétique des logiciels. C'est une étape importante vers une ingénierie logicielle véritablement durable, où chaque ligne de code est pensée non seulement pour sa fonctionnalité, mais aussi pour son empreinte énergétique.
