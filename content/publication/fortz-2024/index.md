---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: Towards Feature-based ML-enabled Behaviour Location
subtitle: ''
summary: ''
authors:
- Sophie Fortz
- Paul Temple
- xavier-devroey
- Gilles Perrouin
tags:
- Variability Mining
- Machine Learning
- Artificial Intelligence
categories: []
date: 2024-02-07
lastmod: 2023-12-03T11:27:54+01:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: 'Conceptual representation of the feature-based approach during the prediction phase.'
  focal_point: ''
  preview_only: false

# links:
# - name: ""
#   url: ""
url_pdf: 'https://xdevroey.be/publication/fortz-2024/fortz-2024.pdf'
url_code:
url_dataset:
url_poster:
url_project:
url_slides:
url_source:
url_video:

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects:
- cyberexcellence
publishDate: '2023-12-03T10:27:54.416422Z'
publication_types:
- '1'
abstract: 'Mapping behaviours to the features they relate to is a prerequisite for
  variability-intensive systems (VIS) reverse engineering. Manually providing this
  whole mapping is labour-intensive. In black-box scenarios, only execution traces
  are available (e.g., process mining). In our previous work, we successfully experimented
  with variant-based mapping using supervised machine learning (ML) to identify the
  variants responsible of the production of a given execution trace, and demonstrated
  that recurrent neural networks (RNNs) work well (above 80% accuracy) when trained
  on datasets in which we label execution traces with variants. However, this mapping
  (i) may not scale to large VIS because of combinatorial explosion and (ii) makes
  the internal ML representation hard to understand. In this short paper, we discuss
  the design of a novel approach: feature-based mapping learning.'
publication: '*Proceedings of the 18th International Working Conference on Variability
  Modelling of Software-Intensive Systems (VaMoS 2024)*'
doi: 10.1145/3634713.3634734
---
