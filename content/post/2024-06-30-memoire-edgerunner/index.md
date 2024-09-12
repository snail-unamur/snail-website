---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Advancing Mobile Code Editing: Johan and Simon's Work on Multi-Language Support with LSP Integration"
subtitle: ""
summary: ""
authors:
    - simon-loir
    - johan-rochet
tags: 
  - Source Code
  - DevEx
  - Mobile Development
categories: []
date: 2024-06-30T00:00:00+02:00
lastmod: 2024-06-30T00:00:00+02:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: 
  - msc-johan-rochet-simon-loir
---

Johan and Simon’s research is a significant step towards the development of an ergonomic and mobile code editor empowered by the Language Server Protocol (LSP) for multi-language support. While code editing is traditionally computer-based, the current technological landscape is witnessing a significant shift toward mobile technologies. Their work not only addresses this shift but also paves the way for a concrete and productive application designed for multi-language development in a single code editor on mobile devices.

They explored how the LSP could be used to provide common support for multiple languages on a unique mobile interface. To this end, they set up a cloud-oriented architecture to allow the use of language servers on mobile devices such as smartphones and tablets. They also designed an interface based on an adapted keyboard and a manipulation mode. The adapted keyboard provides the developer with language-based autocompletion (supplied by the LSP) and custom programming-oriented keyboard keys. Thanks to the manipulation mode, developers can manipulate code through gestures and execute a code action based on specific LSP functionalities. This practical approach has led to the development of a prototype that allows for effective code writing and manipulation in several programming languages on a mobile device.
