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

## Tutorial Steps
### Step 1: Create a New Project
Launch Unreal Engine 5 from the Epic Games launcher.

Select the "Games" development category, then select the "Blank" template.
> :notebook: This tutorial can be applied in non-blank templates or existing projects. A blank template is utilized for demonstration and ease-of-learning.

Leave the "Project Defaults" section unchanged.

Select a location to store your project on your local disk.

Name your project.
