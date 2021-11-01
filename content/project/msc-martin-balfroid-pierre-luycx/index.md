---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "MuTEd: Using mutation testing to enhance software testing education"
summary: "The goal of this master thesis is to define a mutation strategy for software testing education relyinng on a dedicated set of mutation operators with specific mutants selection approach to present only interesting mutants to the students."
authors:
  - martin-balfroid
  - pierre-luycx
tags:
  - Msc Thesis
  - Ongoing
  - Mutation Testing
  - Education
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

One of the main challenges when learning software testing is to define good oracles for the tests. An oracle is a mechanism allowing to automatically decide if a test passes or fails based on its execution. For unit testing, an oracle takes the form of assertions added to the code of the unit tests to check specific output values. Over the years, several techniques (like lines or branch coverage) have been developed to allow developers to check the quality of their tests. Among those, mutation testing injects defects (using mutation operators) to a given source code to see if the current tests can detect them. Recently, Vera-Pérez et al. developed [Descartes](https://github.com/STAMP-project/pitest-descartes), a mutation engine relying on extreme mutation operators to evaluate the quality of the assertions of a test suite. Using a plugin extension called [Reneri](https://github.com/STAMP-project/descartes-reneri), Descartes can generate a report providing information to the developer on the potential reasons why mutants remain undetected. Descartes + Reneri requires a certain amount of knowledge about mutation testing and might not be suited for software testing education.
The goal of this master thesis is, following the Descartes + Reneri philosophy, to define a mutation strategy for software testing education. Such strategy would rely on a dedicated set of mutation operators with specific mutants selection approach to present only interesting mutants to the students. Following the Reneri approach, the mutation strategy can also generate reports explaining to students how they can write tests able to kill specific mutants.
