---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Energy Codesumption : Quand les constructeurs Java interrogent l'empreinte énergétique du code"
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
date: 2026-05-17T14:50:00+02:00
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

Cette année, le cours de Test et Qualité a offert à Anas Damlakhi, Robin Delvaux, Edwyn Eben et Julien Jamoulle l’opportunité de contribuer directement à la recherche en génie logiciel, en collaboration avec l'équipe SNAIL. Le projet, baptisé Energy Codesumption, s'inscrit dans la continuité d'[une étude](https://snail.info.unamur.be/publication/maquoi-2025/) publiée et présentée lors du workshop DevOpsSustain, au sein de la conférence FSE 2025 à Trondheim en juin 2025. Cette recherche, menée par Jérôme Maquoi, pose une question fondamentale : comment le code source d'un projet Java affecte-t-il la consommation énergétique de ce projet ? La problématique est d'actualité : la communauté du génie logiciel reconnaît de plus en plus la durabilité comme un domaine de recherche clé, mais les développeur.euse.s manquent souvent de connaissances sur les stratégies efficaces pour réduire l'empreinte énergétique de leurs applications.

## De l'intuition scientifique à la validation empirique

L'étude initiale a révélé un lien prometteur entre la consommation énergétique du code source et le nombre d'attributs d'objets créés dans ce code. Pour vérifier cette hypothèse, les chercheurs ont utilisé [JoularJX](https://github.com/joular), un outil d'état de l'art conçu pour surveiller la consommation d'énergie des projets Java au niveau du code source. L'approche consiste à exécuter les suites de tests des projets tout en mesurant la consommation d'énergie associée à chaque branche d'exécution. Deux projets Java ont été analysés : Spoon, une bibliothèque open source pour l'analyse et la transformation du code Java, et Spring Boot, un framework largement adopté pour la création d'applications autonomes. Les résultats préliminaires suggèrent que six des sept constructeurs les plus consommateurs d'énergie ont produit entre 181 et plus de 500 attributs, tandis que les moins énergivores n'en ont généré que de zéro à quarante et un.
La contribution des étudiants à la chaîne de recherche

Le projet Energy Codesumption confié aux étudiants vise à étendre cette analyse initiale. Leur mission consiste à prendre en main l'outil développé par Jérôme Maquoi, à sélectionner des projets Java pertinents et à exécuter l'analyse afin de récupérer les données énergétiques ainsi que celles liées aux constructeurs. Le résultat est un jeu de données ouvert, reprenant le code des projets analysés ainsi que les mesures de consommation d'énergie générées par l'outil. Cette exigence garantit que les travaux produits pourront servir de base à de futures recherches et contribuer à la science ouverte.

## Une méthodologie rigoureuse pour des résultats fiables

La démarche expérimentale adoptée dans ce projet suit les meilleures pratiques de la communauté de recherche. Les mesures énergétiques, même effectuées sur le même ordinateur, peuvent être influencées par divers facteurs environnementaux. Pour y remédier, l'équipe fige les configurations du système, s'assure que seul le logiciel étudié s'exécute et effectue un préchauffage de cinq minutes avant les mesures. Chaque suite de tests est exécutée trente fois pour tenir compte de la variabilité aléatoire, avec une période de refroidissement d'une minute entre chaque exécution afin d'éviter que l'augmentation de la température n'entraîne une consommation énergétique artificiellement élevée. Ces précautions méthodologiques sont essentielles pour obtenir des données comparables et scientifiquement valides.

## Des défis techniques et un apprentissage par la pratique

Le parcours des étudiants n'a pas été exempt de difficultés. L'immersion dans le code de l'outil et la compréhension de ses mécanismes ont nécessité une approche pragmatique, avec l'assistance d'outils d'intelligence artificielle pour décrypter les arcanes du projet. Les étudiants ont également fait preuve d'honnêteté intellectuelle en reconnaissant leurs limites techniques, notamment face à la gestion complexe des sous-modules pour prendre les mesures, un défi qui a constitué un point de blocage à surmonter. Cette transparence souligne la nature réelle de l'apprentissage : la maîtrise technique s'acquiert par la confrontation à des problèmes concrets, et la reconnaissance des difficultés constitue une étape essentielle de la progression professionnelle.

## Vers une ingénierie logicielle plus consciente

À l'issue de leur travail (et de plusieurs semaines d’exécution de code), l'équipe a produit l’[analyse complète de deux projets Java et a publié son jeu de données sur la plateforme Zenodo](https://doi.org/10.5281/zenodo.19481968), qui lui a attribué un identifiant DOI permanent. Au-delà de la collecte de données, les étudiants ont également apporté des contributions directes à l'outil de Jérôme Maquoi, améliorant ainsi l'infrastructure de recherche elle-même. Le projet Energy Codesumption illustre parfaitement la synergie entre la formation académique et la recherche de pointe. En confrontant les étudiants à une problématique de recherche ouverte, le cours de Test et Qualité leur a permis de contribuer activement à l’avancement de la connaissance scientifique. Les résultats sont désormais accessibles à tous via Zenodo, invitant la communauté scientifique à poursuivre l'investigation sur ce sujet crucial. Que l'intuition initiale soit confirmée ou infirmée par des analyses plus poussées, la démarche elle-même constitue une avancée : elle invite les développeur.euse.s à considérer la complexité de leur code non seulement sous l'angle de la maintenabilité, mais aussi sous celui de l'efficacité énergétique.
