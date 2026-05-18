# How to Create and Configure a Game-Ready Material Using Texture Maps In Unreal Engine 5

## Overview
This guide explains how to create and set up a new, game-ready material in Unreal Engine 5 using packed ORM maps.

> :bangbang: This guide assumes you are familiar with the basic terminology of texturing and 3D prop modeling.

> :bangbang: This guide assumes you are creating a material for use in a 3D video game. Some steps may differ when producing materials for other types of media.

## What You Will Accomplish
By following this guide, you will:

* Create a new Unreal Engine project.
* Successfully create a new material with color, normal, and Occlusion, Roughness, Metallic (ORM) maps.
* Apply your material to a static mesh object.
* Troubleshoot potential errors.

## Before We Begin (Prerequisites)
Before beginning this tutorial, ensure you have the following:

* The latest version of the Epic Games Launcher, available [here](https://store.epicgames.com/download?lang=en-US).
* The latest version of Unreal Engine 5. For a tutorial on how to install Unreal Engine 5, see [Epic Game's Official Guide](https://www.unrealengine.com/download).
    > :bangbang: This guide utilizes Unreal Engine version 5.7.3. Ensure you have the correct version before proceeding.
* A static mesh object to apply your material to.
* A base color, normal, and ORM map.
    > :bangbang: Make note of the file path of your static mesh and texture maps. You will need it later in this tutorial.

## Tutorial Steps
### Step 1: Create a New Project
Launch Unreal Engine 5 from the Epic Games launcher.

Select the "Games" development category, then select the "Blank" template.
> :notebook: This tutorial can be applied in non-blank templates or existing projects. A blank template is utilized for demonstration and ease-of-learning.

Leave the "Project Defaults" section unchanged.

Select a location to store your project on your local disk.

Name your project & create it.

Wait for Unreal Engine to load before proceeding.

### Step 2: Import Maps and Static Mesh
In your new project, open the Content Browser by clicking the "Content Drawer" button.

The Content Browser is where all project assets are organized and managed.

Open your operating system's file explorer and navigate to the filepath of your static mesh and texture maps.

Click and drag each file into the Unreal Engine Content Browser. This will open the "Import" menu for each file.

* For static mesh imports, ensure the "Static Mesh" checkbox is checked.

* For texture map imports,

By default, Unreal Engine will enable the "SRGB" setting on your imported ORM map. This setting must be disabled to ensure your ORM map applies accurately on your material.

Double-click on your imported ORM map to open its configuration settings.

On the "details" sidebar, scroll down to the "Texture" category, then uncheck the "SRGB" checkbox.

### Step 3: Create a New Material
In the content browser, right click and select "Materiel" to create a new empty materiel.

Name your material.

> :notebook: It is best practice to name your material "m_materialName". This denotes the file as a material and helps with project organization

### Step 4: Configure Your Material
Double click on