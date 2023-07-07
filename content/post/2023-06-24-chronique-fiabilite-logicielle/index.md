---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Software reliability: is ignorance bliss?"
subtitle: "Why managing system quality and reliability isn't trivial"
summary: "Why managing system quality and reliability isn't trivial. Have you ever wondered how software systems are born and how they die? There’s the famous source code and the (sometimes unpopular) algorithms, but how is it all put together? This practice is known as software engineering."
authors:
    - xavier-devroey
tags: 
    - Software Reliability
categories: []
date: 2023-06-28T20:01:42+02:00
lastmod: 2023-06-28T20:01:42+02:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Image by rawpixel.com on Freepik"
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

*The French version is available [here](https://www.lalibre.be/economie/decideurs-chroniqueurs/2023/06/27/fiabilite-logicielle-les-ignorants-sont-ils-vraiment-benis-5S2SM7GVBVB5TA62UXRCW4JHIU/)*

Have you ever wondered how software systems are born and how they die? There's the famous source code and the (sometimes unpopular) algorithms, but how is it all put together? This practice is known as software engineering. Although it has evolved considerably in recent years, it is still often more of an art than a science. It's not surprising when you think about it: successfully building software systems and products requires understanding the users and the context in which they operate. And it's probably one of the most challenging exercises imaginable, given the diversity found in our human societies. I'd go so far as to say that there's something extraordinary about being able, for example, to contact friends by videoconference from the other side of the world. The complexity of the systems involved in this simple action is titanic. And the user, unaware of the machine's workings, finds this normal. However, such complexity is not free, and any system is only as reliable as its weakest component. In a world where software is created by assembling components developed by others, this is a lesson we are regularly and painfully reminded of.

For example, in December 2021, the Log4Shell vulnerability posed severe security problems: 93% of online services worldwide were vulnerable. It was a flaw in a component enabling an application to record messages in a logbook for analysis and tracking purposes. This basic function is invisible to users and commonly used during software development. This function is outsourced to a component (a software library) used by many applications: Log4J. Unfortunately, it was only maintained by a handful of volunteer developers. Fortunately, thanks to its open-source nature, developers could limit the impact. This simple example illustrates that, in a globalized world, managing the quality and reliability of our systems is no trivial matter. And if the average person can continue to use these systems without knowing the ins and outs of how they work (had you heard of Log4Shell before reading this column?), they are also ignoring the risks they are taking. So, is ignorance bliss?  

Yes, because systems of unsuspected complexity provide everyday services. And no, because by not being aware of how they work, even globally, we (from decision-makers to IT specialists) can find ourselves the victims without understanding why. So what can we do? First, realize that complexity is part of modern software systems, and stop hiding behind a convenient ignorance ("I don't know anything about computers"). You don't need to understand the dynamics of gas phase changes in a fridge to know that it's necessary to introduce construction standards, guaranteeing it won't start a fire when turned on. In the same way, you don't need to understand the theory of programming languages to demand that a software system meets standards of operational quality, environmental friendliness, and so on. Thus, software engineering may no longer be in the news only when a system crashes so masterfully that an army of developers is driven to the brink of burnout to avert disasters but also when a system proves remarkably reliable in a context of unprecedented complexity in the history of humankind.
