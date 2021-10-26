---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "JCrashPack2.0: Search-based crash reproduction hardness analysis"
summary: "This master thesis project, revisits the links between search-based crash reproduction and software quality metrics to assess the hardness of search-based crash reproducing test case generation."
authors: [bcherry]
tags:
  - Msc Thesis
  - Finished
  - Crash Reproduction
  - Search-Based Software Testing
categories: []
date: 2021-10-03T12:04:44+02:00

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

url_code: ""
url_pdf: "https://researchportal.unamur.be/fr/studentTheses/jcrashpack20"
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

Search-Based Crash Reproduction (SBCR) aims at helping developers in their debugging tasks by generating a test case reproducing a specific crash, based on its stack trace and the source code. In traditional search-based unit test generation approaches, the hardness to generate test cases is evaluated using static code analysis, like complexity, coupling or code size. Unlike unit test generation, SBCR does not seek to achieve high structural coverage but to reproduce a specific behaviour leading to a crash. In this work, we revisit links between SBCR and software quality metrics to assess the hardness of search-based crash reproducing test case generation. We use the values of the fitness function of Botsing, a search-based crash reproducing tool, as an indicator of the difficulty of the tool to reproduce a crash. Our results show pieces of evidence of an existing link between some software quality metrics and the values of the fitness score. However, we did not find any strong correlation between an individual metric and the hardness to reproduce a crash.

*Internship done at the [Software Engineering Research Group](https://se.ewi.tudelft.nl) of the [Delft University of Technology](https://www.tudelft.nl) in the Netherlands.*
