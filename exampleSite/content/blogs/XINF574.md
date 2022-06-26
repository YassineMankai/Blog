---
title: 'Digital Representations and Analysis of Shapes'
date: 2021-11-27

---

# Context: 
X-INF574: Digital Representations and Analysis of Shapes.

### Course description: (source: moodle)

This course will introduce the fundamental concepts for creating and analyzing shapes on the computer. We will start with generating and representing smooth curves in 2d using parametric and implicit curves. We will then move to various techniques for shape representation in 3d with special emphasis on triangle meshes and associated methods. At the same time, we will introduce methods for shape analysis and in particular defining and computing similarity between shapes, and shape matching (establishing correspondences between points on shapes). Topics will include:

 - Real/Homogeneous Coordinates + Affine/Projective Transformations.
 - Parametric and Implicit Representations for Curves.
 - Bézier curves and the de Calsteljau evaluation algorithm.
 - Triangles meshes
 - Subdivision Surfaces.
 - Point cloud representation and processing algorithms.
 - Shape Processing and Analysis -- Simplification, segmentation, vector field processing, curvature and feature detection.
 - Rigid Registration.
 - Shape retrieval, non-rigid matching and correspondence. Data-driven methods.


# Lab Assignment:
The lab is a series of exercises that aim to have a practical grasp on the different topics of the course (implementation of algorithms and visualization of results).

# Setup:
Visual Studio 2019/ C++/  LibiGL/ Eigen library 


# State:
finished

# New Skills:

## 1st Lab: Homogeneous coordinates and linear transformations

[assignement](https://www.enseignement.polytechnique.fr/informatique/INF574/TD/TD1/INF574-TD1-1.html)

 - Quick introduction to Libigl
 - Animating a model: affine transformation + quaternions

## 2nd Lab: A basic editor for curve interpolation

[assignement](https://www.enseignement.polytechnique.fr/informatique/INF574/TD/TD2/INF574-TD2-1.html)

 - Linear interpolation
 - Function interpolation: Lagrange interpolation/ Cubic spline interpolation/ Drawing tangents
 - Curve interpolation: Hermite cubic spline interpolation/ Drawing tangents

## 3rd Lab: Modeling 3D shapes with Bézier curves

[assignement](https://www.enseignement.polytechnique.fr/informatique/INF574/TD/TD3/INF574-TD3-1.html)

 - Evaluating and Rendering a Bézier curve using the de_casteljau algorithm
 - Rendering a Bézier curve by subdividing the control point
 - Modeling a 3D shape using a curve and normal loops.

## 4th Lab: A first 3D interface to manipulate mesh structures

[assignement](https://www.enseignement.polytechnique.fr/informatique/INF574/TD/TD4/INF574-TD4-1.html)

 - Manipulating a face-triangle structure.
 - Manipulating a half-edge structure.
 - Calculating the degree of each vertex
 - Computing the normals
 - Evaluating the number of connected components of the boundary graph.
 - Computing the Gaussian curvature.

## 5th Lab: Iterative closest point

[assignement](https://www.enseignement.polytechnique.fr/informatique/INF574/TD/TD5/INF574-TD5-1.html)

 - Using a kd-tree for a point cloud structure
 - Normals estimation
 - Implementing the ICP method

## 6th Lab: Mesh generation and subdivision surfaces

[assignement](https://www.enseignement.polytechnique.fr/informatique/INF574/TD/TD6/INF574-TD6-1.html)


