---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Innovation pédagogique, café du lundi matin et pratiques de test et qualité logicielle"
subtitle: ""
summary: ""
authors:
    - xavier-devroey
tags: 
  - Education
  - Academic Life
  - Software Quality
  - Software Testing
categories: []
date: 2025-05-01T00:00:00+02:00
lastmod: 2025-05-01T00:00:00+02:00
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

Il y a quelques semaines de ça, le Prof. Benoît Vanderose est arrivé un lundi de bon matin dans mon bureau en me tendant un café et en s’exclamant : "J’ai une super idée pour notre cours de Test et Qualité !" … Ce qui est génial quand on travaille avec quelqu’un comme le Prof. Vanderose, c’est qu’on n’est jamais à court d’idées. Mais quand ces idées concernent un cours que vous avez en commun, cela signifie généralement plus de travail qu’initialement planifié. Mais un cours donné dans la finalité en génie logiciel à des étudiants·es de master en informatique mérite bien cela ! Et nous voilà donc à discuter de comment faire pour faire l’état des lieux des pratiques de test et qualité en Fédération Wallonie Bruxelles.

Deux semaines passent, le premier cours arrive avec les (seuls) six étudiants·es qui ont choisi la finalité et Jérôme Maquoi, notre assistant pour le cours qui n’avait aucune idée de ce que l’on préparait. Nous sommes le 12 février 2025 dans un séminaire : deux profs de la faculté, tout fiers d’avoir une approche différentiée, présentent le résultat de leurs cogitations à ce petit monde. Le plan est simple : on travaille ensemble pour construire un outil de mesure, on contacte nos partenaires industriels pour collecter des données et on produit une première version d’un rapport des pratiques de test et qualité en Fédération Wallonie Bruxelles. Autant dire que l’idée d’avoir des profs qui travaillent directement avec les étudiants·es les a un peu déstabilisés·es… en tout cas, au début. S’en sont suivi une réorganisation de l’espace de travail pour avoir une grande table et un écran sur lequel projeter les documents édités ensemble, une réorganisation de l’espace Teams pour faciliter le partage de documents et d’information et l’instauration de stand-ups au début de chaque séance de cours pour faire l’état des lieux de l’avancement des travaux.

Première étape, faire l’état des lieux au travers de l’état de l’art scientifique et des différents rapports sur le développement d’applications déjà disponibles. Après une semaines de recherche et de lecture, le groupe de travail (car il faut bien nous appeler comme ça) met la main sur le [Rapport 2024 sur l'État de l'Écosystème des Développeurs de JetBrains](https://www.jetbrains.com/fr-fr/lp/devecosystem-2024/), le [State of DevOps Report 2024 d’Accelerate](https://dora.dev/) (qui avait déjà servi pour contextualiser le cours d’Automate Software Engineering au premier quadrimestre), l’[Octoverse 2024 de GitHub](https://github.blog/news-insights/octoverse/octoverse-2024/) et l’[Open Source Monitor France 2023 de Systematic Paris-Region](https://systematic-paris-region.org/download/open-source-monitor-france-rapport-2023/). Nous sommes le 19 février 2025. On décide alors que c’est suffisant pour se donner une idée des sujets à couvrir. On convient de lire les nouveaux rapports et, lors de la séance de cours suivante, on fait une première mise en commun des thématiques. Problème : comment coordonner la mise en commun de trois rapports ?

Les deux heures de cours qui ont suivi ont été assez épiques. Nous sommes le 26 février 2025. La première heure, les étudiants et Jérôme se sont répartis en trois groupes et chaque groupe a dessiné sur un tableau différent une mindmap des sujets couverts par l’un des trois rapports. S’en ai suivi une mise en commun où je me trouvais au centre de la pièce pour avoir une vue sur les trois tableaux (un sur le mur de gauche, un sur le mur de droite et un devant moi), avec mon laptop connecté à un grand écran pour afficher une fenêtre avec la mindmap miro que j’étais en train d’éditer. Et tout ce petit monde à discuter des thématiques rencontrées dans les quatre rapports et les différentes sources, pendant que je prenais des notes. Croyez-moi, c’est beaucoup plus fatigant que de donner un cours magistral sur un sujet bien défini. Toujours est-il qu’à la fin des deux heures, on avait une première version de la carte (map) des sujets potentiels à couvrir pour étudier les pratiques de qualité.

![Mindmap](mindmap.jpeg "")

Nous laissons passer une semaine pour décanter tout ça et le 5 mars 2025, nous reprenons la map tous ensemble pour la discuter, la retravailler et venir avec une seconde version à partir de laquelle définir notre outil de mesure. À ce moment-là, je pense qu’il était assez clair pour tout le monde que l’on allait concevoir un questionnaire, probablement influencé par les différents rapports lus jusque-là. Une nouvelle semaine donc pour réfléchir aux questions : cette fois, les étudiants·es forment 2 groupes, chaque groupe venant avec des questions pour les différentes thématiques. On s’échange les copies lors de la séance de cours du 12 mars pour annoter et commenter les différentes questions. Benoît et moi jouons les relecteurs attentifs en faisant des commentaires sur chacune des deux séries de questions. À la suite de quoi nous demandons aux étudiants de faire une première mise en commun lors de la séance de travaux pratiques du lendemain. Car oui, j’ai oublié de le préciser, mais le deal était que le travail ne doit pas dépasser quatre heures par semaine, soit les deux heures de cours et les deux heures de travaux pratiques allouées. Le 13 mars vers 12h, nous avons donc une première liste de questions divisées par thématiques. C’est pas mal du tout pour une première. 

18 mars 2025, c’est la semaine blanche durant laquelle il n’y a pas cours. Benoît et moi avons dit aux étudiants que l’on prenait le relais pour tailler dans la liste de questions car 32 pages, c’est beaucoup. Nous voilà donc avec un appel Teams et un écran partagé à repasser sur les différentes questions pour réorganiser tout ça en un questionnaire que l’on pourra envoyer aux entreprises.

Enfin, le 24 mars 2025 une première version de l’enquête est encodée dans Drag’n Survey (la plateforme que l’on utilise à l’UNamur). Après quelques aléas suite à la prise en main de la plateforme, le questionnaire est prêt pour un premier essai. Corrections et re-corrections à la suite des retours de quelques personnes soigneusement choisies et, le 10 avril, on se revoit tous avec les étudiants pour lancer l’enquête.

Bien des mois plus tard, nous avons enfin publié le [rapport complet](https://snail.info.unamur.be/publication/snailreport-2025/) et un [executive summary](https://snail-unamur.github.io/snailreport/) en ligne.
