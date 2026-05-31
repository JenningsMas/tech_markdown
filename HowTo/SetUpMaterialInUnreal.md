# How to Create and Configure a Game-Ready Material Using Packed Texture Maps In Unreal Engine 5

## Overview
This guide explains how to create and set up a new, game-ready material in Unreal Engine 5 using packed ORM maps.

> :bangbang: This guide assumes you are familiar with the basic terminology of texturing and 3D prop modeling. For a brief overview of these terms, see [ThreeDee Design's 3D Art Glossary](https://www.threedee.design/3d-glossary/)

> :bangbang: This guide assumes you are creating a material for use in a 3D video game. Some steps may differ when producing materials for other types of media.

## What You Will Accomplish
By following this guide, you will:

* Create a new Unreal Engine project.
* Successfully create a new material with color, normal, and Occlusion, Roughness, Metallic (ORM) maps.
* Apply your material to a static mesh object.

## Overview: What is a Packed ORM Map?
A packed Occlusion, Roughness, Metallic (ORM) map is a single texture file that contains multiple color channels for each attribute. A packed ORM map uses the red, green, and blue color channels to contain the information for a texture's occlusion, roughness, and metallic properties respectively. 

### Why Use a Packed ORM Map?
A packed ORM map has two main benefits. First, it reduces file size by storing multiple texture attributes in a single file, which helps reduce load times and improve performance for real-time applications like video games. Secondly, it saves time by allowing 3D artists to control multiple texture attributes in a single file.

## Before We Begin (Prerequisites)
Before beginning this tutorial, ensure you have the following:

* The latest version of the Epic Games Launcher, available [here](https://store.epicgames.com/download?lang=en-US).
* The latest version of Unreal Engine 5. For a tutorial on how to install Unreal Engine 5, see [Epic Game's Official Guide](https://www.unrealengine.com/download).
    > :bangbang: This guide utilizes Unreal Engine version 5.7.3. Ensure you have the correct version before proceeding.
* A static mesh object which will use your material.
* A base color, normal, and ORM map.
    > :bangbang: Take note of the file path of your static mesh and texture maps. You will need it later to import your assets into Unreal Engine.

## Tutorial Steps
### Step 1: Create a New Project
Launch Unreal Engine 5 from the Epic Games launcher.

Select the "Games" development category, then select the "Blank" template.
> :notebook: This tutorial can be used in other templates or existing projects. A blank template is utilized for demonstration.

Leave the "Project Defaults" section unchanged.

Select a location to store your project on your local disk.

Name your project & create it.

Wait for Unreal Engine to load before proceeding.

### Step 2: Import Maps and Static Mesh
In your new project, open the Content Browser by clicking the "Content Browser" button.

The Content Browser is where all project assets are organized and managed.

![An example of a filled content browser](https://github.com/JenningsMas/tech_markdown/blob/main/HowTo/Img/Ue5/content_brow.png)
*An example of a filled content browser containing multiple types of assets.*

Open your operating system's file explorer and navigate to the filepath of your static mesh and texture maps.

Click and drag each file into the Unreal Engine Content Browser. This will open the "Import" menu for each file.

* For static mesh imports, ensure the "Import Static Meshes" checkbox is checked, and the "Recompute Normals", "Recompute Tangents" and "Remove Degenerates" checkboxes under the "Build" section are unchecked. 

    * Additionally, if materials were applied to the mesh in an external 3D art software, ensure the "Import Materials" checkbox under the "Materials" section is unchecked and the "Import Textures" checkbox under the "Textures" section is unchecked.

Your content browser should now contain a static mesh object, a base color map, a normal map, and an ORM map.

> :bangbang: Unreal Engine may treat your ORM map as a normal and/or enable its "SRGB" setting. These setting must be changed to ensure your ORM map applies accurately on your material.
>
>* Double-click on your imported ORM map to open its configuration settings.
>
> * Ensure the "Compression Settings" dropdown is set to "Default (BC1 or BC3 with A)
>
>* On the "details" sidebar, scroll down to the "Texture" category, then ensure that the "SRGB" checkbox is unchecked.

### Step 3: Create a New Material
In the content browser, right click and select "Materiel" to create a new empty material.

Name your material.

> :notebook: It is best practice to name your material "m_materialName". This denotes the file as a material and helps with project organization

### Step 4: Add Texture Maps to Your Material
Double click on your new material to open the material editor. You will see this screen:

![An image of an empty material](https://github.com/JenningsMas/tech_markdown/blob/main/HowTo/Img/Ue5/blank_map.png)

In the center of the material editor is the "material graph". The material graph is a collection of nodes that define the attributes of a material.

By default, all new materials contain a base material node which has several inputs corresponding to the material's attributes. We will use additional nodes to modify these inputs with our texture maps.

From the Content Browser, drag and drop your base color, normal, and ORM maps into the material graph. You should now see all three maps as nodes on the graph.

### Step 5: Connect Maps to Base Material Node
Your texture map nodes contain several connections that connect to the base material node to affect its attributes.

Connect the RGB connection of your base color map to the Base Color input on the base material node.

Connect the RGB connection of your normal map to the Normal input on the base material node.

ORM maps must be connected to three different inputs to apply correctly.

>:bangbang: Unreal Engine labels ORM maps as "ARM" in the material editor. ARM is an alternate acronym for Ambient Occlusion, Roughness, Metallic. There is no difference between "ARM" and "ORM" maps.

* Connect the R connection to the Ambient Occlusion input.

* Connect the G connection to the Roughness input.

* Connect the B connection to the Metallic input.

If done correctly, your material graph should appear similar to the following:

![An image of a configured material](https://github.com/JenningsMas/tech_markdown/blob/main/HowTo/Img/Ue5/finished_map.png)

Your material is is now properly configured.

### Step 6: Add Material to Static Mesh
In the Content Browser, double click on your static mesh to open the Static Mesh Editor.

In the materiel section of the Static Mesh Editor, click on the dropdown menu inside the "Element 0" section.

Select your configured material from the options box.

Your material should now display correctly on the static mesh. To verify, drag and drop the static mesh from the Content Browser into the scene and observe its appearance.

![An image of a mesh with material](https://github.com/JenningsMas/tech_markdown/blob/main/HowTo/Img/Ue5/finished_mesh.png)

## Expected Result
Your static mesh inside your scene should now be textured and correctly display its material. When lit, it should have accurate reflections based on the normal and ORM maps. 
