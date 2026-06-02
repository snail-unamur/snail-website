---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Creedengo : Quand les étudiants de l'UNamur contribuent à un code plus vert"
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
date: 2026-05-17T14:00:00+02:00
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

Dans le cadre du cours de Test et Qualité 2026, Nathan Lambrechts, Louca Mathieu et Florian Stormacq ont eu l'opportunité exceptionnelle de collaborer avec l'équipe de recherche SNAIL pour contribuer activement à [Creedengo](https://green-code-initiative.org/projets/creedengo), un projet majeur porté par la [Green Code Initiative](https://green-code-initiative.org/). Cette initiative internationale vise à réduire l'empreinte environnementale du secteur numérique en aidant les développeur.euse.s à écrire du code plus économe en énergie.

## Le défi : transformer la théorie en pratique

La problématique centrale de Creedengo repose sur un constat simple mais crucial : la consommation énergétique du matériel informatique est souvent dictée par la qualité du logiciel qui le pilote. Pourtant, la majorité des développeur.euse.s ignore l'impact énergétique de leurs choix de programmation. Pour combler ce fossé, la Green Code Initiative a développé un plugin pour SonarQube nommé Creedengo, capable d'alerter les développeur.euse.s sur les mauvaises pratiques énergétiques et de leur proposer des alternatives optimisées.
La mission confiée aux étudiants était ambitieuse : prendre en main ce plugin, identifier les bonnes pratiques encore non implémentées, les valider empiriquement par des tests rigoureux, et enfin, les intégrer directement dans le code source du projet via des contributions open source.

## Une démarche scientifique et technique rigoureuse

Le travail des étudiants ne s'est pas limité à une simple implémentation. Face à la difficulté de prioriser les règles sans validation préalable, ils ont développé un outil innovant appelé EnergyTracer. Ce programme permet de comparer deux fragments de code, l'un comportant des smells énergétiques, l'autre optimisé, afin de quantifier précisément la différence de consommation. Cette approche expérimentale garantit que chaque règle ajoutée au plugin repose sur des données tangibles et non sur de simples hypothèses.

La qualité et l'utilité de cet outil ont rapidement été reconnues par la communauté. En effet, la Green Code Initiative a officiellement repris [EnergyTracer](https://github.com/green-code-initiative/EnergyTracer) afin de l'intégrer à son écosystème. Le projet est désormais hébergé sur GitHub, dans l'organisation officielle de l'initiative, ce qui témoigne de la valeur ajoutée réelle apportée par les étudiants au-delà du cadre académique.

## Collaboration internationale et enjeux d'écosystème

Leur contribution s'est également traduite par la soumission de pull requests actives sur les dépôts officiels de la Green Code Initiative. Notamment, une règle visant à éviter les requêtes SQL illimitées (GCI24) a été implémentée pour le langage Python et est en cours de revue par les mainteneurs du projet. Une autre règle, liée à la gestion des listes non limitées (GCI82), est également en cours de développement.

Ce projet a permis aux étudiants d'interagir directement avec Olivier Le Goaër, de la Green Code Initiative, ce qui a soulevé des questions fondamentales sur la nature des règles de qualité logicielle. Ils ont dû naviguer entre des règles propres à un langage de programmation et celles applicables à des frameworks ou des plateformes spécifiques. Cette réflexion a conduit à une proposition intéressante : considérer le « langage » non pas isolément, mais comme un écosystème complet incluant ses bibliothèques et ses environnements d'exécution.

## Un héritage durable pour la communauté

La réussite de ce projet se mesure à la qualité de la validation empirique apportée et à l'intégration effective des règles au sein de l'écosystème Creedengo. Les contributions de Nathan, Louca et Florian ne sont pas de simples exercices académiques ; elles s'inscrivent dans une base de connaissances partagée utilisée par des milliers de développeur.euse.s à travers le monde pour réduire l'empreinte carbone de leurs applications.

En participant activement à la Green Code Initiative, ces étudiants démontrent que la formation universitaire peut être un levier puissant pour l'innovation sociale et environnementale. Leur travail sur Creedengo illustre parfaitement comment la rigueur technique et la conscience écologique peuvent converger pour créer un avenir numérique plus durable.
