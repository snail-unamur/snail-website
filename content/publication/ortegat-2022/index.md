---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: Towards Automated Testing for Simple Programming Exercises
abstract: "Automated feedback and grading platforms can require substantial effort when encoding new programming exercises for first-year students. Such exercises are usually simple but require defining several test cases to ensure their functional correctness. This paper describes our initial effort to leverage automated test case generation for simple programming exercises. We rely on grey-box fuzzing and random combinations of method calls to test the students’ solutions and compare their execution to the results produced by a reference implementation. We implemented our approach in a prototype, called SimPyTest, openly available on GitHub. We discuss its usage and possible future extensions."
authors:
  - pierre-ortegat
  - benoit-vanderose
  - xavier-devroey
tags:
  - Education
  - Software Testing
  - Test Case Generation
date: '2022-11-18'
lastmod: 2022-09-01
featured: false
draft: false

# links: 
# - name: ""
#   url: ""
url_pdf: 'https://xdevroey.be/publication/ortegat-2022/ortegat-2022.pdf'
url_code: 'https://github.com/snail-unamur/unamur-tests-python-auto'
url_dataset:
url_poster:
url_project:
url_slides: 
url_source:
url_video: 'https://youtu.be/yB9kHv4xmLg'


# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ''
  focal_point: ''
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects:
  - msc-pierre-ortegat
publishDate: '2022-09-01T00:00:01.633930Z'
publication_types:
- '1'
publication: "*Proceedings of the 4th International Workshop on Education through Advanced Software Engineering and Artificial Intelligence (EASEAI '22)*"
doi: 10.1145/3548660.3561334
---

{{< youtube yB9kHv4xmLg >}}