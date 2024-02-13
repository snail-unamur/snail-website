---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Towards LLM-Generated Code Tours for Onboarding"
authors: 
    - martin-balfroid
    - benoit-vanderose
    - xavier-devroey
date: 2024-04-20
doi: "10.1145/3643787.3648033"

# Schedule page publish date (NOT publication's date).
publishDate: 2024-02-12T00:00:01+02:00

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: "*Proceedings of the 2024 ACM/IEEE International Workshop on NL-based Software Engineering (NLBSE '24)*"
publication_short: ""

abstract: "Onboarding new developers is a challenge for any software project. Addressing this challenge relies on human resources (e.g., having a senior developer write documentation or mentor the new developer). One promising solution is using annotated code tours. While this approach partially lifts the need for mentorship, it still requires a senior developer to write this interactive form of documentation. This paper argues that a Large Language Model (LLM) might help with this documentation process. Our approach is to record the stack trace between a failed test and a faulty method. We then extract code snippets from the methods in this stack trace using CodeQL, a static analysis tool and have them explained by gpt-3.5-turbo-1106, the LLM behind ChatGPT. Finally, we evaluate the quality of a sample of these generated tours using a checklist. We show that the automatic generation of code tours is feasible but has limitations like redundant and low-level explanations."

# Summary. An optional shortened abstract.
summary: ""

tags: 
    - Artificial Intelligence
    - Large Language Model
    - Onboarding
categories: []
featured: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

url_pdf: https://xdevroey.be/publication/balfroid-2024/balfroid-2024.pdf
url_code:
url_dataset: https://doi.org/10.5281/zenodo.10527352
url_poster:
url_project:
url_slides:
url_source:
url_video:

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Example of generated code tour step"
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: 
    - ariac

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---
