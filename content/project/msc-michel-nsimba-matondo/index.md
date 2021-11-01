---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "MetaTReq: A meta-modelisation approach of test requirements"
summary: "The goals of this master thesis is to define an extendable meta-model and associated DSL to describe high-level test requirements and their (optionally) associated assertions for Java programs."
authors:
  - michel-nsimba-matondo
tags:
  - Msc Thesis
  - Ongoing
  - Test Coverage Criteria
  - Model-based Testing
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

Test cases can be manually written or automatically generated. In white-box test case generation approaches, tests are generated from the source code, usually using a search-based approach. Many test coverage requirements have been defined over the years, like, for instance, line coverage, branch coverage, input and output coverage, etc. Without any additional information, those approaches face the so-called oracle problem (i.e., deciding if one execution of the SUT, triggered by a test case, is valid or not). Recently, new search-based test case generation approaches rely on external information to decide whether such execution is valid or not. For instance, search-based crash reproduction uses a given Java stack-trace to generate a crash-reproducing test case. Another approach relies on information from a static code analyzer to generate test cases exposing API misuses. In those two examples, the oracle is simple: if the test case causes a crash (i.e., if an uncaught exception is thrown during the execution), the test fails. Other examples include the definition of particular methods' return values or assertions on those return values, etc.
The goals of this master thesis is to define an extendable meta-model and associated DSL to describe high-level test requirements and their (optionally) associated assertions for Java programs.
