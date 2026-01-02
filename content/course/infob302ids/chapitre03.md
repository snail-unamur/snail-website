---
title: Question de recherche et hypothèse
date: '2025-09-15'
type: book
weight: 30
summary: Ce chapitre décrit comment établir et vérifier la qualité d'une question de recherche et de ses sous-questions et hypothèses.
---

{{< toc hide_on="xl" >}}

Une fois que l'on a pris connaissance de l'état de l'art, il est possible de formuler une question de recherche en lien avec la problématique étudiée. Cette question représente une interrogation que l'on pose afin d'aider à identifier la méthode à appliquer qui permettra d'y répondre et de définir de manière précise le protocole expérimental.

## Question et sous-questions de recherche

Par exemple, dans le cas où l'on crée un nouvel algorithme permettant de générer des tests, la question de recherche sera :

> Dans quelle mesure l'approche XYZ permet-elle de générer des tests plus efficaces pour la détection de fautes que les approches existantes A, B, C ?

Dans cet exemple, une méthode possible est l'utilisation d'un benchmark (un ensemble de programmes) sur lequel on va appliquer les différentes approches afin de comparer les tests générés.

Il n'est pas rare qu'un article scientifique comporte plusieurs questions de recherche. Ces questions permettent souvent de raffiner une question plus générale afin de préciser le cadre (scope) de la recherche et de clairement distinguer les éléments qui font partie de ceux qui ne sont pas considérés. Une bonne (sous-)question de recherche n'est pas trop ouverte (ou générique), afin de ne pas avoir un cadre trop large. De la même manière, elle n'est pas non plus trop fermée, afin de pouvoir apporter les nuances nécessaires à la réponse.

{{< callout warning >}}
**Il faut par exemple éviter les questions dont la réponse est *oui* ou *non*.** Bien que claire et compréhensible, une telle réponse n'apporte pas beaucoup d'information et ne fait dont pas progresser son domaine de recherche. (Sans compter qu'elle vous vaudra une **pénalité immédiate** dans le cadre du cours d'introduction à la démarche scientifique !)
{{< /callout >}}

Dans notre exemple, la question générale pourrait être comprise de plusieurs manières, en fonction de l'angle adopté et de la sémantique que l'on donne au mot *efficaces*. C'est pour lever ce genre d’ambiguïtés qu'il est intéressant de raffiner une question de recherche en sous-questions. Dans notre cas, si l'on considère seulement les tests générés, on pourra par exemple raffiner la question en sous-questions :

> - Dans quelle mesure l'approche XYZ génère-t-elle des tests qui couvrent plus de lignes de code que les approches A, B, C ?
> - Dans quelle mesure l'approche XYZ génère-t-elle des tests qui détectent plus de mutants que les approches A, B, C ?
> - Dans quelle mesure l'approche XYZ génère-t-elle des tests qui détectent plus de fautes que les approches A, B, C ?

À partir de ces questions, il devient très facile de définir un protocole expérimental qui comportera une phase de génération de tests, une phase d'analyse des tests générés avec des mesures de la couverture de code, du score de mutation et du nombre de fautes détectées sur un benchmark défini.

## Hypothèses de recherche

En fonction de la culture et des pratiques d'un domaine de recherche, il est intéressant d'aller une étape plus loin et de formuler ce que l'on appelle des hypothèses de recherche. Ces hypothèses sont des affirmations en lien avec une question de recherche. Tout comme les sous-questions de recherche, ces hypothèses permettent de préciser le cadre de la recherche et le protocole expérimental.

Dans notre exemple, si l'on considère que des tests générés *efficaces* sont avant toute chose des tests utilisables par un développeur afin de détecter des fautes, on peut raffiner la question de recherche générale en sous-questions :

> - Dans quelle mesure l'approche XYZ est-elle utilisable par un développeur par rapport aux approches existantes A, B, C ?
> - Dans quelle mesure l'approche XYZ aide-t-elle un développeur à détecter des fautes par rapport aux approches existantes A, B, C ?

