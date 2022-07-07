---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "LASoT: Learning to assert in software testing using mutants"
summary: "The goal of this master thesis is to assess the usage of Descartes and Reneri in an IDE. The master thesis consists of developing an IDE plugin to include Descartes and Reneri and evaluate with developers to what extend the usage of mutation testing helps writing better assertions."
authors:
    - samuel-van-de-put
tags:
  - Msc Thesis
  - Ongoing
  - Mutation Testing
categories: []
date: 2021-09-15

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

One of the main challenges when learning software testing is to define good oracles for the tests. An oracle is a mechanism allowing to automatically decide if a test passes or fails based on its execution. For unit testing, an oracle takes the form of assertions added to the code of the unit tests to check specific output values. Over the years, several techniques (like lines or branch coverage) have been developed to allow developers to check the quality of their tests. Among those, mutation testing injects defects (using mutation operators) to a given source code to see if the current tests can detect them. Recently, Vera-Pérez et al. developed [Descartes](https://github.com/STAMP-project/pitest-descartes), a mutation engine relying on extreme mutation operators to evaluate the quality of the assertions of a test suite. Using a plugin extension called [Reneri](https://github.com/STAMP-project/descartes-reneri), Descartes can generate a report providing information to the developer on the potential reasons why mutants remain undetected.
The goal of this master thesis is to assess the usage of Descartes and Reneri in an IDE. The master thesis consists of developing an IDE plugin to include Descartes and Reneri and evaluate with developers to what extend the usage of mutation testing helps writing better assertions.
