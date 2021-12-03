---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Presentation abstract: VaryMinions , Identifying Variants in Event Logs with RNNs"
abstract: "Business processes capture the activities of every profit or non-profit, public or private organisation, coordinating humans and software to collectively deliver value. As organisations evolve, new needs appear: e.g., handling a change in the law about reimbursing travel expenses at the university. These needs lead to the emergence of process variants, differing in their control flow or performance while having commonalities with the original processes. The execution of a process consists in an ordered sequence of events, constituting an event trace. Such traces can be examined to identify and solve potential is- sues. In the context of process variants, one trace will however usually concern a subset of the variants and identifying these variants is a prerequisite to any maintenance activity. Unfortunately, event logs do not usually contain information about the specific variant (or set of variants) which (could have) produced the event traces, which can prevent practitioners from identifying and reproducing the context of the problem that has to be fixed. While there is a growing interest to employ ML techniques for VIS engineering, to the best of our knowledge, classification of variants from behavioural traces using ML techniques has not been studied yet. We provided a first experiment of the usage of two types of Recurrent Neural Networks (RNNs) to predict the candidate variant(s) that could produce a given event trace. An implementation of our approach with the full results is openly available."
authors:
- Sophie Fortz
- Paul Temple
- xavier-devroey
- Patrick Heymans
- Gilles Perrouin
tags:
- Machine Learning
- Software Product Lines
- Variability Mining
date: '2021-12-07'
lastmod: '2021-12-03'
featured: false
draft: false

# links:
# - name: ""
#   url: ""
url_pdf: 'https://benevol2021.github.io/papers/BENEVOL_2021_paper_14.pdf'
url_code:
url_dataset:
url_poster:
url_project:
url_slides:
url_source:
url_video:


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
publishDate: '2021-12-03'
publication_types:
- '1'
publication: "*20th Belgium-Netherlands Software Evolution Workshop, BENEVOL '21*"
doi:
---
