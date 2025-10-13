---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Co-funding FSR - UNIVERSEH: Diversity-based sampling for many-folded-variability cyber-physical systems"
summary: "This PhD project will provide diversity-based sampling techniques for the analysis and test of variability-aware Cyber-Physical Systems (CPSs). In particular, we will explore 1) formal modelling of the variability space of CPSs, 2) Exploring the notion of diversity, and 3) designing novel diversity-based algorithms. The contributions will be evaluated on a diversity of CPSs including space satellites."
authors:
  - sara-erasolasso
  - xavier-devroey
tags:
  - Funded
  - Ongoing
  - UNIVERSEH
  - CyberCyber-Physical System
  - Software Testing
  - Software Product Lines
categories: []
date: 2025-10-01

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

Cyber-physical systems (CPSs) combine computational and physical capabilities. CPSs serve in many domains, such as embedded systems (cars, drones, space satellites, etc.), industry 4.0 (automated warehouses, robotics) or “smart” things (smart homes,  etc.). CPSs operate under stringent functional and non-functional requirements as they must fulfil (often) safety-critical missions in changing environments.  In addition, they exploit variability, i.e., the ability of a system to alter its behavior by activating one more option (also called features). CPS designers can explicitly model variability during design to engineer product lines, i.e., a family of systems sharing common components configured or adapted in some way to form variants. Variability can also occur at runtime, e.g., when a drone shuts down an energy-consuming sensor to preserve battery life.  

While variability is core to the design and operation of CPSs, it is also a challenge when it comes to exploring and validating variants. Indeed, the number of variants grows exponentially with the number of variability options available: 320 independent Boolean options are sufficient to build more variants than the number of atoms in the universe. Large variability-aware systems like the Linux kernel possess thousands of options. CPSs also have specificities: some options are not Boolean and may be time-dependent. Thus the CPSs’ variability space is complex and hybrid.

Under such assumptions, exhaustively exploring the variability space of CPSs is intractable for, e.g., testing the different variants. One popular approach consists of sampling variants from a compact representation of the variability space (using feature models) based on some criteria: pairwise testing, uniformity sampling, etc.  

The main objective of this project is to theoretically study and provide new sampling criteria for CPSs. Many criteria proposed in the literature only apply to Boolean features, which are not expressive enough for CPSs. This thesis will, therefore, extend sampling to such systems by achieving diversity in the sampled variants. Diversity is a promising criterion because it is correlated with criteria aimed at finding faults (such as pairwise sampling) while (sometimes) being easier to compute.

This PhD grant is co-funded by the [SnT research center of the University of Luxembourg](https://www.uni.lu/snt-en/) under the FSR - [UNIVERSEH](https://universeh.eu) co-funding. This is a co-supervision with Prof. [Mike Papadakis](https://mpapad.github.io) from the [Security, Reasoning and Validation (SerVal)](https://www.uni.lu/snt-en/research-groups/serval/) research group.

{{< figure src="footer-funding-universeh.png">}}
