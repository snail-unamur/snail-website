---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Training machine learning models for vulnerability prediction and injection using datasets of vulnerability-inducing commits"
summary: ""
authors: []
authors: 
 - jeremie-dierickx
tags: 
  - Msc Thesis
  - Finished
  - Cybersecurity Testing
  - Machine Learning
  - Mining Software Repository
  - Artificial Intelligence
date: 2022-11-04T10:14:16+01:00

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Training and testing on vulnerability inducing and vulnerability fixing commits"
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
url_pdf: "https://researchportal.unamur.be/en/studentTheses/training-machine-learning-models-for-vulnerability-prediction-and"
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

Multiple techniques exist to find vulnerabilities in code, such as static analysis and machine learning. Although machine learning techniques are promising, they need to learn from a large quantity of examples. Since there is not such large quantity of data for vulnerable code, vulnerability injection techniques have been developed to create them. Both vulnerability prediction and injection techniques based on machine learning usually use the same kind of data, thus pairs of vulnerable code, just before the fix, and their fixed version. However, using the fixed version is not realistic, as the vulnerability has been introduced on a different version of the code that may be way different from the fixed version. Therefore, we suggest the use of pairs of code that has introduced the vulnerability and its previous version. Indeed, this is more realistic, but this is only relevant if machine learning techniques can properly learn from it and the patterns learned are significantly different than with the usual method. To make sure of this, we trained vulnerability prediction models for both kind of data and compared their performance. Our analysis showed a model trained on pairs of vulnerable code and their fixed version is unable to predict vulnerabilities from the vulnerability introducing versions. The same goes for the opposite, despite both models are able to properly learn from their data and detect vulnerabilities on similar data. Therefore, we conclude that the use of vulnerability introducing codes for machine learning training is more relevant than the fixed versions.

*Internship done at the [SnT](https://www.uni.lu/snt-en/) of the [University of Luxembourg](https://www.uni.lu/en/), Luxembourg.*