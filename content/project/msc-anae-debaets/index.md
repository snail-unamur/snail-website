---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Automated Vulnerability Injection in Web Applications: A Tool to Support Cybersecurity Education"
summary: ""
authors: 
 - anae-debaets
tags: 
  - Msc Thesis
  - Finished
  - Cybersecurity
  - Education
  - Mutation Testing
categories: []
date: 2025-06-23T10:47:40+02:00

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Overall architecture"
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

This thesis presents the development of a configurable tool that automatically injects web application vulnerabilities into existing Django codebases to support cybersecurity education. The primary goal is to enhance hands-on learning by allowing educators and students to engage with realistic, production-like environments that incorporate well-known security flaws, specifically drawn from the OWASP Top Ten 2021. Instead of generating synthetic applications, the tool modifies authentic Django projects, ensuring pedagogical relevance and structural fidelity.

To guide and validate the tool’s conceptual design, a Systematic Literature Review (SLR) was conducted, focusing on existing approaches to vulnerability injection, security exercise generation, and automation in cybersecurity training. The SLR revealed a clear need for adaptable, user-configurable systems that balance automation with educational depth, gaps that this project addresses directly.

The final system consists of a modular backend, a web-based graphical user interface, and precise code transformation logic using the libcst library, ensuring readable and structurally sound outputs. It supports selective injection of multiple vulnerability types and provides validation features. Through a testing framework and scenario-based evaluations, the configurator proved effective in producing stable, instructive, and customizable exercises. Ultimately, this work contributes a novel open-source tool that promotes scalable, realistic, and engaging cybersecurity education.

{{< linkedinupdate "urn:li:activity:7342815445630017536" >}}