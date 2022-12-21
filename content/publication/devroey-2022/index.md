---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: 'JUGE: An infrastructure for benchmarking Java unit test generators'
subtitle: ''
summary: ''
authors:
- xavier-devroey
- Alessio Gambi
- Juan Pablo Galeotti
- René Just
- Fitsum Kifetew
- Annibale Panichella
- Sebastiano Panichella
tags:
- Search-Based Software Testing
- Software Testing
- Test Case Generation
categories: []
date: '2022-12-20'
lastmod: 2022-12-21T09:51:11+01:00
featured: false
draft: false

url_pdf: 'https://onlinelibrary.wiley.com/share/author/DR3PP8RB8YYZGXTKR4AY?target=10.1002/stvr.1838'
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
  caption: ''
  focal_point: ''
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects:
- cyberexcellence
publishDate: '2022-12-21T08:51:11.608025Z'
publication_types:
- '2'
abstract: Summary Researchers and practitioners have designed and implemented various
  automated test case generators to support effective software testing. Such generators
  exist for various languages (e.g., Java, C#, or Python) and various platforms (e.g.,
  desktop, web, or mobile applications). The generators exhibit varying effectiveness
  and efficiency, depending on the testing goals they aim to satisfy (e.g., unit-testing
  of libraries versus system-testing of entire applications) and the underlying techniques
  they implement. In this context, practitioners need to be able to compare different
  generators to identify the most suited one for their requirements, while researchers
  seek to identify future research directions. This can be achieved by systematically
  executing large-scale evaluations of different generators. However, executing such
  empirical evaluations is not trivial and requires substantial effort to select appropriate
  benchmarks, setup the evaluation infrastructure, and collect and analyse the results.
  In this Software Note, we present our JUnit Generation Benchmarking Infrastructure
  (JUGE) supporting generators (search-based, random-based, symbolic execution, etc.)
  seeking to automate the production of unit tests for various purposes (validation,
  regression testing, fault localization, etc.). The primary goal is to reduce the
  overall benchmarking effort, ease the comparison of several generators, and enhance
  the knowledge transfer between academia and industry by standardizing the evaluation
  and comparison process. Since 2013, several editions of a unit testing tool competition,
  co-located with the Search-Based Software Testing Workshop, have taken place where
  JUGE was used and evolved. As a result, an increasing amount of tools (over 10)
  from academia and industry have been evaluated on JUGE, matured over the years,
  and allowed the identification of future research directions. Based on the experience
  gained from the competitions, we discuss the expected impact of JUGE in improving
  the knowledge transfer on tools and approaches for test generation between academia
  and industry. Indeed, the JUGE infrastructure demonstrated an implementation design
  that is flexible enough to enable the integration of additional unit test generation
  tools, which is practical for developers and allows researchers to experiment with
  new and advanced unit testing tools and approaches.
publication: '*Software Testing, Verification and Reliability*'
doi: https://doi.org/10.1002/stvr.1838
---
