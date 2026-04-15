---
title: Introduction
date: '2025-09-15'
type: book
weight: 10
summary: Ce chapitre introduit l’automatisation appliquée au génie logiciel et pose le cadre du cours INFOM126 (Automated Software Engineering) de l’Université de Namur. Nous clarifions les objectifs, les concepts clés et le positionnement du cours dans la discipline informatique / génie logiciel, avant d’illustrer concrètement ce que l’automatisation change dans la pratique du développement et de l’exploitation du logiciel.
---

{{< toc hide_on="xl" >}}

Ce chapitre introduit l’automatisation appliquée au génie logiciel et pose le cadre du cours INFOM126 (Automated Software Engineering) de l’Université de Namur. Nous clarifions les objectifs, les concepts clés et le positionnement du cours dans la discipline informatique / génie logiciel, avant d’illustrer concrètement ce que l’automatisation change dans la pratique du développement et de l’exploitation du logiciel.

Objectifs du chapitre. À l’issue de la lecture, vous serez capable de :

- caractériser les avantages et limites de l’automatisation;
- relier les activités de génie logiciel aux outils et pratiques automatisées (CI/CD, monitoring, IaC); 
- situer l’Automated Software Engineering (ASE) et ses enjeux humains, techniques et éthiques; 
- comprendre l’organisation et les attentes du cours.

## Automatisation : promesses, limites et paradoxes

### Pourquoi automatiser ?

Automatiser consiste à déléguer à un système logiciel des opérations répétitives ou coûteuses pour accélérer l’exécution, améliorer la qualité et rendre les processus plus prédictibles et robustes. Les bénéfices typiques incluent une réduction du travail humain direct, des cycles plus courts (exécution 24/7), une cohérence d’output et une meilleure sécurité lorsqu’on retire l’humain d’environnements dangereux.

### Les contreparties et risques

Les limites sont réelles : coûts d’amorçage élevés (apprentissage et intégration d’outils), propagation systématique de défauts si un processus automatisé est mal conçu, effets d’échelle (petit incident, grand impact), et fragilité de chaînes séquentielles où une panne bloque tout. Des impacts sur l’emploi existent—souvent par transformation des rôles plutôt que suppression pure. Exemples évoqués : rappel industriel quand une pièce défectueuse se propage; indisponibilité globale d’un service quand le certificat d’authentification expire; besoin d’un opérateur humain capable de superviser, corriger ou contourner temporairement.

### Paradoxe et ironies de l’automatisation

Plus un système automatisé est efficace, plus critique devient la contribution des opérateurs humains qui le supervisent. Les ironies de l’automatisation rappellent qu’on obtient parfois l’opposé de l’effet recherché; d’où l’importance de checks et d’une visibilité sur les effets des actions. En contexte logiciel, l’absence du référent « pipeline » peut paralyser une équipe entière.

> Exemple pédagogique. La demande d’automatiser les 20% de cas les plus difficiles (et non les 80% faciles) illustre que l’objectif n’est pas seulement la vitesse mais aussi la réduction de la fatigue cognitive et l’optimisation de la valeur perçue par les opérateurs.

## Le génie logiciel : définitions, qualités et principes

### Pourquoi le génie logiciel ?

Le logiciel est aujourd’hui omniprésent; sa production a des impacts sociétaux importants et engage la responsabilité des développeurs. Le génie logiciel fournit une approche systématique et disciplinée pour concevoir, exploiter et maintenir des systèmes fiables et utiles.

### Définitions (paraphrase)

- Le génie logiciel est l’application systématique de connaissances scientifiques et techniques, de méthodes et de retours d’expérience pour concevoir, implémenter, tester et documenter le logiciel en optimisant production, support et qualité.
- Il s’agit d’une démarche disciplinaire et mesurable couvrant développement, opérations et maintenance—trois volets indissociables dans la pratique moderne.

### Informatique vs. génie logiciel

La computer science apporte théories et modèles; le génie logiciel mobilise ces fondements pour résoudre un problème client/utilisateur via outils et techniques (analyse, conception, tests, déploiement). L’ASE se concentre sur l’outillage et son design afin d’améliorer process et qualité.

### Qualités d’un « bon » logiciel (synthèse)

- Maintenabilité : faciliter l’évolution au fil des besoins.
- Fiabilité/Sécurité : éviter dommages et accès malveillants.
- Efficience : usage parcimonieux des ressources (temps, mémoire, énergie).
- Acceptabilité : utilisable, compréhensible, compatible, et socialement/organisationnellement acceptable.
Ces qualités guident les choix d’architecture, de codage et d’automatisation.

### Principes généraux (sélection commentée)

- KISS : simplicité sans sur-simplification; l’objectif est de faciliter la compréhension et la maintenance.
- Maintenir la vision : une architecture claire et cohérente évite l’érosion (ex. microservices vs. monolithe central).
- Ouvert au futur & réutilisation : concevoir pour généraliser, adapter (matériel, plateformes, librairies) et réutiliser sans complexifier inutilement.
- Penser avant d’agir : un temps de réflexion en amont augmente la qualité et diminue les retouches.

### Responsabilité et éthique

