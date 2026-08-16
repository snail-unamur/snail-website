---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "EnergyTrackr: A Modular Energy Regressions Detection Tool"
authors: 
    - francois-bechet
    - jerome-maquoi
    - Luís Cruz
    - benoit-vanderose
    - xavier-devroey
date: 2026-10-12
doi: "10.1145/3832783.3834640"

# Schedule page publish date (NOT publication's date).
publishDate: 2026-08-16T00:00:02+02:00

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["paper-conference"]

# Publication name and optional abbreviated publication name.
publication: "*Proceedings of the 41st IEEE/ACM International Conference on Automated Software Engineering (ASE '26)*"
publication_short: ""

abstract: "Energy efficiency is increasingly recognized as an important dimension of software quality. As systems evolve rapidly, tracking how energy consumption changes across versions can provide valuable insights for developers and researchers. Although detecting energy regressions (i.e., unintended increases in energy consumption) remains challenging due to measurement variability and complex execution environments, recent advances now make systematic analysis practical. Still, dedicated support for monitoring energy behavior over a project's history is missing. This paper presents EnergyTrackr, a modular, open-source tool for automatically detecting, classifying, and visualizing energy regressions across a commit history. EnergyTrackr traverses a specified set of commits, builds each revision, and measures application-level energy consumption by executing the test suite using the RAPL-based Linux perf utility. It applies established best practices for measurements such as warm-up, randomized execution, repetition, and thermal control. The resulting data are analyzed through a statistical pipeline that filters outliers and classifies energy changes using multiple criteria (e.g., significance, practical impact, ...). EnergyTrackr generates interactive reports that provide a comprehensive view of energy evolution and is designed for easy integration into existing Linux workflows. A preliminary evaluation on large Java projects shows that EnergyTrackr can produce stable measurements at scale and effectively identify energy regressions."

# Summary. An optional shortened abstract.
summary: ""

tags: 
    - Software Testing
    - Energy Consumption
    - Sustainability
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
url_code: "https://github.com/snail-unamur/energytrackr"
url_dataset: 
url_poster:
url_project:
url_slides:
url_source:
url_video: "https://doi.org/10.5281/zenodo.21507425"

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Evolution plot showing the commit cc2363e and nearby commits from JSoup. Each blue dot is the median energy consumption, with corresponding black error bars. The red (resp. green) vertical bars represent commits with a level of at least 2 with an energy regression (resp. improvement). Commits with an additional colored circle denote regressions with their certainty level: blue for level 2, orange for level 3, purple for level 4, and red for level 5. The levels can be cumulated and are all visually represented."
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: 
    - phd-jerome-maquoi
    - msc-francois-bechet

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---
