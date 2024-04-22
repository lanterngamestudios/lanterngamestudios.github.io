---
title: Mesh Vegetation Painter
layout: home
---

# Mesh Vegetation Painter Docs

*Mesh vegetation painter is a tool that allows you to paint terrain vegetation detail layers on non-terrain meshes like rocks, buildings, etc...*

## Installation

- From your unity project, select `Window>Package Manager`.
- On the top left, select `My Assets` from the drop down.
- Find `Mesh Vegetation Painter` in your list of assets, select it and click `Download`.
- Once the download has finished, click `Import`
- Select what you would like to import when prompted and then click `Import`. If unsure on what to select, import everything.

## Usage
- Once the asset pack has been imported, select the `GameObject` you would like to paint vegetation details on.
- In the inspector, click `Add Component` and add `VegetationPainterV2`.
- Properties on this script are as follows:
![Script Properties](/assets/images/scriptProperties.png)

| Property 	| Description 	|
|---	|---	|
| **Data** 	| Data contains all of the data generated used to render your vegetation in editor and during Play mode. 	|
| **Max Painting Surface Angle** 	| The max angle (from VEctor3.Up)that you want to paint vegetation on, aka the maximum slope angle that vegetation can be painted on. Useful to stop vegetation from painting on the vertical side of cliffs etc... 	|
| **Max Render Distance** 	| If the user does not enable/disable this through their own code or shader, this changes how far the camera has to be before the vegetation is no longer rendered. 	|
| **Main Camera** 	| The main rendering camera in your game. If null, autoset on awake. 	|
| **Linked Terrain** 	| The terrain that the object is liked on. This is used to read vegetation prototype data such as meshes, materials, etc... 	|

- `Data` also contains more properties, visible once some vegetation has been painted:

![Data Properties](/assets/images/dataProperties.png)

| Parameter 	| Description 	|
|---	|---	|
| **Object Painted** 	| The GameObject reference to the prefab of your vegetation object (grass, fern, bush, etc...) 	|
| **Mesh** 	| The Mesh of the vegetation detail (automatically detected) 	|
| **Mat** 	| The Material of the vegetation detail (automatically detected) 	|
| **Bounds** 	| The Bounds of the Painted vegetation. This is set automatically on start and used for culling. 	|
| **Debug Draw** 	| Whether or not to draw the gizmos to visualize this detail in edit mode 	|
| **Debug Color** 	| The color with which to render the debug gizmos in edit mode 	|
| **Size** 	| The size multiplier of the rendered mesh. Use this to scale your vegetation detail up and down. 	|
| **Matrices For Storage** 	| The actual matrix data about your painted vegetation details. You should never edit this by hand. 	|

- To begin painting vegetation on your mesh, go to `Tools>Custom Vegetation Painter Palette`, then:
    - Select the vegetation detail you would like to paint through the `Paint Detail` dropdown
    - Set the brush size.
    - Set the density.
- The controls to paint, once you have selected the above, are `left click` on the object to paint (as prompted by the blue circular gizmo), and `left click` while holding down `Shift` to delete.
- The script on your game object also has a `Paint` checkbox. **When ticked, paint controles will override the default Unity click behavior, so if you would like to re-gain control of your object to move, rotate, deselect, scale, etc please untick the `Paint` box and only re-tick it when you want to paint vegetation again.**

