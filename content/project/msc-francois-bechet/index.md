---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Systematic Detection of Energy Regressions in Java Projects and Identification of Regression Code Patterns"
summary: ""
authors:
 - francois-bechet
tags: 
  - Msc Thesis
  - Finished
  - Sustainability
  - Energy Consumption
  - Green Coding
categories: []
date: 2025-06-24T10:47:40+02:00

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Evolution plot showing commit cc2363e and nearby commits."
  focal_point: ""
  preview_only: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

url_code: "https://github.com/snail-unamur/energytrackr"
url_dataset: "https://github.com/snail-unamur/energytrackr-data"
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

Green software engineering is emerging as a crucial response to the rising energy impact of digital technologies, which may soon rival aviation and shipping combined. While several tools aim to help developers track energy consumption and detect regressions, they all have their own limitations. This motivated the development of EnergyTrackr, a fully modular and automated tool designed to detect statistically significant energy changes.

The main goal was to uncover energy anti-patterns as a first step toward building energy- aware linters. To achieve this, a custom pipeline was implemented: one module iterates over a repository's history and measures energy usage per commit; another generates interactive reports enabling developers to spot energy regressions faster. Stability was improved through system setup script and statistical validation methods.

Experiments on three Java projects (Jsoup, univocity-parsers, fastexcel) confirmed the tool's ability to identify significant energy changes and highlighted recurring anti-patterns such as missing early exits or costly dependency upgrades. EnergyTrackr is ready to integrate into developer workflows and lays the groundwork for building energy-aware linters, pending further large-scale studies.

{{< linkedinupdate "urn:li:activity:7343302180403056640" >}}
