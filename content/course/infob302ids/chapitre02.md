---
title: Bibliographie 
date: '2025-09-15'
type: book
weight: 20
summary: Une fois le sujet de recherche choisi, la première étape consiste à étudier l'état de l'art en faisant une recherche bibliographique.
---

{{< toc hide_on="xl" >}}

Une fois le sujet de recherche choisi, la première étape consiste à étudier l'état de l'art en faisant une recherche bibliographique. Un bon état de l'art est essentiel pour plusieurs raisons :

- Se familiariser plus en profondeur avec le sujet traité. En identifiant le contexte, le ou les problèmes traités, ainsi que les contributions déjà réalisées et leurs limitations les scientifiques acquièrent une meilleure compréhension du sujet. Cela clarifie la manière dont il pourra le traiter et faire avancer la science. Cette partie est souvent appelé *Background* dans les articles scientifiques et introduit les concepts nécessaires à la compréhension du sujet traité.
- Positionner sa contribution par rapport l'état de l'art. Afin de délimiter clairement la contribution et que d'autres scientifiques puissent comprendre le paysage de la recherche sur le sujet traité. Ce positionnement (souvent appelé *Related work* dans les articles scientifiques) permet également de plus facilement identifier les pistes de recherche future pour le sujet traité.

Le reste de cette section couvre les étapes principales d'une recherche bibliographique et de l'analyse d'une liste d'articles (potentiellement) intéressants pour définir l'état de l'art d'un domaine de recherche. Il est important de souligner que ces étapes ne sont pas nécessairement séquentielles et peuvent se faire de manière itérative : par exemple, identifier un petit ensemble d'articles, analyser leur pertinence et revenir vers un moteur de recherche bibliographique pour trouver d'autres articles.

## Moteurs de recherche bibliographique

Le moyen le plus simple de trouver des références bibliographiques est d'utiliser un moteur de recherche dédié. Il en existe de plusieurs sortes, nous listons ici les principaux utilisés dans la recherche en informatique :

