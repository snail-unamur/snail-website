---
title: Basic block coverage for search-based unit testing and crash reproduction
subtitle: ''
summary: ''
authors:
- Pouria Derakhshanfar
- xavier-devroey
- Andy Zaidman
tags: 
- Crash Reproduction
- Search-Based Software Testing
- Artificial Intelligence
categories: []
date: '2022-10-01'
lastmod: 2022-10-06T15:58:49+02:00
featured: false
draft: false

url_pdf: 'https://xdevroey.be/publication/derakhshanfar-2022-a/derakhshanfar-2022-a.pdf'
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ''
  focal_point: ''
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
publishDate: '2022-10-06T13:58:49.429378Z'
publication_types: ["article-journal"]
abstract: Search-based techniques have been widely used for white-box test generation.
  Many of these approaches rely on the approach level and branch distance heuristics
  to guide the search process and generate test cases with high line and branch coverage.
  Despite the positive results achieved by these two heuristics, they only use the
  information related to the coverage of explicit branches (e.g., indicated by conditional
  and loop statements), but ignore potential implicit branchings within basic blocks
  of code. If such implicit branching happens at runtime (e.g., if an exception is
  thrown in a branchless-method), the existing fitness functions cannot guide the
  search process. To address this issue, we introduce a new secondary objective, called
  Basic Block Coverage (BBC), which takes into account the coverage level of relevant
  basic blocks in the control flow graph. We evaluated the impact of BBC on search-based
  unit test generation (using the DynaMOSA algorithm) and search-based crash reproduction
  (using the STDistance and WeightedSum fitness functions). Our results show that
  for unit test generation, BBC improves the branch coverage of the generated tests.
  Although small ($∼ $1.5%), this improvement in the branch coverage is systematic
  and leads to an increase of the output domain coverage and implicit runtime exception
  coverage, and of the diversity of runtime states. In terms of crash reproduction,
  in the combination of STDistance and WeightedSum, BBC helps in reproducing 3 new
  crashes for each fitness function. BBC significantly decreases the time required
  to reproduce 43.5% and 45.1% of the crashes using STDistance and WeightedSum, respectively.
  For these crashes, BBC reduces the consumed time by 71.7% (for STDistance) and 68.7%
  (for WeightedSum) on average.
publication: '*Empirical Software Engineering*'
doi: 10.1007/s10664-022-10155-0
---
