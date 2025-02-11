---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "FuzzE, Development of a Fuzzing Approach for Odoo's Tours Integration Testing Plateform"
authors: 
    - gabriel-benoit
    - François Georis
    - Géry Debongnie
    - benoit-vanderose
    - xavier-devroey
date: 2025-03-31
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: 2025-02-07T00:00:01+02:00

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["paper-conference"]

# Publication name and optional abbreviated publication name.
publication: "*Proceedings of the 2025 IEEE Conference on Software Testing, Verification and Validation (ICST)*"
publication_short: ""

abstract: "For many years, Odoo, an open-source add-on-based platform offering an extensive range of functionalities, including Enterprise Resource Planning, has constantly expanded its scope, resulting in an increased complexity of its software. To cope with this evolution, Odoo has developed an integration testing system called tour execution, which executes predefined testing scenarios (i.e., tours) on the web user interface to test the integration between the front, back, and data layers. This paper reports our effort and experience in extending the tour system with fuzzing. Inspired by action research, we followed an iterative approach to devise FuzzE, a plugin for Odoo's tour system to create new tours. FuzzE was eventually developed in three iterations. Our results show that mutational fuzzing is the most effective approach when integrating with an existing testing infrastructure. We also reported one issue to the Odoo issue tracker. Finally, we present lessons learned from our endeavor, including the necessity to consider testability aspects earlier when developing web-based systems to help the fuzzing effort, and the difficulty faced when performing triage and root cause analysis on failing tours."

# Summary. An optional shortened abstract.
summary: ""

tags: 
    - Fuzzing
    - University Industry Collaboration
    - Software Testing
categories: []
featured: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

url_pdf: https://xdevroey.be/publication/benoit-2025/benoit-2025.pdf
url_code: https://github.com/snail-unamur/FuzzE
url_dataset: https://doi.org/10.5281/zenodo.14605997
url_poster:
url_project:
url_slides:
url_source:
url_video:

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "FuzzE conceptual overview"
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects:
    - cyberexcellence
    - msc-gabriel-benoit

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---
