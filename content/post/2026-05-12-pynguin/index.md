---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Sécuriser l'interface Python/C : Comment une nouvelle méthode de test a révélé des bugs critiques dans les bibliothèques d'IA"
subtitle: ""
summary: ""
authors:
    - xavier-devroey
tags: 
  - Artificial Intelligence
  - Software Testing
  - Search-Based Software Testing
categories: []
date: 2026-05-12T00:00:00+02:00
lastmod: 2026-05-12T00:00:00+02:00
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
projects:
    - cyberexcellence
---

Les bibliothèques fondamentales de la data science et du Machine Learning (NumPy, SciPy, Pandas, TensorFlow) reposent sur un compromis d'ingénierie classique : offrir la simplicité de Python pour le développement, tout en déléguant les calculs intensifs à du code natif en C pour la performance via ce qu'on appelle une interface de fonction étrangère (FFI).

Cependant, cette hybridation crée une zone de fragilité critique. Contrairement à Python, qui gère automatiquement la mémoire et vérifie les bornes des tableaux, le code C opère avec une liberté totale. Si une fonction C reçoit des arguments invalides (par exemple, un tableau de mauvaise dimension), elle ne lève pas d’exception Python propre. Au lieu de cela, elle tente d'accéder à une adresse mémoire invalide, ce qui provoque une segmentation fault (segfault) et fait planter l'interpréteur Python entier.

Les outils de test automatisés (comme Pynguin) fonctionnent en boucle : ils génèrent un test, l'exécutent, mesurent la couverture et ajustent la stratégie. C’est ce que l’on appelle une approche évolutive (search-based). Pour que cela fonctionne, Pynguin doit pouvoir exécuter le test et surveiller simultanément l’impact de cette exécution, par exemple pour voir quelles lignes de code sont exécutées. Ce mécanisme (appelé instrumentation) gère également les exceptions propres à Python. En revanche, si le test généré provoque une segfault, le processus de test lui-même meurt. La boucle est brisée, le bug détecté est perdu sans pouvoir être rapporté au développeur et l'exploration du code s'arrête. Détecter ces bugs nécessitait jusqu'alors une intervention manuelle complexe et hasardeuse.

## La solution : l'exécution par sous-processus isolés

La recherche menée par Lucas Berg de l’Université de Namur et Lukas Krodinger de l’Université de Passau, en Allemagne, propose une refonte de l’architecture d’exécution des tests pour surmonter cette limitation. L'idée centrale consiste à découpler la boucle d’exécution de Pynguin de celle des tests. Techniquement, au lieu d'exécuter les tests dans des threads au sein du même processus (partageant la même mémoire), chaque test est lancé dans un sous-processus isolé. Cette approche transforme un crash en une donnée exploitable, en permettant à Pynguin de les récupérer. En d’autres termes, elle permet non seulement de détecter des bugs autrement invisibles, mais aussi de générer automatiquement des tests de régression pour les corriger. Cette approche comporte toutefois un coût : le temps d’exécution des tests s’allonge en raison de la création et de la gestion des sous-processus. 

## Une histoire rendue possible par l’Open Source et l’Open Science

Cette avancée est le fruit d'un travail académique soutenu et de collaborations entre plusieurs universités. Tout a commencé avec Lucas Berg, qui a réalisé son mémoire de master à l'Université de Namur sous la direction du professeur Xavier Devroey. Durant le stage de recherche qui accompagne ce mémoire, Lucas est parti travailler au sein de l’équipe du professeur Annibale Panichella à l’Université de Delft, aux Pays-Bas. Le but initial de la recherche était de générer des données complexes dans [Pynguin](https://www.pynguin.eu/), un outil open source de génération de tests pour des programmes Python, développé par l’équipe du professeur Gordon Fraser à l’Université de Passau, afin de tester des bibliothèques de machine learning. Lucas s’est rapidement retrouvé confronté aux limites liées à la gestion des appels en C et a redirigé ses efforts vers la conception d’une solution qui pallie ce problème. Ce travail a débouché non seulement sur un mémoire réussi avec brio, mais aussi sur une [proposition de modification du code de Pynguin](https://github.com/se2p/pynguin/pull/82).

Cette proposition de modification a vite attiré l’attention de Lukas Krodinger et Stephan Lukasczyk, de l’équipe du professeur Fraser, lorsqu’ils se sont retrouvés confrontés au même problème de crash lors d’appels à des bibliothèques écrites en C. Lucas, qui a été engagé en tant qu’assistant à la faculté d’Informatique à la fin de son master, s’est alors mis à collaborer avec Lukas et Stephan pour raffiner son approche et l’intégrer à Pynguin. Cette collaboration a été rendue possible grâce au caractère open source de l’outil et des librairies de machine learning évaluées. Elle a débouché sur une publication dont l’artefact reprenant les données générées (open data), ainsi que les éléments nécessaires pour reproduire l’évaluation (open methodology), a été évalué et a reçu les badges IEEE témoignant de sa qualité.

## Des bugs découverts dans des bibliothèques populaires de ML

En appliquant cette méthode à 1 648 modules des bibliothèques les plus utilisées au monde, Lucas et Lukas ont découvert 32 bugs inédits causant des crashs qui avaient échappé aux tests manuels, dont des erreurs de validation d'arguments dans des fonctions mathématiques complexes de NumPy et SciPy, des plantages lors d'opérations d'indexation dans Pandas et plus de 20 bugs dans des fonctions de gestion de la mémoire dans TensorFlow.

Ces découvertes ont été directement rapportées aux équipes de développement, ce qui a permis d'apporter des corrections renforçant la stabilité de l'écosystème de la data science.

## L'impact concret de la recherche en software engineering

Ce travail montre comment une recherche académique, née d'un mémoire de master et affinée par des collaborations internationales, peut avoir un impact immédiat sur des logiciels utilisés par des millions de personnes. Grâce à cette méthode, les bibliothèques logicielles qui servent de fondement à l'IA deviennent plus robustes, montrant que même les outils les plus complexes peuvent être rendus plus sûrs grâce à l'innovation et à la persévérance.

## Bugs identifiés

- https://github.com/numpy/numpy/issues/30495
- https://github.com/scipy/scipy/issues/24217
- https://github.com/scipy/scipy/issues/24216
- https://github.com/pandas-dev/pandas/issues/61753
- https://github.com/numpy/numpy/issues/29299
- https://github.com/scipy/scipy/issues/23272
- https://github.com/tensorflow/tensorflow/issues/96209

-----------------

Cette recherche a été partiellement financée par le projet [CyberExcellence by DigitalWallonia](https://cyberexcellence.be/) (n° 2110186), financé par le Service public de Wallonie (SPW Recherche), ainsi qu’avec le soutien de Wallonie-Bruxelles International (projet RealM).
