---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: Generating Class-Level Integration Tests Using Call Site Information
subtitle: ''
summary: ''
authors:
- Pouria Derakhshanfar
- xavier-devroey
- Annibale Panichella
- Andy Zaidman
- Arie van Deursen
tags:
- Search-Based Software Testing
categories: []
date: '2022-10-14'
lastmod: 2022-10-18T08:07:30+02:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ''
  focal_point: ''
  preview_only: false

# links:
# - name: ""
#   url: ""
url_pdf: 'https://xdevroey.be/publication/derakhshanfar-2022-b/derakhshanfar-2022-b.pdf'
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
publishDate: '2022-10-18T06:07:30.235518Z'
publication_types:
- '2'
abstract: Search-based approaches have been used in the literature to automate the
  process of creating unit test cases. However, related work has shown that generated
  tests with high code coverage could be ineffective, i.e., they may not detect all
  faults or kill all injected mutants. In this paper, we propose Cling , an integration-level
  test case generation approach that exploits how a pair of classes, the caller and
  the callee, interact with each other through method calls. In particular, Cling
  generates integration-level test cases that maximize the Coupled Branches Criterion
  (CBC). Coupled branches are pairs of branches containing a branch of the caller
  and a branch of the callee such that an integration test that exercises the former
  also exercises the latter. CBC is a novel integration-level coverage criterion,
  measuring the degree to which a test suite exercises the interactions between a
  caller and its callee classes. We implemented Cling and evaluated the approach on
  140 pairs of classes from five different open-source Java projects. Our results
  show that (1) Cling generates test suites with high CBC coverage, thanks to the
  definition of the test suite generation as a many-objectives problem where each
  couple of branches is an independent objective; (2) such generated suites trigger
  different class interactions and can kill on average 7.7% (with a maximum of 50%)
  of mutants that are not detected by tests generated randomly or at the unit level;
  (3) Cling can detect integration faults coming from wrong assumptions about the
  usage of the callee class (25 for our subject systems) that remain undetected when
  using automatically generated random and unit-level test suites.
publication: '*IEEE Transactions on Software Engineering*'
doi: 10.1109/TSE.2022.3209625
---