- [Google Scholar](https://scholar.google.com) est probablement le moteur de recherche le plus répandu et le plus utilisé par les scientifiques. Il faut toutefois se méfier car il a tendance à indexer tout document, indépendamment de sa nature (article publié, rapport de recherche non revu par les pairs, dataset, etc.).
- [Microsoft Academic](https://academic.microsoft.com) est le moteur de recherche équivalent à Scholar développé et maintenu par Microsoft.
- [Scopus](https://www.scopus.com/) est un moteur de recherche payant, accessible si vous êtes connecté depuis le réseau de l'UNamur ou via un accès à distance (utilisez l'option *Sign in via your institution*). Plus avancé que Scholar et Academic, Scopus offre différentes options pour faire une recherche (par mots clés, titre, résumé, etc.).

À côté des moteurs de recherche généraux, on trouve aussi les moteurs de recherche des différents éditeurs scientifiques, actifs dans la recherche en informatique. Ces moteurs de recherche sont spécialisés, mais ne fourniront que les articles publiés par l'éditeur :

- [ACM Digital Library](https://dl.acm.org), le moteur de recherche de l'ACM.
- [IEEEXplore](https://ieeexplore.ieee.org/), le moteur de recherche de l'IEEE.
- [ScienceDirect](https://www.sciencedirect.com), le moteur de recherche d'Elsevier.
- [Springer Link](https://link.springer.com), le moteur de recherche de Springer.

{{< callout note >}}
**Les bases de données bibliographiques telles que [DBLP](https://dblp.org) permettent d'avoir des références bibliographiques propres.** Il est vivement conseillé de télécharger vos références depuis ces bases de données. Les logiciels de gestion de bibliographie (Zotero, JabRef) vous permettent d'importer des références facilement (soit via un fichier, soit directement en copiant/collant l'entrée au format BibTex).
{{< /callout >}}

### Accéder à un article

L'accès aux articles n'est pas toujours simple et dépends de l'éditeur et des options de publication choisies par les auteurs. On en parlera plus en détail dans le [chapitre sur l'Open Science](../chapitre10/), mais voici quelques éléments pratico-pratiques pour trouver un article :

- Vérifier que l'article n'est pas accessible sur le site de l'éditeur. Soit parce que les auteurs ont payé un *article processing charge* que l'article soit accessible en *open-access*. Soit parce que l'université a payé un abonnement à l'éditeur pour avoir accès à ses publications. C'est le cas pour les articles sur [ScienceDirect](https://www.sciencedirect.com) à l'Université de Namur. À noter qu'à partir du 1er janvier 2026, tous les articles de l'[ACM Digital Library](https://dl.acm.org) ont été rendus disponibles en open access.
- Pour les articles non disponibles directement sur le site de l'éditeur, il sont parfois accessibles sur le site web de l'auteur ou de son institution. Le moyen le plus rapide pour vérifier la disponibilité de l'article est de passer par [Google Scholar](https://scholar.google.com), d'entrer le nom de l'article et de voir si un lien vers un PDF apparaît à la droite de l'entrée.

![Google Scholar example - article available](exemple-scholar-pdf.jpg)

- Enfin, il existe aussi des extensions telles que [Unpaywall](https://unpaywall.org/products/extension) pour pouvoir lancer une recherche et télécharger une version accessible d'un article.

## Identifier les mots clés

La qualité des mots clés identifiés est essentielle pour s'assurer que l'on n'omet pas un pan entier de la littérature dans son état de l'art. Pour compliquer le tout, il n'est pas rare que des sous-domaines de recherche utilisent des synonymes pour désigner des éléments similaires (par exemple, education et teaching) ou au contraire, utilisent le même mot pour désigner des concepts différents (par exemple, feature en ingénierie des exigences, en Software Product Line engineering et en machine learning). Identifier les mots clés utilisés pour la recherche ne se fait généralement pas en une fois, en particulier pour des scientifiques débutant·e·s.
Une bonne tactique visant à construire une requête efficace pour interroger un moteur de recherche repose sur différents éléments, parmi lesquelles :

1. Partir d'une description générale du domaine de recherche. [Wikipedia](https://www.wikipedia.org) est votre amis ... plus que ChatGPT en tout cas (on parlera de l'utilisation d'outils propulsés par l'IA pour la recherche un peu plus loin).
2. Partir d'une liste d'articles reconnus du domaine, cette liste peur vous être donnée par un scientifique plus expérimenté (n'hésitez jamais à demander de l'aide 😉), transmise par des scientifiques menant une recherche dans le domaine ou venir d'une précédente revue systématique de la littérature.
3. Identifier dans la description et les articles à disposition quelques mots clés qui semblent pertinent en se basant sur les titres, les résumés et, éventuellement les états de l'art (background et related work) des articles.
4. Mettre à jour la requête sur base des nouveaux mots clés identifiés et voir si les résultats renvoyés par le moteur de recherche sont mis à jour.
5. **Itérer à l'étape 3** jusqu'à ce que les résultats retournés se stabilisent ou que les nouvelles publications ne font plus sens pour le domaine de recherche visé (auquel cas il est peut-être nécessaire de retirer certains mots clés).

## Le snowballing

Le snowballing est une technique couramment utilisée une fois que l'on a identifié quelques articles pertinents pour un état de l'art. Le principe est de lister les articles qui citent ou sont cités par un article donné. La liste des articles cités est accessible dans la liste des références à la fin de l'article (il est souvent plus facile d'y accéder via la version électronique de l'article sur le site web de l'éditeur). Les articles qui citent un article donné sont plus difficile à trouver. Heureusement, les moteurs de recherche comme Google Scholar permettent de retrouver cette information facilement.

![Google Scholar example - list references citing an article](exemple-scholar-citedby.jpg)

Le snowballing permet de rapidement identifier un ensemble d'articles appartenant à un domaine de recherche s'il est utilisé à partir de quelques références données. Cet ensemble peut, par la suite, être utilisé pour identifier des mots clés comme expliqué dans la section précédente. S'il est utilisé plus tard dans l'identification de l'état de l'art, le snowballing permet de s'assurer qu'un état de l'art est (relativement) complet et n'a pas omis des articles pertinents.

## Inclure ou exclure un article

La décision d’inclure ou d’exclure une publication ou un article dans un état de l’art dépends de plusieurs critères. Certains de ces critères sont liés au contenu de l’article (l’article décrit-il un élément pertinent du domaine de recherche considéré ?), mais d’autres sont liés à sa nature (un article qui n’est pas passé par un processus de revue par les pairs doit-il être inclus ? un livre traitant du domaine ? un rapport technique ? une thèse de doctorat ? etc.). Il est important de garder ces critères à l’esprit lors de la réalisation d’un état de l’art.

Une technique classique afin de trier rapidement un ensemble d’articles obtenus via un moteur de recherche bibliographique consiste en :

- Lire le titre, le résumé (*abstract*) et les mots clés de l’article pour décider si oui ou non il traite d’un sujet pertinent pour l’état de l’art.
- En cas de doute, lire l’introduction (et éventuellement la conclusion) pour confirmer ou non la pertinence et identifier les éventuels nouveaux mots clés intéressant pour la recherche.

{{< callout note >}}
**Pour simplifier et évacuer la question de la nature des articles à utiliser pour votre état de l’art, il est plus facile de ne considérer que les articles qui ont suivi un processus de revue par les pairs (*peer-reviewed*).** Cette information est généralement disponible sur le site de l’éditeur (publié dans les actes d’une conférence ou dans un journal). Un article qui n’a pas été peer-reviewed est donc exclu d’emblée. Cette approche peut être modulée pour les sujets de pointe, mais il faut alors considérer les articles non revus pas les pairs avec attention et prendre quelques précautions d'écriture (par exemple, ne pas les utiliser pour supporter une hypothèse fondamentale à la recherche).
{{< /callout >}}

## Gérer les références et articles trouvés

Ce n'est pas tout de trouver des articles, il est aussi nécessaire de pouvoir les classer, les gérer et les retrouver facilement. Pour cela nous conseillons vivement d'utiliser un gestionnaire bibliographique tel que [Zotero](https://www.zotero.org) ou [JabRef](https://www.jabref.org). Dans la labo, nous utilisons Zotero car il dispose de fonctionnalités de partage (pratique pour les travaux à plusieurs) et d'autocomplétion des métadonnées (on ajoute un PDF et Zotero crée l'entrée automatiquement). Il y a une règle d'or à respecter :

{{< callout note >}}
**Quoi que vous fassiez, ayez toujours une base de donnée bibliographique avec des références propres (c'est-à-dire, des métadonnées correctes) !** Ne pas avoir une bibliographie propre est une erreur que beaucoup de chercheurs (y compris senior) font. Ils se retrouvent alors à devoir corriger leur bibliographie manuellement, généralement quelques heures avant une deadline . Pour les mémorants et les doctorants, c'est même pire, car les références ont tendance à évoluer au fil du temps et l'on se retrouve alors avec des entrées dupliquées dans la bibliographie qu'il faut alors nettoyer et corriger (et c'est pénible 🙄).
{{< /callout >}}

## Outils supplémentaires pour la recherche de références

Il existe un certain nombre d'outils permettant de faciliter la recherche (y compris via snowballing), plusieurs d'entre eux intégrant des outils propulsés par l'IA. ⚠️ Attention à l'utilisation de ces outils : comme tous les outils propulsés par l'IA, ils sont aussi bons que les données sur lesquelles ils ont été entraînés (*crap in - crap out*). Vérifier les références sur une base de donnée de référence comme [DBLP](https://dblp.org) évitera pas mal d'ennuis.

- [Connected Papers](https://www.connectedpapers.com) permet de visualiser les citations sous forme de graphe (5 graphes par mois dans la version gratuite).
- [ResearchRabbit](https://app.researchrabbit.ai) permet de visualiser les citations sous forme de graphe. La version gratuite permet déjà de faire un grand nombre de choses.
- [Consensus](https://consensus.app) permet d'avoir un rapide aperçu de l'état de l'art d'un sujet donnée sur base d'une phrase ou d'une question. Le problème est que sans un minimum de connaissance du domaine de recherche visé, il est difficile de savoir quels mots clés utiliser ou quelle question poser (ou de voir si le résultat généré est cohérent avec l'état de l'art que vous voulez explorer).
- [Perplexity Academic](https://www.perplexity.ai/academic) est une version spécialisé de Perplexity. À nouveau, à utiliser avec précaution, la réponse dépendra de l'utilisation des bons mots clés du domaine de recherche.

si vous en connaissez d'autres, n'hésitez pas à nous contacter, on les ajoutera à la liste. 😉
