---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "ChatGPT, Could you please generate my exam?"
subtitle: ""
summary: ""
authors:
    - xavier-devroey
tags: 
  - Education
  - Academic Life
  - Large Language Model
categories: []
date: 2025-01-17T00:00:00+02:00
lastmod: 2025-01-17T00:00:00+02:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Image from DC Studio on Freepik"
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

It's time for the January exams. Three years ago, my colleague Benoît Vanderose and I created a verification and validation course for the MSc in Software Engineering students. From the start, we both thought we needed a practical exam where students actually perform V&V tasks. So, for our exam, students have to analyze a codebase, read SonarQube reports, refactor code, correct bugs, and write tests. This was quite unusual for them (most courses are evaluated using projects or paper exams), and the students' reaction three years ago was, let's say, interesting.

Our major challenge is that we need a codebase that is not too big to be understandable but not too small to have non-trivial bugs, code smells, and symptoms of bad development practices. For the past three years, we have used the [JPacMan framework of the SERG teams at TU Delft](https://github.com/SERG-Delft/jpacman) (thank you for making it open source 🙏). The project implements a JPacMan game with some tests (but not too much, which is what we were looking for). We modified the code several times to add architectural smells, bugs, and antipatterns. But after three years, of course, the code got passed along between students. So, this year, we decided to use the project for the practical sessions and to find another project for the exam.

To be honest, this is kind of annoying. Most Java codebases on GitHub are too big for a 4-hour exam or too simple to have challenging enough exam questions. While I was looking for an existing open-source codebase, Benoît (jokingly, or maybe not) suggested that we could use ChatGPT to generate one that fits our needs. So, I went down the ChatGPT rabbit hole and took a day to create a Java codebase for a popular game: chess. The choice of a popular game serves two purposes: first, there is a higher chance that students are familiar with the rules and spend less time understanding them; second, there is a higher chance that ChatGPT can generate (nearly) valid code for the game.

Doing so-called "prompt engineering" is not easy. There are a lot of trials and errors, and I think I am generally not that good at it. Or at least not good at expressing what I want clearly and commonly. To overcome this, I applied a trick that Martin, one of the PhD students of our team, showed me: instead of directly asking for the result, ask ChatGPT to generate a prompt that will produce the result and edit it to your needs. So here is the prompt I used: 

```
Please generate a prompt asking to produce the Java source code of a chess game 
with a graphical user interface.
```

And here is the result I got:

```
Please provide the complete Java source code for a chess game 
with a graphical user interface (GUI). The code should include:
1. A main class to launch the application.
2. A GUI that displays the board and pieces using Java Swing or JavaFX.
3. Functionality to move pieces according to chess rules.
4. A mechanism to validate legal moves and enforce rules like check, checkmate, and castling.
5. Support for two-player mode (human vs. human) and optional basic AI for human vs. computer.
6. Visual feedback for selected pieces and possible moves.
7. Clear comments to explain key parts of the code.
The code should be modular, well-structured, and follow standard Java coding conventions.
```

Which is way more than what I would have included in my prompt. The result was a simple version of the game. It was not very modular, with pieces represented as strings and everything UI, game logic, etc. mixed into two classes. Not all the rules were implemented, and ChatGPT kindly asked me if it wanted me to do it. Of course, I said yes. It gave me a more complete game, with everything still mashed up into two classes. My next prompt was the following:

```
Refactor the code to follow the model-view-controller architecture. 
```

To be honest, I was not sure it would work, but to my surprise, it did. ChatGPT refactored the code and created three classes for the model, the view, and the controller. I also asked to add some Javadoc, which it did. Next, I wanted to refactor the code to make the different pieces independent classes instead of string values:

```
Refactor the code to extract the different pieces of the chess game and create a 
corresponding inheritance hierarchy. Each kind of piece should have its own class. 
Each class should describe the logic of the movements allowed for that piece.
```

And again, nice results. It generated classes only for some pieces, but after asking to generate classes for all the pieces, I had a running game with only very few minor edits to make for the code to compile. I used a few additional prompts to refactor the code and add some specific game logic, and in less than a day, I had a fully working codebase for a widely known game. I took care to commit each version of the game generated by ChatGPT into a private for now (sorry, students 😉) GitHub repository. So, in the coming years, when we change the exam codebase again, we will have a codebase ready for the practical sessions of the course with a Git history this time.
