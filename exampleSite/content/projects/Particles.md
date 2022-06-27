---
title: "It’s all particles"
image: "/uploads/particles.PNG"
content: "This project is an implementation of a scientific article about position based dynamics"
links:
    - icon: fab fa-github
      url: https://github.com/YassineMankai/unified_particle_system
date: 2022-03-12

---
# Context:

X-INF585: Computer Animation


{{< youtube sNLf50y6ePw >}}

# Introduction:

This project aims at implementing different features explored by M ̈uller et al in the field of position based dynamics. The main idea behind their work is to create a unified solver to simulate the interaction of different types of 3D objects at once (rigid bodies, cloths, fluids..) given some environmental constraints.
In order to do so, they proposed to model each object with a set of basic particles. They opted for particles for their simplicity, versatility and specially for their ability to simulate a wide range of shapes. Constructing objects starting from particles reduces the number of collisions to process compared to complex algorithms for generating contacts between mesh based representations.

[Github repository](https://github.com/YassineMankai/unified_particle_system)

[Final report](/uploads/REPORT_INF585.pdf)

P.S: More details on the designing and implementation process can be found in the report.

# Group members:

* [Mohamed Rached Waly](https://rachedwaly.github.io/)
* Yassine Mankai

# Setup:

C++     Damien Rohmer's CGP library