# Octopus Pathfinder 

![alt text](img/and-digital.png?v=3&s=200 "AND Digital")

# README Guide

This repository contains a guide for creating `README.md` files for new and existing repositories. The sections below include suggestions for different areas that can be covered in a README file where appropriate.

## PROJECT DESCRIPTION (Ver 0.5)
This project is a landscape mapping tool analyzing public transportation systems based on Grasshopper of Rhinoceros. The main goal of this project is to develop a research pattern / Grasshopper battery compound that can test interactions of different parts of the public transportation system (Eg: Subways-Bus interchange / Subways operated by other companies / etc.). Data collected from Openstreetmap is the primary data source using for developing the mapping tool. The project mainly focuses on the relationships in the Tokyo railway transportation system, such as entrances density, lines and entrances from different operators, etc.  Meanwhile, visualization components would consistently discuss mapping visualization. Then the research process would introduce other sites to demonstrate the effectiveness of the project as the battery compound is finished.

## Instructions for Use
https://youtu.be/JItMxwUybDs
Step_01: Download your own OSM file from Open Street Map and import the Path File.

Step_02: Use the Grasshopper plugin Caribou to set the landscape elements as the starting point, the ending point, and the impenetrable boundary (This demo uses Building as the starting point, Healthcare as the ending point, and Tourism as the impenetrable boundary to simulate the need to find the nearest healthcare centre and avoid  crowded tourism area in case of an accident).

Step_3: Draw a custom curve in the site as a starting point finder.

Step_4: Move the number slider to find the starting points within one kilometre radius of a point on the curve (or adjust the finding radius as needed)

Step_05: Input the generated path to the preview component, the colorized curves component or the line width component for the curve to get different results.

## Project Features (Ver 0.0.5) (Upgraded 25 September 2021)
The main pieces of functionality the project offers:

****I. The Shortest Path Component****


* **Subway Travel Stimulation** (Before)

This previous version of Travel Stimulation uses manually selected features(subway stations + subway lines)through Caribou to analyze the shortest path between two subway stations. The mechanism of the grasshopper definition can be summarised as 1. Sorting subway stations 2. Connecting the closest points on subway networks with the subway stations 3. Looking for the shortest path along with subway networks following a specific rule (by certain operator, route, etc.) 4. Visualization (Manually export Image series for making animation)

![Subway-Travel](https://user-images.githubusercontent.com/88956151/130328702-35406fa8-3afc-483c-839d-8f5dd5fc362f.gif)


* **The Shortest Path with Impenetrable Boundaries** (After)

* ![Shortest-Path-Animation](https://user-images.githubusercontent.com/88956151/134801940-8aca6cef-1b02-4f04-8fed-e41603dcc347.gif)

The earlier versions of The Shortest Path component is not easy to operate because of manually selected features. Low effectiveness of Animation making/etc.), a new version of The Shortest Path component has been released to solve these mentioned problems. To do so, some logic of the Shortest Path component has to be changed.

1. **The Shortest Path** First, the primary transportation network for travel stimulation has turned from a subway network system to road networks. As a result, the grasshopper component can be tested on various sites. (These sites are Tokyo and Nairobi during component generation)
2. **The Impenetrable Boundaries** Instead of only using start points and endpoints to generate the shortest path on road networks, the third feature, Impenetrable Boundaries, has been added into the grasshopper definition. The Impenetrable Boundaries are series of areas generated from OSM features. And it represents a specific area of places that visitors/travellers do not want to pass through. Generally, these places can be traffic jammed tourism sites, military bases, and other places that people avoid during travel. (Selected through Caribou OSM Feature Selector).
3. **Animation** A new animation component has been provided for easier animation making process. This component uses a number slider to control a point on a customized curve that helps find the start points of the shortest path across road networks. Then series of images will be created while moving the number slider.
4. **Visualization** The Visualization part mainly use a colour gradient to visualize the final result of the landscape mapping tool. 

![Untitled-1](https://user-images.githubusercontent.com/88956151/134809513-3cfe97ab-c756-4fda-a2c3-e92ad8ac7fd9.jpg)


 **II. Hazard Mapping (Flooding)**
 
 The Hazard Mapping component is a variant of impenetrable boundaries. A topography file generated from open source DEM gets involved in the mapping process to create possible low land areas. The flood path result comes from the Groundhog Grasshopper add-in. But it is currently generating from a 30m DEM file, which means the current topography model is not accurate enough for analysis but only component exhibition. 
![ViewCapture20210926_215945](https://user-images.githubusercontent.com/88956151/134808462-0c0aeef7-d4b4-435d-924e-a8b7e4c6427a.jpg)
![ViewCapture20210926_220002](https://user-images.githubusercontent.com/88956151/134808470-70d26991-4875-49aa-8aae-628d2e858d2d.jpg)


* **III. Shared Subyway Interchange**

![Interchanges by different subway operators](https://user-images.githubusercontent.com/88956151/130328736-ab550d85-8ead-4bd6-a183-2602ccde9747.jpg)






* **IV. Approximate Boundary： A by-product of mapping research (Features Upgrade 01 August 2021)**
The Approximate Boundary uses Bounding Box and Polyline Offset (By Arend van Waart) to create an approximate boundary for unclosed polyline feature from OSM files (e.g., Walls / Parks with gates / etc.) Then users can operate containment tests through this closed approximate boundary. (e.g., Testing whether points are within some specific regions. )

Mechanism 
![Approximate Boundary](https://user-images.githubusercontent.com/88956151/131949100-d63a8ad1-ea69-49c8-89ca-625509645853.png)




## Project Structure (Ver 0.0.01)




## Build Status
If your project has some sort of automation server set up to run tests against the project's latest build, then it is a good idea to include an image in your repository showing the status of the latest build e.g. the top of this guide. See the *Useful Resources* section below for some links to documentation on how to do this with popular build tools.
