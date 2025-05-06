---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Energy Codesumption, Leveraging Test Execution for Source Code Energy Consumption Analysis"
authors: 
    - jerome-maquoi
    - Maxime Cauz
    - benoit-vanderose
    - xavier-devroey
date: 2025-06-23
doi: "10.1145/3696630.3728707"

# Schedule page publish date (NOT publication's date).
publishDate: 2025-05-06T08:16:53+02:00

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["paper-conference"]

# Publication name and optional abbreviated publication name.
publication: "*Proceedings of the 33rd ACM International Conference on the Foundations of Software Engineering (FSE Companion ’25)*"
publication_short: ""

abstract: "The software engineering community has increasingly recognized sustainability as a key research area. However, developers often have limited knowledge of effective strategies to reduce software energy consumption. To address this, we analyze energy consumption in software execution, aiming to raise developer awareness by linking energy consumption with each line of code. We rely on unit test executions to identify energy-intensive executions and manually analyze five hot and five cold spots to identify potentially energy-intensive source code constructs. Our findings suggest a link between the energy consumption of the source code and the number of objects’ attributes created within that code. These results lay the groundwork for further analysis of the relationship between object instantiation and energy consumption in Java."

# Summary. An optional shortened abstract.
summary: ""

tags: 
    - Software Testing
    - Energy Consumption
    - Sustainability
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
url_code:
url_dataset: 
url_poster:
url_project:
url_slides:
url_source:
url_video:

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Distribution of the energy consumption of the five highest and five lowest CT of the Spring Boot and Spoon."
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: 
    - phd-jerome-maquoi

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---
