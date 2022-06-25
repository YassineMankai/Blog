---
title: "Procedural Generation for game development"
content: "implementing unity tools"
image: "/uploads/cave_finalgrid.PNG"
links:
    - icon: fab fa-github
      url: https://github.com/YassineMankai/ProceduralCaveGeneartion
date: ""

---

## Context

This is a series of unity implementations of procedural generation methods based on the great work of Sebastian Lague [Youtube Channel](https://www.youtube.com/c/SebastianLague). This youtuber has an excelent content on different video-game/computer Graphics related subjects. 

The main idea of this series is to follow some of his tutorials and reproduce them. I tried to avoid copying directly from the source and to steer away from the beginning when it comes to data structures and algorithms, to make sure I focus on the idea and apply it correctly.

## Cave Generation:

#### Tutorial: [PlayList](https://www.youtube.com/watch?v=v7yyZZjF1z4&list=PLFt_AvWsXl0eZgMK_DT5_biRkWXftAOf9&ab_channel=SebastianLague)


#### Goal:

The goal of this project is to create a unity tool that randomly generates a cave plan and then create the appropriate mesh. To demonstrate a use case for such system, I used it in a simple roll-a_ball game where the player is instanciated as a cube in a fixed corner and should cover all the rooms (to color them) in order to win the game. A cave is defined as a number of rooms connected by bridges. Any room is ensured to be accessible from the starting position.

#### Implementation:

I will start with the main function that is called each time a cave generation is requested. This function uses a number of methods each one of them implements a step of the pipeline. You can find below a snippet of the code.  

```c#
   public void GenerateMap()
    {
        mapDS = new MapDS(width, height);
        RandomFillMap();
        SmoothMap(nbIterations);
        CalculateBlocks(wallBlockSizeThreshold, roomSizeThreshold);
        CreateBridges(bridgeRadius);

        mapDS.setBorder(borderSize); // last thing to be applied
        MeshGenerator meshGen = GetComponent<MeshGenerator>();
        meshGen.GenerateMesh(mapDS, 1, true, true);
    }
```

The cave is represented in memory as a grid of integers representing each the state of a cell (a cell can be a wall or empty). 

 - We start by instantialting a data structure *mapDS* that will store this grid. Then, we randomly fill this grid. We obtain something like this : 
![randomly generated grid](/uploads/cave_randomgrid.png)
 
 - As you can see, the grid is too noisy and does not show any cave-like structure. For this, we use the *SmoothMap* function which is based on a [cellular automaton](https://en.wikipedia.org/wiki/Cellular_automaton) procedure. I used the same parameters as those presented in the youtube channel I mentioned above. We can see below the results of this step. It appears a clear division into rooms. They are still disconnected and we have other problems like small rooms or small wall blocks.
![randomly generated grid](/uploads/cave_smoothgrid.png)

 - The next step represented by the CalculateBlocks and CreateBridges methods. They aim at infering some information on the generated grid. We store in specific data structure informations on each room (size, position of each cell, border cells, ...). Using this information we filter small rooms and small blocks of wall. I generate bridges between rooms based on a [minimum spanning tree](https://en.wikipedia.org/wiki/Minimum_spanning_tree) algorithm using the distance between the closests two cells of the considered rooms. This is a different approach that I preferred to the one presented in the tutorial. Finally, an outer border is added to the grid.
![randomly generated grid](/uploads/cave_finalgrid.PNG)

 - I should note that until now, we're only manipulating data structures without any visual output. The photos I showed above use the following step to generate a mesh according to the grid. This seperation between the data and the visual is even more clear in the unity project as there are two scripts (attached to the same GameObject) each handling one aspect of the cave generation. The first component is called *MapGenerator* and contains the three first steps and the *GenerateMap* function. It also calls the *GenerateMesh* method of the second component called *MeshGenerator* after ensuring that the data is ready. The *GenerateMesh* method is based on the [marching square algorithm](https://en.wikipedia.org/wiki/Marching_squares). There is a big switch code block that I copied from the tutorial as it includes the handling of 16 cases. The idea is to triangulate the grid and get a mesh that covers the wall part. I then extended the same idea to generate a mesh for the side of the wall and a mesh for the interior of each room. In this part, I learned how to manipulate meshes in unity. It is similar to any graphics API as we have a vertices/triangles structure to fill. Then, you need to instantiate a *Mesh* object and to set its attributes (vertices, traingles, uv, ...) to the list of values you have . You then need to add a *MeshFilter* component to a gameObject and set it's mesh attribute to the *Mesh* object you created.
 
 ```c#
	List<Vector3> vertices;
	List<int> triangles;
	List<Vector2> uv;
	
	// Fill vertices, triangles and uv with the values you calculated in the previous steps
    
	Mesh mesh = new Mesh();
	mesh.vertices = vertices.ToArray();
	mesh.triangles = triangles.ToArray();
	mesh.uv = uv.ToArray();
	meshFilter.mesh = mesh;
	mesh.RecalculateNormals();
```

I present below a short video of the final result:

{{< youtube ouYJ5Ux64c8 >}}


## Planet Generation:

#### Tutorial: [PlayList](https://www.youtube.com/watch?v=QN39W020LqU&list=PLFt_AvWsXl0cONs3T0By4puYy6GM22ko8&ab_channel=SebastianLague)

#### Goal:

The goal of this project is to make a unity tool that 'pseudo-randomly' generates a planet surface and allows the user to define a color map applied according to the point elevation. The system exports a set of parameters that serves as control tools to shape the planet.

#### Implementation:

##### Data representation

The different data structures used in this tool are centered in the C# class *MeshDataStructure*. To simplify the calculations needed, I decided to work internally with a quad-based mesh. Vertices positions are stored in the list *verticesDS* as vector3 points. Faces are stored as a Vector4int list *quadsDS*. Before each 'generate planet call', I apply the noise filters on the point positions and forward this data to the meshFilter component of the GameObject.


##### Generating a sphere

To generate the rough surface of a planet, I decided to implement a [catmull-clark subdivision](https://en.wikipedia.org/wiki/Catmull%E2%80%93Clark_subdivision_surface) of a cube. For an interation of level 5, the obtained mesh is close to a sphere and the resolution is good enough for a detailed displacement of the points on the surface. The implementation can be found in the *subdivide* of the *MeshDataStructure* class. The calculations are optimized by caching the neighboorhood of each vertex (a map vertex to faces and a map vertex to edges).

##### Using noise to manipulate the surface elevation

Using a implementation of the simplex noise provided by the libnoise-dotnet library, we can implement a noise filter to get a more planet-like shape. To describe various types of continent and island formations, we can accumulate different sets of noises (different parameter values). Each set is a multi-layered noise implemented as the sum of frequency-increasing simplex evaluations. The increase rate of a noise set is determined via the roughness parameter. The persistence parameter is used to modulate the change of the amplitude in relation to the frequency.

#### Working with a node-based shader material

![](/uploads/node_based_shader.png)

I present below a short video of the final result:

{{< youtube gt-e_55kvLU >}}


## Unity features I learned to use:
 - Using the *Mesh* and *MeshFilter* components to generate a custom mesh.
 - Using the Universal Render Pipeline to generate a custom shader (Material) using a node-based graphical interface
 - Creating a custom editor (*CustomEditor*) section that appears on the inspector of a gameobject and extend its features with buttons and other editing elements. 
 - The use of the Gradient unity tool for texture generation.



