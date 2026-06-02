---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Analyse de la qualité d'une application vibe codée : le projet Petit Tonnerre"
subtitle: ""
summary: ""
authors:
    - xavier-devroey
    - benoit-vanderose
    - jerome-maquoi
tags: 
  - Education
  - Vibe Coding
  - Software Development
  - Large Language Model
categories: []
date: 2026-05-17T14:30:00+02:00
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

Dans le cadre du cours de Test et Qualité 2026, une équipe d'étudiants composée de Justin Frémy, Olan Heinen, Guillaume Sougné et Gianni Wetzels s'est lancée dans une exploration fascinante : l'analyse de la qualité d'une application développée en mode « vibe coding ». Ce projet a été réalisé en collaboration avec l'équipe de recherche SNAIL de l'Université de Namur.

## Le contexte : coder sans coder, mais à quel prix ?

Le « vibe coding » désigne la pratique consistant à développer des applications sans écrire soi-même le code, en s'appuyant sur des outils d'intelligence artificielle comme Copilot. Jérôme Maquoi et ses amis en ont fait l'expérience de manière concrète : en un seul week-end d'octobre 2025, ils ont développé une application fonctionnelle grâce à cette approche. Une seule règle d’application : ne pas écrire une seule ligne de code. Petit Tonnerre est le fruit de cette expérience accélérée. Mais une application fonctionnelle est-elle nécessairement une application de bonne qualité ? C'est précisément cette tension entre la rapidité de production et le niveau de qualité qui constitue le cœur de la problématique explorée par les étudiants.

## Le système étudié

L'application Petit Tonnerre est un système de gestion de la maintenance des appareils électroménagers. Elle repose sur un backend en Python et un frontend en TypeScript, pour un total d'environ 6 000 lignes de code. Cinq développeurs ont travaillé sur ce projet, réalisé en un seul week-end. Cette contrainte temporelle extrême, que l’on retrouve, par exemple, dans des hackathons, offre un terrain d'observation privilégié pour comprendre comment le vibe coding influence les caractéristiques qualitatives du code produit.

## Méthodologie et outils d'analyse

Pour mener à bien cette analyse, l'équipe a mobilisé une batterie d'outils spécialisés : SonarQube pour l'analyse statique de la qualité, Radon pour la complexité cyclomatique, le TypeScript Compiler pour les erreurs de typage, GitDelver, un outil développé par Nicolas Riquet de l’équipe SNAIL pour l'extraction des données de versionnement, JSCPD pour la détection de duplication de code, et CodeScene pour l'analyse des hotspots et de la fréquence des changements. Cette diversité d'outils permet d'obtenir une vue multidimensionnelle de la qualité du code.

## Le dataset produit et sa disponibilité

Le format attendu était un jeu de données reprenant le code du projet analysé ainsi que les mesures de qualité relevées pour les différents stades de développement. Le dataset final comprend deux fichiers principaux : un fichier contenant les métriques par commit et un autre détaillant les hotspots par fichier, identifiés sur la base de leur évolution. Le projet complet, incluant le code source et l'ensemble des données analysées, est désormais [accessible publiquement sur GitHub](https://github.com/snail-unamur/petittonnerre).

## Les questions qui restent ouvertes

Deux questions émergent naturellement de ce travail. La première porte sur ce qui bloquait dans les prompts utilisés : comprendre les limites des instructions fournies à l'IA permettrait d'identifier les points de friction inhérents au vibe coding. La seconde interroge la représentativité de l'étude : dans quelle mesure les observations tirées de Petit Tonnerre peuvent-elles être généralisées à d'autres projets développés selon la même approche ? Ces interrogations dessinent les contours de travaux futurs, tout en rappelant que la question de la qualité dans le vibe coding est loin d'être close.
