---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "VaryMinions: Leveraging RNNs to Identify Variants in Variability-intensive Systems' Logs"
subtitle: ''
summary: ''
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
categories: []
date: 2024-03-08
lastmod: 2024-03-08T08:09:00+01:00
featured: false
draft: false

# links:
# - name: ""
#   url: ""
url_pdf: 'https://xdevroey.be/publication/fortz-2024-b/fortz-2024-b.pdf'
url_code:
url_dataset: 'https://zenodo.org/doi/10.5281/zenodo.5083333'
url_poster:
url_project:
url_slides:
url_source:
url_video:

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Result of Friedman's statistical test along with Nemenyi's post-hoc analysis over all datasets and parameterisations."
  focal_point: ''
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
publishDate: 2024-03-08T00:00:01+02:00
# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["article-journal"]
abstract: "From business processes to course management, variability-intensive software systems (VIS) are now ubiquitous. One can configure these systems' behaviour by activating options, e.g., to derive variants handling building permits across municipalities or implementing different functionalities (quizzes, forums) for a given course. These customisation facilities allow VIS to support distinct relevant customer requirements while taking advantage of reuse for common parts. Customisation thus allows realising both scope and scale economies. Behavioural differences amongst variants manifest themselves in event logs. 
To re-engineer this kind of system, one must know which variant(s) have produced which behaviour. Since variant information is barely present in logs, this paper supports this task by employing machine learning techniques to classify behaviours (event sequences) among variants. Specifically, we train Long Short Term Memory (LSTMs) and Gated Recurrent Units (GRUs) recurrent neural networks to relate event sequences with the variants they belong to on six different datasets issued from the configurable process and VIS domains. After having evaluated 20 different architectures of LSTM/GRU, our results demonstrate that it is possible to effectively learn the trace-to-variant mapping with high accuracy (at least 80% and up to 99%) and at scale, i.e., identifying 50 variants using 5000+ traces for each variant."
publication: "*Empirical Software Engineering*"
doi: ''
---