Dans ce cas-ci, le protocole expérimental sera totalement différent. On peut par exemple demander à cinq groupes de développeurs différents de produire des tests pour une ou plusieurs applications données contenant des fautes. Quatre de ces groupes pourront s'aider d'une approche automatisée (XYZ, A, B et C) et le cinquième (le groupe témoin) écrira les tests manuellement. Contrairement à notre exemple précédent, ce protocole ne précise toutefois pas ce qui sera mesuré. Afin de préciser le cadre de la recherche, on peut formuler la série d'hypothèses suivantes :

> - L'approche XYZ permet à un développeur de produire un ensemble de tests plus rapidement que les approches A, B, C et que l'approche manuelle.
> - L'approche XYZ permet à un développeur de produire un ensemble de tests couvrant plus de code et de mutants que les approches A, B, C et que l'approche manuelle.
> - L'approche XYZ permet à un développeur de détecter plus de fautes que les approches A, B, C et que l'approche manuelle.
> - L'approche XYZ permet à un développeur de détecter plus rapidement les fautes que les approches A, B, C et que l'approche manuelle.

Ces hypothèses nous renseignent sur ce qui sera mesuré : le temps mis par les développeurs pour produire une suite de tests et pour détecter les fautes, ainsi que le nombre de fautes détectées et la couverture de code et le score de mutation des tests produits.

## Prototypes de questions de recherche

En fonction des objectifs de la recherche, il est possible de partir d'un certain nombre de prototypes de questions de recherche à adapter.

### Décrire et explorer

- Quelles sont les caractéristiques de X (dans le contexte Y) ?
- Comment X a-t-il évolué au fil du temps (dans le contexte Y) ?
- Quels sont les principaux facteurs de X ?
- Comment X a-t-il géré Y ?

### Explorer et tester

- Quelle est la relation entre X et Y ?
- Quel est le rôle de X dans Y ?
- Quel est l'impact de X sur Y ?
- Comment X influence-t-il Y ?
- Quelles sont les causes de X ?

### Évaluer et agir

- Quels sont les avantages et les inconvénients de X (dans le contexte Y) ?
- Quelle est l'efficacité de X (pour la tâche Y) ?
- Comment X peut-il être réalisé (dans le contexte Y) ?
- Quelles sont les stratégies les plus efficaces pour améliorer X (dans le contexte Y) ?
- Comment X peut-il être utilisé dans Y ?

## Le framework PICOT

Le framework PICOT est couramment utilisé dans la recherche clinique. Il permet d'identifier les éléments essentiels qui doivent apparaître dans un question de recherche ou de vérifier qu'une question de recherche est bien formulée, c'est-à-dire qu'elle délimite bien le cadre de la recherche.

### Patient, population ou problème

Qui ou quoi est le patient, la population ou le problème en question ? Par exemple, des classes Java.

### Intervention

Quelle est l'intervention (action ou traitement) envisagée ? Par exemple, la génération de tests unitaires avec l'outils XYZ.

### Comparaison ou contrôle

Quelles autres interventions devraient être envisagées ? Par exemple, la génération de tests unitaires avec les outils standards A, B et C.

### Résultat ou objectif

Quel est le résultat ou l'objectif souhaité ou attendu ? Par exemple comparer la capacité à détecter des fautes en utilisant le score de mutation.

### Délai (Time)

Combien de temps faudra-t-il pour atteindre le résultat souhaité ? Par exemple, en utilisant des *time budgets* de 1, 3 et 5 minutes pour les différents outils.

## La checklist FINER

Le checklist suivante permet de vérifier qu'une question de recherche est de bonne qualité. Cette liste se concentre sur la réalisabilité de la recherche. Elle est complémentaire au framework PICOT qui se concentre sur le cadre (scope) de la recherche.

### Faisable

Le chercheur est-il capable d'étudier la question de recherche ?

### Intéressante

La question de recherche est-elle intéressante pour le chercheur, ses pairs et la communauté ?

### Novatrice

La réponse à la question apporte-t-elle de nouvelles perspectives ou confirme-t-elle des résultats antérieurs ?

### Éthique

La réponse à la question de recherche respecte-t-elle les normes éthiques et juridiques du chercheur et de son institution ?

### Pertinente (Relevant)

La question de recherche est-elle pertinente pour la communauté scientifique (et le grand public) ?

## Resources additionnelles

- [Writing Strong Research Questions - Criteria and Examples](https://www.scribbr.com/research-process/research-questions/)
