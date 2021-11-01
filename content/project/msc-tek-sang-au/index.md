---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "JCrashBench: Crash reproduction benchmark augmentation using mutation testing"
summary: "The goal of this master thesis is to complement existing crash reproduction benchmarks by using mutation testing to generate crashy versions of an application and assess those potential crashes using search-based crash reproduction."
authors:
  - tek-sang-au
tags:
  - Msc Thesis
  - Ongoing
  - Crash Reproduction
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

Search-based crash reproduction is a technique relying on genetic algorithms to produce a test case able to reproduce a given crash stack trace. Benchmarking is a crucial step to assess and improve the state-of-the-art of search-based software testing. For crash reproduction, previous research has relied on [JCrashPack](https://github.com/STAMP-project/JCrashPack), a benchmark containing 200 Java crashes. Defining such benchmarks is hard: it requires searching for crashes in issue trackers, investigating the crash to understand its underlying cause, and collecting the necessary artifacts (binaries and source code). A complement to benchmarks with real-world crashes is the definition of artificial crashes using mutation testing on the source to inject artificial defects. This approach has been used successfully to improve the identification of defects using static analysis and machine learning.
The goal of this master thesis is to use mutation testing to generate crashy versions of an application and assess those potential crashes using search-based software crash reproduction. It will complement the existing benchmark (JCrashPack) with artificial crashes to enhance the comparison of crash reproduction approaches.
