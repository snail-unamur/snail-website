---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Towards user-friendly fuzzers"
summary: ""
authors: 
 - anae-debaets
tags: 
  - Msc Thesis
  - Ongoing
  - Fuzzing
  - DevEx
  - Web Development
categories: []
date: 2024-09-29T10:47:40+02:00

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

Fuzz testing, or simply fuzzing, is an automated testing technique aiming at discovering bugs or vulnerabilities of software systems by providing random, invalid, or potential harmful input data. Fuzzing is a black-box testing technique, as typically, fuzzers, i.e. tools running fuzzing, have no access to the source code. Where structured testing will typically be manually written, i.e. developers will write test cases to ensure a system behaves as expected - verification - and fulfils the users' expectations - validation -, fuzzing tools may employ techniques to generate a range of inputs with minimal manual intervention. However, many open-source or openly-accessible fuzzers have rudimentary user interfaces, so that developers must typically have a good understanding of what software security testing is, as well as understand how specific fuzzers need to be configured for specific software under tests. This project will explore how existing fuzzers could be made more approachable for non-experts. The scope of the project will be restricted to web systems (REST).
