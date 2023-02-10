---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "DeFlake: Exploring test flakiness debugging"
summary: "The goal of this master thesis is to explore potential leads to debug and fix flaky tests, producing different outcomes when executed several times, by applying debugging approaches to failing tests to understand the root cause of flakiness."
authors:
  - gaetan-delvaux
tags:
  - Msc Thesis
  - Finished
  - Test Flakiness
  - Debugging
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

Flaky tests are test cases that produce different outcomes when executed several times. Such tests are highly undesirable in any development project since they randomly break the project builds without actually indicating the presence of a defect. Over the years, the industry has come up with several strategies to detect and deal with flaky tests. For instance, a common strategy consists of re-running flaky tests several times to see if they produce different outputs. Such strategies are time-consuming and add an additional burden to the build process.
The goal of this master thesis is to explore potential leads to debug and fix flaky tests, for instance, by applying debugging approaches to failing tests to understand the root cause of flakiness.
