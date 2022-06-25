---
title: 'Procedural Generation for game development'
content: "implementing unity tools"
github_link: https://github.com/YassineMankai/ProceduralCaveGeneartion

---

## Context

This is a series of unity implementations of procedural generation methods based on the great work of Sebastian Lague [Youtube Channel](https://www.youtube.com/c/SebastianLague). This youtuber has an excelent content on different video-game/computer Graphics related subjects. 

The main idea of this series is to follow some of his tutorials and reproduce them. I tried to avoid copying directly from the source and to steer away from the beginning when it comes to data structures and algorithms, to make sure I focus on the idea and apply it correctly.

## Cave Generation:

### Goal:

The goal of this project is to randomly generate a cave plan and then create the appropriate mesh. The player is then instanciated in a fixed corner and should go to all rooms (to color them) to win the game. A cave is defined as a number of rooms connected by bridges. Any room should be accessible from the starting position.

### Implementation:

As I stated above, the implementation is partially based on a youtube tutorial. It contained a number of data structure manipulations and algorithm implementations that are outside the scope of this lab. For this, I will spare those details for a potential other post in the future and focus more on the general pipeline.

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


### Unity features I learned to use:
 - Using the *Mesh* and *MeshFilter* components to generate a custom mesh.
 - Using the Universal Render Pipeline to generate a custom shader (Material) using a node-based graphical interface
 - Creating a custom editor (*CustomEditor*) section that appears on the inspector of a gameobject and extend its features with buttons and other editing elements. 