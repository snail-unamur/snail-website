---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Prompt Debloating for LLM-based Test Generation with Graph-Augmented Retrieval"
summary: ""
authors: 
 - victor-santele
tags: 
  - Msc Thesis
  - Finished
  - Large Language Model
  - University Industry Collaboration
  - Test Case Generation
  - Artificial Intelligence
categories: []
date: 2025-09-01T10:47:41+02:00

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Logarithmic Distribution of Context Sizes in Tokens across Methods"
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
url_pdf: "https://researchportal.unamur.be/en/studentTheses/prompt-debloating-for-llm-based-test-generation-with-graph-augmen"
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

The use of Large Language Models (LLMs) for automated test generation offers promising results but remains constrained by issues like hallucinations and prompt size limitations. This thesis investigates the integration of a graph-based Retrieval Augmented Generation (RAG) technique to enhance test generation within TestSpark, an IntelliJ IDEA plugin. We introduce GRACE-TG (Graph-Retrieved Augmented Contextual Enhancement for Test Generation), which constructs a graph of code entities using the Program Structure Interface (PSI) and rank nodes via a Personalized Weighted PageRank algorithm. This enables a precise selection of relevant context for LLMs while significantly reducing input size. Evaluation across 147 real-world Java bugs demonstrates that GRACE-TG reduces prompt sizes by over 97% compared to the current version of TestSpark, with equivalent or improved test coverage. These results suggest that graph-based retrieval can be a good candidate to improve test generation with LLMs.

{{< linkedinupdate "urn:li:activity:7368313011830169602" >}}
