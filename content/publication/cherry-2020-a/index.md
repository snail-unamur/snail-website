---
title: "Crash reproduction difficulty, an initial assessment"
date: 2020-12-03
publishDate: 2020-12-01T16:31:22.548158Z
authors: ["Boris Cherry", xdevroey, "Pouria Derakhshanfar", bvdose]
publication_types: ["1"]
abstract: "This study presents the initial step towards a thorough analysis of the difficulty to reproduce a crash using search-based crash reproduction. Traditionally, code size and complexity are considered representative indicators of the difficulty for search-based approaches, like search-based unit test generation, to generate tests. However, unlike unit test generation, crash reproduction does not seek to cover a set of behaviors but instead to generate one or more tests exercising a specific behavior reproducing a given crash. In this context, there is no guarantee that the indicators used for unit testing are still valid for crash reproduction. In this study, we seek to identify such indicators by considering various code metrics, code smells, and change metrics. We report our effort to collect those metrics for JCRASHPACK, a state-of-the-art crash reproduction benchmark, and an initial assessment by considering metrics individually. Our results show that although JCRASHPACK is larger than benchmarks used in previous studies, additional crashes should be added to improve its diversity and representativeness, and that no individual metric can be used to characterize the difficulty to reproduce a crash."
featured: false
publication: "*Proceedings of the 19th Belgium-Netherlands Software Evolution Workshop (BENEVOL '20)*"

tags:
- Crash Reproduction
- Search-Based Software Testing

# links:
# - name: ""
#   url: ""
url_pdf: 'https://xdevroey.be/publication/cherry-2020-a/cherry-2020-a.pdf'
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: ''
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects:

---
