---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "ReVa@Odoo: Variability reverse engineering, a Odoo case study"
summary: "The goal of this master thesis is to define, implement, and (potentially) execute a reverse engineering approach for the Odoo ERP using the various artefacts available in the community version to produce a variability model, enabling the analysis of the configuration space of the Odoo ERP."
authors:
  - tek-sang-au
tags:
  - Msc Thesis
  - Ongoing
  - Software Product Lines
  - Variability Mining
categories: []
date: 2021-09-15

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

Software product lines (SPLs) and variability-intensive systems rely on the idea that software of the same family can be built by systematically reusing assets, some common to all members, whereas a subset only shares others. One example of such software is Odoo (https://www.odoo.com), an open-source Enterprise Resource Planning (ERP) platform allowing the integration of various business applications (e-commerce, accounting, manufacturing, warehouse, etc.) depending on the needs of a customer. Over the years, the research community has defined several approaches to reverse engineering and model the variability of SPLs. For example, feature models represent the features (i.e., set of assets) in tree structures and capture the constraints (inclusion, exclusion, etc.) between the different features. Reverse engineering such a model is the first step towards analysing an existing variability-intensive system. The goal of this master thesis is to define, implement, and (potentially) execute a reverse engineering approach for the Odoo ERP using the various artefacts available in the community version (https://github.com/odoo/odoo).
