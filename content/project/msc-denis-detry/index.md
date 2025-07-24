---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Automated performance testing for mixed reality systems"
summary: ""
authors: 
 - denis-detry
tags: 
  - Msc Thesis
  - Finished
  - Virtual Reality
  - Performance Testing
categories: []
date: 2025-06-23T10:47:40+02:00

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Performance testing workflow"
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

Software engineering for mixed reality headsets is still in its early genesis even though the required hardware for it has been available for several decades. Existing methods to streamline development are still limited and developers often find themselves doing things manually. Mixed Reality system testing, for example, are often done by hand by developers who have to wear the headsets and do the testing as if they were an end user. This is a significant time sink in the development process.

This thesis focuses on the available methods for automating these tests, specifically, performance tests. They have the added challenge of requiring to run on the headset directly. It is of great priority for mixed reality apps because bad performance can at best make the experience worse and at worst cause motion sickness in users.

To find a solution to the problem, we’ve firstly explored the different available avenues for automation of the tests. Then we’ve decided to adapt an existing mixed reality capture and replay of user interactions tool so that it would fit our needs. The tool’s objective would be to detect gains and losses in performance between two different builds of a same mixed reality app. Having access to this kind of tool would allow developers to gain a significant amount of time during the development of their apps when they have to do small performance optimizations. It would not only be quicker than a human doing the tests themselves but it would also be more precise, and better able to detect the differences more accurately.

{{< linkedinupdate "urn:li:activity:7342837938759630848" >}}
