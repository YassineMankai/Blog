---
title: 'IGD301: Lab 1 & 2'
description: Setup a blog and a unity project
draft: false

---
## Context
This post is part of the homework for the Human-Computer Interaction for Mixed Reality course I'm taking at Telecom Paris. In this post, I will discuss two points:
 - How I created this static website.
 - My experience with Unity 3D.
 
 
## LAB-1: Blog

### Setup

It's actually quite easy. The first steps follow directly the instruction described in this youtube video.

{{< youtube ResipmZmpDU >}}

You would need as explained a github account (to fork the hugo template you want to use), a forestry account (to manage the content of the blog) and a netlify account (to deploy the website). After the steps described in the video, you can change the config.yaml file as you wish to setup the website name and some generic parts.

I should note that the forestry step is not necessary. After setting up the blog, I found that it complicates the procedure specially for the template I chose and I decided to work directly on the github repository by generating a new markdown file for each post. I only use forestry to manage Media file since it's easier that way.

### Choose your template

I found the "hugo-profile" the most suited template. It's simple enough to use and proposes good amount of freedom concerning what part to include in the blog. the aesthetic was perfect for my taste. I liked its simple scroll-down mechanism for each section and its card-based layout for the projects and the blog posts.

### Write a blog post (or add a project)

A post is defined by a single markdown file. These file follow standard structure. I based my posts on existent examples and on the following [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet "Markdown Cheatsheet").


## LAB-2: Unity 

I had the opportunity to use  Unity on a social VR project in June 2021. We created a selfie tool that works for Unity games developped for Oculus Quest. The tool allows the user to merge real life and virtual elements in the final photo and we used a webcam that we mounted on one of the controllers to capture the real world. 
Unity is an engine that allows easy development of games and 3D application. It is based on a hierarchical representation of the objects in the scene and on a Component-based architecture to simulate behaviour. You have pre-existant components for standard things like transform, mesh, material, rigid body, ... And, you can add scripts for specific actions. You have also an input system that you can use to read values from keyboard, mouse or a VR controller.
Since I already had Unity installed before, I did not have much to do in the scope of this lab in order to setup a project. I only uploaded the last version then (2020.3) and created an new empty Unity 3D project.
