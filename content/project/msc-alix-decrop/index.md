---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Leveraging Large Language Models to Automatically Infer RESTful API Specifications"
summary: ""
authors: 
 - alix-decrop
tags: 
  - Msc Thesis
  - Finished
  - Search-Based Software Engineering
  - Large Language Model
  - REST API
categories: []
date: 2022-11-04T10:14:15+01:00

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Overview of the Multiple Request Mutation Strategy process."
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
url_pdf: "https://researchportal.unamur.be/en/studentTheses/leveraging-large-language-models-to-automatically-infer-restful-a"
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

Application Programming Interfaces, known as APIs, are increasingly popular in modern web applications. With APIs, users around the world are able to access a plethora of data contained in numerous server databases. To understand the workings of an API, a formal documentation is required. This documentation is also required by API testing tools, aimed at improving the reliability of APIs. However, as writing API documentations can be time-consuming, API developers often overlook the process, resulting in unavailable, incomplete or informal API documentations.
Recent Large Language Model technologies such as ChatGPT have displayed exceptionally efficient capabilities at automating tasks, disposing of data trained on billions of resources across the web. Thus, such capabilities could be utilized for the purpose of generating API documentations.
Therefore, the Master’s Thesis proposes the first approach Leveraging Large Language Models to Automatically Infer RESTful API Specifications. Preliminary strategies are explored, leading to the implementation of a tool entitled MutGPT. The intent of MutGPT is to discover API features by generating and modifying valid API requests, with the help of Large Language Models.
Experimental results demonstrate that MutGPT is capable of sufficiently inferring the specification of the tested APIs, with an average route discovery rate of 82.49% and an average parameter discovery rate of 75.10%. Additionally, MutGPT was capable of discovering 2 undocumented and valid routes of a tested API, which has been confirmed by the relevant developers.
Overall, this Master’s Thesis uncovers 2 new contributions:

1. Large Language Models are capable of generating valid and diversified HTTP requests for RESTful APIs, only requiring the name of the API as input.

2. It is possible to automatically infer RESTful API specifications by leveraging Large Language Models.

A replication package with the implementation and evaluation data is available at the following [GitHub repository](https://github.com/alixdecr/MutGPT).