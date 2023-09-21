---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "A configurable approach to cyber-physical systems fuzzing"
authors: 
    - guillaume-nguyen
date: 2023-08-20
doi: "10.1145/3579028.3609005"

# Schedule page publish date (NOT publication's date).
publishDate: 2023-08-20T08:16:53+02:00

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: "*Proceedings of the 27th ACM International Systems and Software Product Line Conference - Volume B*"
publication_short: ""

abstract: "Operational Technology has gotten a growing place in our daily lives. With the increasing number of devices (connected or not), the need for a clean environment that allows effective and efficient testing is also increasing. Furthermore, some devices are connected to the physical world with the ability to affect it. Assembling those specific devices with at least a sensor, an actuator, and a (micro)processor creates Cyber-Physical Systems (CPSs). With such power in the hands of machines, it is imperative that they behave as expected and that they resist disruptive environments (whether from cyber attacks, unwanted noise, or environmental disturbance). Indeed, the impacts of an unexpected behavior could lead to significant damage (disruption of the production line, overheating of a nuclear reactor, false fire alarm, etc.). That is why the safety and the security of those systems should also be at the center of concerns. As the definition of those systems is quite simple, one can assemble various components to create a unique CPS. One could also modify an existing CPS to satisfy a specific need (e.g., a fire alarm system modified to detect carbon monoxide in the air, changing communication protocols or programming languages used for the sake of maintainability). To test such highly-configurable systems, there are multiple techniques. Fuzzing works particularly well with any system by sending pseudo-random inputs. To adapt to specific systems and test requirements (coverage, resources, etc.), fuzzing is itself highly-configurable (Grammar-based, symbolic, probabilistic, etc.). This is why it could perform particularly well with CPSs, which all might require a different and specific testing approach depending on their interfaces, components, etc. Currently, no frameworks allow for the classification of CPSs  to enable the automatization of the generation of tests following their requirements. That is why this thesis will take a configurable approach to find and recommend the most suitable classification of CPS for testing and comparing the various fuzzing techniques to find the most effective ones based on relevant features and requirements of CPSs."

# Summary. An optional shortened abstract.
summary: ""

tags: 
    - Fuzzing
    - Cyber-Physical System
    - Cybersecurity Testing
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
  caption: "Cyber-physical systems metamodel by Tekinerdogan et al."
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: 
    - cyberexcellence

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---
