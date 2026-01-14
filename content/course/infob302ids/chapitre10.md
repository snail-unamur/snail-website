---
title: Open Science
date: '2025-09-15'
type: book
weight: 100
summary: Ce chapitre décrit et discute les bonnes pratiques relatives à l'open science dans la recherche en informatique.
---

{{< toc hide_on="xl" >}}

## Qu'est-ce que l'Open Science ?

D'après l'[UNESCO](https://unesdoc.unesco.org/ark:/48223/pf0000383323_fre), l'open science est "*un ensemble de principes et de pratiques qui visent à rendre la recherche scientifique, dans toutes les disciplines, accessible à tous, au profit des scientifiques et de la société dans son ensemble.*" Cette définition va au-delà de l'acception commune de l'open science qui se limite à rendre accessible les résultats issus de la recherche scientifique. Le but ici est de rendre les connaissances scientifiques accessibles, mais aussi que la production de ces connaissances soit elle-même inclusive, équitable et durable. En favorisant une science plus accessible, inclusive et transparente, l'open science vise à ce que chacun·e puisse participer au progrès scientifique et en bénéficier, conformément au paragraphe 1 de l’article 27 de la [Déclaration universelle des droits humains](https://www.un.org/fr/about-us/universal-declaration-of-human-rights).

Selon cette définition, l'opens science regroupe différentes pratiques visant à :

- rendre les connaissances scientifiques multilingues, librement accessibles à toutes et tous et réutilisables ;
- renforcer la collaboration scientifique et le partage des informations au profit de la science et de la société ;
- ouvrir les processus de création, d’évaluation et de diffusion des connaissances scientifiques à la société au-delà de la communauté scientifique traditionnelle.

Pour rendre cela possible, l'open science repose sur les piliers suivants :

![Pillars of Open Science, UNESCO (2021)](unesco.png)

Dans la suite de ce chapitre, nous nous concentrerons principalement sur le processus de création, d’évaluation et de diffusion des connaissances scientifiques dans la recherche en informatique et les bonnes pratiques concernant ce processus en terme d'open science.

### Bénéfices pour la recherche

Les bénéfices de l'open science sont de plus en plus reconnus. D'un point de vue pratique, les effets observés sont :

- une augmentation du nombre d'accès et de citations des publications ;
- une facilitation du transfers technologique vers l'industrie;
- une augmentation des collaborations autours de dépôts ouverts (open repositories) comme GitLab, GitHub, etc..

L'open science a aussi relancé le débat sur les coûts liés aux abonnements à des périodiques et des bibliothèques en ligne comme ACM DL, IEEEXplore, ScienceDirect, etc. Rendre les publications accessible permet en effet de diminuer ces coûts pour les universités et de rendre les articles accessible aux chercheurs et professionnels du monde industriel gratuitement.

Attention, il est important de souligner ici que **open science ne veut pas dire gratuit** à tous les niveaux ou **sans contrôle**. Le contrôle peut se faire de différente manière (par exemple, donner accès à des données sur demande avec justification) et les infrastructures permettant de mettre en place des pratique d'open science ont un coût qui doit être assumé d'une manière ou d'une autre (par exemple, [OpenAIRE](https://www.openaire.eu/) est l'infrastructure de soutien à l'open science européenne, financée par des fonds publics).

## *Open source*

L'open source est bien connu en informatique. Le même principe s'applique pour du logiciel développé dans le cadre de la recherche, que ce soit des prototypes ou du logiciel scientifique pour, par exemple, faire de l'analyse de données. On distingue différents types de licences, parmi lesquelles :

- la [MIT licence](https://choosealicense.com/licenses/mit/), une des licenses les plus libres au niveau de ses permissions. Cette license est souvent utilisée pour les prototypes de recherche car elle est préférée par les industriels et facilite le transfert vers l'industrie.
- la [GPLv3](https://choosealicense.com/licenses/gpl-3.0/) est une license dite *contaminante* pour laquelle il est nécessaire de repartager tout logiciel qui utilise lui-même du logiciel sous license GPL.
- la [GNU LGPLv3](https://choosealicense.com/licenses/lgpl-3.0/) est une variante de la GPLv3 permettant d'utiliser le logiciel comme une librairie (externe) sans contaminer le logiciel utilisateur.

Une bonne pratique consiste, lors de la soumission d'une publication, à fournir un lien vers un dépôt du logiciel. Attention que, en cas de revue en double aveugle, celui-ci doit être anonymisé, par exemple, via l'outils [Anonymous GitHub](https://anonymous.4open.science).

## *Open methodology*

Le but est ici permettre à d'autres chercheurs de pouvoir reproduire les résultats, éventuellement dans un contexte différent. Cette reproduction est essentielle pour permettre à la connaissance d'avancer en enrichissant la connaissance empirique que l'on a d'un objet d'étude.

Les méthodes ouvertes impliquent une **description complète et transparente des méthodologies de recherche**, y compris la description détaillée du dispositif expérimental, de la manière dont les données ont été collectées et analysées (manuellement pour des données qualitatives et via des outils statistiques pour les données quantitatives). L'idée est d'aller au delà de la description fournie (partiellement) dans un article scientifique pour également fournir la description détaillée des étapes d'analyse, les éventuels scripts automatisant cette analyse, les guides d'analyse (par exemple, le guide décrivant comment les données qualitatives ont été codées), etc.

Cette description qui fait alors partie d'un *artifact* peut-être elle même revue par les pairs. Par exemple, l'[ACM a défini un ensemble de badges](https://www.acm.org/publications/policies/artifact-review-badging) pour reconnaître le niveau de maturité d'un artefact.

- **Artefact disponible**, indique que l'artefact est accessible sur une plateforme ouverte telle que [Zenodo](https://zenodo.org) et qu'il dispose d'un *Digital Object Identifier* (DOI) permettant de l'identifier de manière unique.
- **Artefact fonctionnel**, indique que l'artefact est documenté, complet et peut être exécuté.
- **Artefact réutilisable**, indique que l'artefact est non seulement fonctionnel, mais que sa qualité (documentation, code, etc.) permet de le réutiliser dans un autre contexte de recherche.

À noter qu'un artefact fonctionnel ou réutilisable n'est pas nécessairement disponible librement. C'est souvent le cas lorsqu'une recherche implique des données sensibles ou du code source propriétaire. Les pairs en charge de la revue de l'artefact s'engagent alors à ne pas le diffuser et à l'effacer une fois la revue effectuée.

## *Open data*

Les données ouvertes dans le cadre de la recherche scientifique permettent peuvent prendre plusieurs formes. Il peut s'agir des données brutes récoltées lors d'une expérience ou encore d'une jeu de données (dataset) qui a déjà subi un prétraitement pour nettoyer, normaliser, formater, [anonymiser](https://journals.sagepub.com/doi/10.1177/1468794114550439), etc. des données.

La distribution de données ouvertes peut se faire de différentes manières : la plus courante est de passer par une plateforme ouverte telle que [Zenodo](https://zenodo.org). Il se peut aussi que pour des raisons de confidentialité, seules les métadonnées (les données décrivant les données du jeu de données) soient librement accessibles. L'accès aux données se fait alors sur demande et de manière encadrée.

Dans tous les cas, pour être librement accessible, les données ouvertes doivent respecter le [principe FAIR](https://force11.org/info/the-fair-data-principles/) :

### Trouvable (Findable)

- **F1** : Les (méta)données se voient attribuer un identifiant unique (au niveau mondial) et persistant (par exemple, un DOI).
- **F2** : Les données sont décrites à l'aide de métadonnées riches.
- **F3** : Les (méta)données sont enregistrées ou indexées dans une ressource consultable (par exemple, un dépôt ouvert).
- **F4** : Les métadonnées spécifient l'identifiant des données.

### Accessible

- **A1** : Les (méta)données sont récupérables à l'aide de leur identifiant grâce à un protocole de communication normalisé (par exemple, en passant par <https://www.doi.org>).  
  Le protocole est ouvert, libre et universellement applicable et permet une procédure d'authentification et d'autorisation, si nécessaire.
- **A2** : Les métadonnées sont accessibles, même lorsque les données ne sont plus disponibles.

### Interopérable

- **I1** : Les (méta)données utilisent un langage formel, accessible, partagé et largement applicable pour la représentation des connaissances.
- **I2** : Les (méta)données utilisent un ou des vocabulaires qui respectent les principes FAIR.
- **I3** : Les (méta)données comprennent des références qualifiées à d'autres (méta)données.

### Réutilisable

- **R1** : Les (méta)données possèdent une pluralité d'attributs précis et pertinents, y compris une licence d'utilisation claire et accessible, indiquent leur provenance et répondent aux normes communautaires pertinentes pour le domaine concerné.

### Licences d'utilisation ouverte

Il existe plusieurs [licenses d'utilisation ouvertes](https://creativecommons.org/share-your-work/cclicenses/). Les plus courantes sont les *Creative Commons* (CC) qui constituent un modèle de licence publique visant à faciliter l'octroi d'autorisations de droits d'auteur pour les oeuvres publiées. 

Les deux licences Creative Commons les plus utilisées sont la licence du domaine public ([CC0 Public Domain Dedication](https://creativecommons.org/publicdomain/zero/1.0/)) et la licence d'attribution ([CC-BY](https://creativecommons.org/licenses/by/4.0/)). La première est une licence qui met en oeuvre le véritable domaine public, agissant effectivement comme une renonciation à tout droit d'auteur. La seconde est une licence ouverte qui permet la réutilisation et la redistribution de l'artefact à la seule condition d'attribuer l'oeuvre originale à ses auteurs.

Certaines licenses permettent également d'empêcher l'utilisation des données dans un contexte commercial ou empêchent de dériver d'autres données. Il faut faire attention lorsque l'on décide d'appliquer ces licenses car elles compliquent la réutilisation des données dans d'autres contextes de recherche.

Un [outils](https://creativecommons.org/chooser/) est disponible pour aider au choix d'une license.

## *Open review*

La revue par les pairs ouverte (*open review*) est l'un des modèles existant de [revue par les pairs](/course/infob302ids/chapitre06/) qui vise à rendre le processus le plus transparent possible. Ce type de modèles permet d'ouvrir différents aspects de la revue et est déjà implémenté par plusieurs conférences et journaux via des plateformes comme <https://openreview.net>.

### Identités ouvertes

Dans ce modèle, l'identité des auteurices et des évaluateurices est dévoilée (publiquement ou uniquement aux autres parties impliquées) à un moment du processus de review. Par exemple, une fois les rapports rentrées, les identités sont rendues visibles pour qu'une discussion puisse s'engager. Sur base de ces rapports et de cette discussion, l'éditeur peut prendre une décision sans avoir à préserver le secret des identités des différentes parties prenantes.

Une fois la publication acceptée, les identités des évaluateurices peuvent être révélées publiquement (c'est encore assez rare) ou non.

### Rapports d'évaluations ouverts

Une fois l'article publié, il est également possible de demander aux évaluateurices si iels désirent rendre leurs rapports publics. Dans ce cas, l'article sera accompagné de ces rapports (et des réponses des auteurices).

### Participations ouvertes

Enfin, il est également possible d'avoir un modèle dans lequel une publication (ou un jeu de données ou un artefact) est laissé à la libre évaluation par des évaluateurices volontaires. Dans ce cas, l'élément évalué doit être accessible publiquement et les évaluateurices doivent pouvoir se porter volontaires pour faire l'évaluation. Cette évaluation peut elle même prendre la forme d'une évaluation complète ou de (plus simples) commentaires détaillés.

Par exemple, la plateforme [PubPeer](https://pubpeer.com) permet de commenter et d'évaluer des résultats de recherche scientifique publiés. C'est notamment via cette plateforme que la chercheuse néerlandaise [Elisabeth Bik](https://en.wikipedia.org/wiki/Elisabeth_Bik) a rapporté plus de 4,000 cas de manipulations de photos dans des publications scientifiques.

## *Open access*

L'open access (ou accès ouvert) est un ensemble de principes qui permettent de mettre à disposition du public des articles scientifiques publiés sans restriction d'accès (payant ou non). Lorsque l'on parle d'Open Science, l'open access est en général la première chose à laquelle on pense.

Dans un modèle de publication classique sans open access, une fois publié chez un éditeur commercial, l'article est accessible aux lecteurs contre rémunération soit pour l'article, soit via un abonnement payé par l'institution de recherche à laquelle le lecteur est rattaché.

Dans un modèle open access, une publication publiée chez un éditeur commercial pourra être accessible ouvertement soit chez l'éditeur au moment de sa publication, on parle alors de **gold open access**. Soit dans un dépôt ouvert après une période d'embargo, on parle alors de **green open access**. En gold open access, plutôt que de faire payer l'accès, l'éditeur commercial demandera aux auteurs de payer des frais de publication (*Article Processing Charges - APC*) uniques. En green open access, il est de la responsabilité des auteurs de rendre leur publication accessible via un dépôt ouvert (par exemple, [arXiv](https://arxiv.org)) après une période d'embargo (1 an, en général). Ces éléments sont résumés ci-dessous.

![Typical publishing workflow for an academic journal article (preprint, postprint, and published) with open access sharing rights per SHERPA/RoMEO](openaccess.png)

Enfin, certaines revues publient ouvertement et directement un article accepté sans contrepartie financière pour les auteurs. On parle alors de **diamond open access**. Ces revues (beaucoup plus rares) sont en général rattachées à des institutions (en général, financées par de l'argent public) jouant le rôle d'éditeur commercial.

### Droit de publication secondaire

La loi belge permet aux chercheureuses un *droit de publication secondaire* (*Secondary Publication Right - SPR*) par lequel iels conservent le droit :

- de mettre en libre accès le manuscrit d'un article scientifique, après un délai de *12 mois après publication* pour les sciences humaines et sociales et de *6 mois* pour les autres sciences,
- quel que soit le contrat signé avec l’éditeur pour tout article issu d’une recherche *financée au moins pour moitié par des fonds publics*, y compris les articles publiés avant l’entrée en vigueur de cet article de loi (15-09-2018).

La notion de "manuscrit" vise également une version digitale de l'article. La version qui peut être rendue accessible au public en libre accès est la version *postprint*, à savoir la version finale présentée par l'auteur, après la révision par les pairs, telle qu'acceptée pour publication. (Avis de l'Office belge de la Propriété Intellectuelle, transmis à la Ministre Glatigny, juillet 2022).

Ce droit est impératif et d’application nonobstant le droit choisi par les parties dès lors qu’un point de rattachement est localisé en Belgique. ([Code de droit économique, Livre XI, article XI.196 §2.1](https://www.ejustice.just.fgov.be/cgi_loi/article.pl?language=fr&sum_date=&pd_search=2013-03-29&numac_search=2013A11134&page=1&lg_txt=F&caller=list&2013A11134=0&trier=promulgation&dt=CODE+DE+DROIT+ECONOMIQUE&fr=f&choix1=et#Art.XI.196))

### En Fédération Wallonie-Bruxelles

La Fédération Wallonie-Bruxelles (FWB) a voté un [Décret visant à l'établissement d'une politique de libre accès aux publications scientifiques (Open Access)](https://gallilex.cfwb.be/textes-normatifs/45142), entré en vigueur à la rentrée académique 2018-2019. Il implique que tout chercheur financé par des fonds publics **doit déposer en libre accès dans une archive institutionnelle**, le texte complet de ses publications parues dans un périodique. Ce décret repose sur le principe que la diffusion des résultats de la recherche financée par des subventions publiques permet non seulement la libre circulation du savoir et ainsi l'innovation mais il accroît également la visibilité des chercheurs, et l'accessibilité et l'impact de leurs travaux.

La FWB s'aligne ainsi sur les politiques de libre accès d'autres bailleurs de fonds comme le F.R.S-FNRS et la Commission européenne. À noter que certains bailleurs de fonds, comme le FNRS, *exigent* que la liste des publications soit tirée de l'archive institutionnelle.

L'Université de Namur dispose, comme toutes les autres universités de la fédération, d'une [politique institutionnelle en matière d'open access](https://www.unamur.be/fr/institution/positionnement-institutionnel/open-access), requérant que les publications, thèses, mémoires, etc. soient encodés dans l'outils [PURE](http://pure.unamur.be).

## *Open educational resources*

La dernière catégorie concerne la dissémination du savoir avec la création de ressources ouvertes pour l'éducation. Tout comme les artefacts, ces ressources doivent pouvoir être accessibles publiquement avec une license permettant leur utilisation dans différents contextes. À nouveau, les [licenses d'utilisation ouvertes](https://creativecommons.org/share-your-work/cclicenses/) sont un bon choix pour permettre une diffusion large de ces ressources.

## Resources additionnelles

- Mendez, D., Graziotin, D., Wagner, S., & Seibold, H. (2020). [Open science in software engineering](https://doi.org/10.1007/978-3-030-32489-6_17). In Contemporary empirical methods in software engineering (pp. 477-501). Cham: Springer International Publishing.
- [Open Science](https://www2.sigsoft.org/EmpiricalStandards/docs/supplements?supplement=OpenScience#) supplement des ACM SIGSOFT Empirical Standards permettant de vérifier la qualité d'un artefact ouvert.
- [Choose an open source license](https://choosealicense.com) permet d'avoir une vue synthétique des différentes licenses logiciel open source et de ce qu'elles autorisent ou non.

### Dépôts ouverts

- [PURE](http://pure.unamur.be), le dépôt institutionnel de l'Université de Namur.
- [PeriScops](https://periscops.be), le portail des publications scientifiques en Fédération Wallonie-Bruxelles.
- [Zenodo](https://zenodo.org), le dépôt de publications, d'archives et de données ouvertes de l'Europe. Il dispose d'une [intégration avec GitHub](https://help.zenodo.org/docs/github/) permettant d'automatiquement mettre à jour un dépôt Zenodo lors d'une *release* sur GitHub.
- [Software Heritage archive](https://archive.softwareheritage.org), un dépôt sauvegardant les repository GitHub, GitLab, SourceForge, etc. et permettant d'ajouter et de sauvegarder du code source issue d'autres repositories.
- [arXiv](https://arxiv.org), archive d'articles scientifiques en open access.

### Plateformes d'évaluation ouvertes

- [PubPeer](https://pubpeer.com), une plateforme permettant l'évaluation via participation ouverte de résultats de recherche.
- [OpenReview.net](https://openreview.net), une plateforme d'open review utilisée par un grand nombre de journaux et conférences en informatique.
