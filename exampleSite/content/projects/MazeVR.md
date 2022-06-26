---
title: "A VR game: MazeVR"
image: "/uploads/maze.jpg"
content: "This project is a VR maze-based game "
links:
    - icon: fab fa-github
      url: https://github.com/YassineMankai/mazeVR
date: 2021-09-00

---
# Context:

HCI-902a: Fundamentals of XR

# Introduction:

This project has two main objectives: discovering the process of designing a virtual reality experience and learning the basic tools of Unity. We had at our disposal a Pico G2 4K VR headset with a remote controller and both had 3 degrees of freedom (the 3 axes of rotation). We were asked to start by fixing a problem of our choice and try to solve it by proposing a VR application.

[Github repository](https://github.com/YassineMankai/mazeVR)

[Final report](/uploads/FofER_report.pdf)

P.S: More details on the designing and implementation process can be found in the report.

{{< youtube 1WCJ7USJIhc >}}

# State:

finished

# Group members:

* Lauriane Bertrand
* Yassine Mankai

# Setup:

Pico G2 4K + Unity + Pico SDK

# Steps:

## 1. Designing a problem:

We discussed the different advantages a VR app can have compared to traditional solutions and we concluded that a sense of presence is a major game-changer when it comes to conveying an experience. From there, we worked on the meaning of presence as it's a complex concept and englobes different dimensions like space, time, senses, interaction ... Then, we decided to focus on situations where the spatial aspect of immersion is more prominent. The problem to which we converged concerns users for whom VR can be a perfect tool to escape their confined personal spaces and engage in entertaining open experiences where they can explore and discover worlds. We formulated then a question that our solution should answer: “How can we make the user explore while being entertained at home?”

## 2. Designing a solution:

To find our design, we chose to write different scenarios and think about how to solve the proposed issues. We made several sketches and then iterated over them to form coherent prototypes.
We decided then to focus on the prototype that had the best promising features (open to expansion, less monotone, more entertaining, motivate more exploration and less linear progress, ...).
Our final design was a game where the user is placed in a maze that keeps changing and the goal is to find portals to different mini-worlds where mini-games (puzzles) could be solved to gain keys. After collecting a certain number of keys, the player can open the final door and access the reward. The final design included also simple gameplay with victory constraints and penalties for failing mini-games (timers, light shutdowns, ...)

## 3. Implementing the solution:

As a final version of this project, we implemented a VR game. It’s divided into one main scene/universe (the maze) and two mini-games/worlds (PipePuzzle and Differences).  A portal system links the main scene to the others and no special order is needed to solve the mini-games. Text hints are present in each scene to indicate what should be performed.

We present here the different scenes:

### Main scene, Maze:

![Main scene: Maze](/uploads/maze.jpg)

### Mini-game, Differences:

![Mini-game: Differences](/uploads/differences.jpg)

### Mini-game, PipePuzzle:

![Main scene: PipePuzzle](/uploads/pipepuzzle.jpg)

## 4. Evaluating the solution:

We discussed in the last part of our report the different issues we found in our final product. Some of them were related to what could be implemented in the context of the project (first experience with the Pico Unity SDK + a 7-week project).  But other problems were related to the ideas we presented and could only be avoided by going through a new design iteration.

# Personal contribution:

* Important contribution to the design process
* Creation in Unity3D of MainScene (maze) and PipePuzzle scene
* Implementation of a simple maze generation algorithm: flipping the state (wall/ empty) of n (>size) randomly selected cells according to a probability calculated based on the current state of the cell's neighborhood.
* Implementation of a pipeline puzzle generation algorithm based on a randomly weighted grid-like graph and a greedy "shortest" path calculation.

# New Skills:

* Initiation to Unity3D (scenes, scripts, input, ...)
* Initiation to the Pico SDK
* Developping a VR game