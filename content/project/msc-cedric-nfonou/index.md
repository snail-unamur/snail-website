---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "MultiPlat: un framework déclaratif multi-plateforme et multi-dimensionnel"
summary: ""
authors: 
 - cedric-nfonou
tags: 
  - Msc Thesis
  - Finished
  - Development Framework
  - Web Development
categories: []
date: 2024-09-29T10:47:41+02:00

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Schéma de l’architecture générale de MultiPlat adapté de la conception interne du projet."
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
url_pdf: "https://researchportal.unamur.be/en/studentTheses/multiplat"
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

The evolution of digital usage has led to a rapid diversification of application runtime environments, ranging from traditional web browsers to immersive extended reality (XR) devices, as well as mobile and desktop platforms. This plurality of environments creates a growing need for solutions that can deliver a consistent user experience while minimizing the development and maintenance efforts associated with multi-platform deployment. However, current approaches often rely on separate implementations for each environment, leading to code duplication, visual and functional inconsistencies, and increased complexity in managing software evolution. These limitations hinder portability and slow down the time-to-market of multi-platform applications.

In this context, the MultiPlat framework was designed to facilitate the creation of graphical interfaces deployable without modification across multiple environments (Web, XR, Mobile). Its principle relies on a modular and declarative architecture, where the same component can be rendered in 2D using React DOM or in immersive 3D using A-Frame, while preserving visual and functional consistency. The framework also integrates an adaptive-position component for conditional positioning based on the execution context, as well as a command-line interface (CLI) to select the target platform and automatically adjust the project configuration.
Experimental validation, conducted in a multi-platform test environment (web browser, XR headset, WebXR emulator), measured cross-platform portability, visual consistency, and real-world performance. The results confirm the feasibility and technical robustness of the approach, while identifying areas for improvement, particularly inter-device synchronization and optimized native mobile support.
