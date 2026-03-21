---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Real-World Fault Detection for C-Extended Python Projects with Automated Unit Test Generation"
authors: 
    - lucas-berg
    - Lukas Krodinger
    - Stephan Lukasczyk
    - Annibale Panichella
    - Gordon Fraser†
    - Wim Vanhoof
    - xavier-devroey
date: 2026-05-19
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: 2026-03-21T00:00:01+02:00

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["paper-conference"]

# Publication name and optional abbreviated publication name.
publication: "*Proceedings of the 19th IEEE International Conference on Software Testing, Verification and Validation (ICST 2025)*"
publication_short: ""

abstract: "Many popular Python libraries use C-extensions for performance-critical operations allowing users to combine the best of the two worlds: The simplicity and versatility of Python and the performance of C. A drawback of this approach is that exceptions raised in C can bypass Python’s exception handling and cause the entire interpreter to crash. These crashes are real faults if they occur when calling a public API. While automated test generation should, in principle, detect such faults, crashes in native code can halt the test process entirely, preventing detection or reproduction of the underlying errors and inhibiting coverage of non-crashing parts of the code. To overcome this problem, we propose separating the generation and execution stages of the test- generation process. We therefore adapt PYNGUIN, an automated test case generation tool for Python, to use subprocess-execution. Executing each generated test in an isolated subprocess prevents a crash from halting the test generation process itself. This allows us to (1) detect such faults, (2) generate reproducible crash-revealing test cases for them, (3) allow studying the underlying faults, and (4) enable test generation for non-crashing parts of the code. To evaluate our approach, we created a dataset consisting of 1 648 modules from 21 popular Python libraries with C-extensions. Subprocess-execution allowed automated testing of up to 56.5 % more modules and discovered 213 unique crash causes, revealing 32 previously unknown faults."

# Summary. An optional shortened abstract.
summary: ""

tags: 
    - Seach-Based Software Testing
    - Software Testing
categories: []
featured: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

url_pdf: 
url_code: 'https://github.com/se2p/pynguin'
url_dataset: 'https://zenodo.org/records/18879486'
url_poster:
url_project:
url_slides:
url_source:
url_video:

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: 
    - cyberexcellence
    - realm

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---
