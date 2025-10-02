---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "MuLLSA: Mutation with LLM and Static Analysis"
summary: ""
authors: 
 - arthur-barbieux
tags: 
  - Msc Thesis
  - Finished
  - Security Testing
  - Artificial Intelligence
categories: []
date: 2025-08-28T12:38:40+02:00

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Approach overview"
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
url_pdf: "https://researchportal.unamur.be/en/studentTheses/mullsa"
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

Looking after bugs and vulnerabilities is one of the most important tasks in computer science, especially in the context of web applications. There are many techniques to detect and prevent these issues, one of the most widely used being mutation testing. However, creating mutants manually is a time-consuming and error-prone pro- cess. To address this, we perform a combination of static analysis and an LLM to automatically generate mutants. In this study, we compare the performance of an LLM in producing mutants based on three different static analysis tools: KAVe, WAP, and the LLM itself. Our results show significant variability between tools. Mutants produced using traditional static analysers vary heavily depending on the type of vulnerability, and tend to perform better when tools are combined. When it comes to the LLM, the quality of mutants is more consistent across different vulnerabilities, and the overall code coverage is significantly higher than traditional approaches. On the other hand, LLM-generated mutants have a higher success rate in passing initial verification, but often contain syntactic or semantic errors in the code. These findings suggest that LLMs are a promising addition to automated vulnerability testing workflows, especially when used in conjunction with static analysis tools. However, further refinement is needed to reduce the generation of incorrect or invalid code and to better align with real-world exploitability.

{{< linkedinupdate "urn:li:activity:7368155477089689600" >}}