Le code produit a des conséquences; les professionnels doivent contribuer au bien-être des personnes, éviter le tort, respecter la confidentialité et la vie privée, et créditer le travail d’autrui (licences open source comprises). Ces engagements éthiques s’appliquent aussi lorsqu’on utilise des LLM pour générer, refactorer ou documenter du code : l’auteur reste responsable.

## Activités du génie logiciel et points d’automatisation

### Ingénierie des exigences

But : établir les services attendus et les contraintes d’opération et de développement. Sous-activités : élicitation/analyse (besoins des parties prenantes), spécification (textes, user stories, modèles), validation (alignement avec les attentes). Le cycle est itératif et implique fortement des humains (utilisateurs, opérateurs).

### Développement (conception et implémentation)

À partir des exigences, on conçoit l’architecture, puis on implémente (code, tests). Conception et implémentation sont imbriquées et demandent de préserver la vision. On privilégie un développement incrémental, en gérant les deadlines et la qualité.

### Vérification et validation

La V&V démontre la conformité à la spécification et la pertinence pour l’utilisateur. Elle combine revues et tests (unitaires, intégration, fonctionnels, sécurité, charge). Les tests sont la pratique V&V la plus répandue; l’automatisation (ex. exécution en CI) en démultiplie la portée.

### Évolution et maintenance

Le logiciel évolue avec le contexte (exigences, décrets, technologies). La frontière « développement vs maintenance » s’estompe : de nombreux projets sont des refontes d’existants, avec migration de données parfois délicate. Le refactoring et la documentation préparent l’avenir; une part peut être assistée (LLM), mais le contrôle humain demeure essentiel.

## Automated Software Engineering (ASE)

### Définition opérationnelle

L’ASE vise à concevoir et orchestrer des outils et des pipelines automatisés pour soutenir les activités du génie logiciel (build, tests, analyses, déploiement, monitoring). Le champ est représenté, entre autres, par la conférence ASE et par de nombreuses études de cas industrielles.

### CI/CD : la colonne vertébrale

Le Continuous Integration / Continuous Delivery/Deployment automatise la chaîne depuis le commit/push jusqu’aux analyses (tests, linters, couverture), et éventuellement jusqu’au déploiement si les checks passent. Les systèmes de CI jouent le chef d’orchestre de ces tâches et notifient en cas d’échec.

### Étude de cas TSSG (synthèse)

Dans une équipe Java, l’outillage open source permet le suivi d’issues, le build (compilation, gestion de dépendances, tests), l’intégration continue et la gestion des tests (automatisés et manuels). Un manque identifié : l’automatisation du déploiement. Cet exemple illustre la chaîne d’outils et le rôle central de la CI.

### Panorama d’outils et pratiques (FWB 2025)

Une enquête (Fédération Wallonie–Bruxelles) signale une large adoption de l’automatisation pour compilation, analyse de code, tests, CI et déploiement. Côté gestion de versions, Git domine (présence résiduelle de SVN). Pour la gestion de projet, Jira est majoritaire; en CI/CD, on retrouve Jenkins, GitLab CI, Azure Pipelines et GitHub Actions, avec quelques outils « autres ». Ces résultats confirment l’importance de l’outillage dans la qualité des processus.

### Automatisation « historique » et LLM aujourd’hui

La compilation est une première forme d’automatisation (traduire un langage de haut niveau en code exécutable). Aujourd’hui, des LLM peuvent assister la génération de code et de tests, le refactoring et la documentation; la question centrale demeure la qualité et la responsabilité de l’auteur.

## Exemples et illustrations

- Apollo & Margaret Hamilton : l’ingénierie du logiciel a émergé historiquement pour rendre fiable et certifiable le logiciel de systèmes critiques; l’anecdote souligne l’importance de processus, outillage et discipline.
- Cigale / Noé (UNamur) : un cas d’évolution majeure où un fork open source devenu inmaintenable a conduit à une refonte et une migration de données — exemple des effets cumulatifs des changements réglementaires.
- Chaîne d’outils Java (type TSSG) : suivi d’issues, IDE + système de build (dépendances, tests), CI orchestrant analyses et notifications; tests fonctionnels (ex. Selenium), sécurité et charge complètent les tests unitaires.

## Résumé — Points clés à retenir

- L’automatisation vise vitesse, qualité, prédictibilité et sécurité, mais n’élimine pas le besoin d’opérateurs humains : elle renforce leur rôle.
- Le génie logiciel articule exigences, conception/implémentation, V&V et évolution; l’ASE fournit les outils et pipelines qui soutiennent ces activités.
- La CI/CD est la colonne vertébrale de l’ASE : déclenchements sur commit, analyses automatisées, déploiements éventuels, et feedback rapide.
- Les qualités (maintenabilité, fiabilité/sécurité, efficience, acceptabilité) guident l’architecture et l’automatisation; les principes (KISS, vision, futur/réutilisation, penser d’abord) orientent les décisions.
- L’éthique (ACM) et la responsabilité demeurent, y compris avec l’usage des LLM.
- Le cours INFOM126 vous amènera à analyser un projet et à concevoir une pipeline concrète, avec des références et outils courants du secteur.
