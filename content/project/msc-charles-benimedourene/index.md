---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Automatic Vulnerability Injection using Genetic Improvement and Static Code Analysers"
summary: ""
authors: 
 - charles-benimedourene
tags: 
  - Msc Thesis
  - Finished
  - Genetic Improvement
  - Search-Based Software Engineering
  - Cybersecurity Testing
categories: []
date: 2022-11-04T10:14:15+01:00

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Overview of the genetic improvement approach"
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
url_pdf: "https://researchportal.unamur.be/en/studentTheses/automatic-vulnerability-injection-using-genetic-improvement-and-s"
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

This thesis explores the idea of applying genetic improvement in the aim of injecting vulnerabilities into programs. Generating vulnerabilities automatically in this manner would allow creating datasets of vulnerable programs. This would, in turn, help training machine-learning models to detect vulnerabilities more efficiently.
This idea was put to the test by implementing VulGr, a modified version of the framework dedicated to genetic improvement named PyGGi. VulGr itself uses CodeQL, a static code analyser, offering a new approach to statical detection of vulnerabilities. VulGr’s end goal was to use CodeQL to inject vulnerabilities into programs of the Vul4J dataset.
This experiment proved unsuccessful, CodeQL lacking accuracy and being too time-consuming to produce concrete results in an acceptable time span (less than 72 hours). However, the general approach and VulGr still retain their relevancy for future uses as CodeQL is an ongoing community effort promising new updates fixing the issues mentioned.
