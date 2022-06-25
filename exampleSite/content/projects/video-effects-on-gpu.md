---
title: "Video Effects On GPU"
image: "/uploads/videoeffectsongpu.png"
content: "An application able to apply a series of filters on an image or a video from the GPU via WebGL and OpenGL ES then to display and save the result."
links:
    - icon: fab fa-github
        url: https://github.com/rachedwaly/Video_Effects_On_GPU
---

# Context: 
PAF: Projet d'Application Final 

# Introduction:
The context of this project was to allow students to apply the knowledge acquired in the technical courses of the first year as well as to discover certain aspects present in the courses offered by the school in the second year. The principle of PAF is to immerse yourself in a multidisciplinary project, to take the time to apply and deepen your technical knowledge, and to get to the bottom of things in a concentrated way. The project took place during the last two weeks of June 2020, which were entirely dedicated to it. We worked in a team of 4 under the supervision of Mr. Jean Le Feuvre(Associate Professor). 
The objective was to realize an application able to apply a series of filters on an image or a video from the GPU via WebGL and OpenGL ES then to display and save the result.


[List of daily reports (in french)](https://drive.google.com/drive/folders/13ttBaaSZ7IhNkeT79r5KxyiGmRaBQGI7?usp=sharing)

[Final report (in french)](/uploads/PAF_rapport.pdf)

[Github repository](https://github.com/rachedwaly/Video_Effects_On_GPU)


# Setup:
git fork from GPAC  + WebGL + Javascript + GLSL

# State:
finished

# Group members:
 - Caroline Xia
 - Mohamed Rached Waly
 - Yassine Mankai 
 - Zakary Saheb

# Personal contribution:
 - Implementation of a code pipeline using an intermediate framebuffer to iterate multiple sucessive shaders on a source video stream: managing the framebuffer swapping.
 - Creation of a shader generation system that assembles a shader code text from an object representing the wanted video effect (e.g.: a shader for a blurry effect) => automation of the video effect application.

 # New Skills:
 - Manipulating FrameBuffers
 - Understanding the basics of GPU programming
