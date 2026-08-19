---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Investigating LLMs for Feature Presence Prediction in Software Products"
authors: 
    - Guillaume Nguyen
    - Paolo Arcaini
    - Maxime Cordy
    - Xavier Devroey
    - Fuyuki Ishikawa
date: 2026-09-29
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: 2026-08-19T00:00:01+02:00

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["paper-conference"]

# Publication name and optional abbreviated publication name.
publication: "*Proceedings of the International Conference on Software and Systems Reuse, Product Lines, and Configuration (VARIABILITY'26)*"
publication_short: ""

abstract: "Assessing legacy systems for compliance with new requirements is critical but hindered by obsolete documentation and the loss of expert knowledge. While Software Product Line (SPL) research excels at feature model reconstruction, identifying specific features within a single legacy product for re-evaluation remains a persistent challenge and has received comparatively less attention than full feature model reconstruction. In this paper, we evaluate the ability of five Large Language Models (LLMs) to automate feature retrieval from legacy code. We propose an empirical framework using SPL benchmarks across 248 product variants to enable a controlled quantitative evaluation. Our study investigates the impact of prompting strategies, including few-shot configuration, feature name obfuscation, and source code granularity (individual function definition vs. complete code). Our results demonstrate that while LLMs can identify features with reasonable accuracy, their performance is highly sensitive to lexical cues and prompting design. We highlight a fundamental Precision-Recall trade-off and provide empirical insights into the conditions and challenges of using LLMs for legacy system re-assessment."

# Summary. An optional shortened abstract.
summary: ""

tags: 
    - Conformity Assessment
    - Cyber-Physical System
    - Large Language Model
categories: []
featured: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

url_pdf:
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
  caption: "Approach overview"
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: 
    - cyberexcellence

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---
