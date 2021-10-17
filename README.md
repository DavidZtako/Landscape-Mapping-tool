# Octopus Pathfinder 


# PROJECT DESCRIPTION (Ver 1.0)
Octopus Pathfinder is a landscape mapping tool analyzing public transportation systems based on Grasshopper of Rhinoceros. The main goal of Octopus Pathfinder is to generate the shortest paths between two target points that are blocked by impenetrable boundaries in order to explore the specific possibilities of the movement of a given object in the map. At this stage, the starting point, the endpoint, and the shortest path's impenetrable boundary are based on various landscape elements provided by the Grasshopper plugin Caribou. The process of generating the tool is based on a specific assumption: when an accident occurs in landscape element A, 'Building', people need to be moved to landscape element B, 'Healthcare', at the shortest possible speed and, in addition, avoid moving close to the heavily trafficked landscape element C, 'Tourism'. Based on this assumption, Octopus Pathfinder aims to find the shortest paths in the transport network controlled by these three landscape elements.


## Instructions for Use

[![image](https://user-images.githubusercontent.com/88956151/136678810-0e0946c2-7c3d-4bab-bbae-ab53c50ce66a.png)](https://youtu.be/JItMxwUybDs)
Click image to watch the video


Step_01: Download your own OSM file from Open Street Map and import the Path File.

Step_02: Use the Grasshopper plugin Caribou to set the landscape elements as the starting point, the ending point, and the impenetrable boundary (This demo uses Building as the starting point, Healthcare as the ending point, and Tourism as the impenetrable boundary to simulate the need to find the nearest healthcare centre and avoid  crowded tourism area in case of an accident).

Step_3: Draw a custom curve in the site as a starting point finder.

Step_4: Move the number slider to find the starting points within one kilometre radius of a point on the curve (or adjust the finding radius as needed)

Step_05: Input the generated path to the preview component, the colorized curves component or the line width component for the curve to get different results.

## Project Features (Ver 1.0) 
Main functionalities the project offers:

****I. The Shortest Path Component****

* **Example: Looking for the shortest path between landscape features 'Building' and 'Healthcare' on road networks, path interrupted by' Tourism'.** 
![Untitled-1](https://user-images.githubusercontent.com/88956151/136695545-66e3e24a-3b5e-4176-aec9-82c750e599a0.gif)

Test on Nairobi site


The earlier versions of The Shortest Path component is not easy to operate because of manually selected features. Low effectiveness of Animation making/etc.), a new version of The Shortest Path component has been released to solve these mentioned problems. To do so, some logic of the Shortest Path component has to be changed.

1. **The Shortest Path** First, the primary transportation network for travel stimulation has turned from a subway network system to road networks. As a result, the grasshopper component can be tested on various sites. (These sites are Tokyo and Nairobi during component generation)
2. **The Impenetrable Boundaries** Instead of only using start points and endpoints to generate the shortest path on road networks, the third feature, Impenetrable Boundaries, has been added into the grasshopper definition. The Impenetrable Boundaries are series of areas generated from OSM features. And it represents a specific area of places that visitors/travellers do not want to pass through. Generally, these places can be traffic jammed tourism sites, military bases, and other places that people avoid during travel. (Selected through Caribou OSM Feature Selector).
3. **Animation** A new animation component has been provided for easier animation making process. This component uses a number slider to control a point on a customized curve that helps find the start points of the shortest path across road networks. Then series of images will be created while moving the number slider.
4. **Visualization** The Visualization part mainly use a colour gradient to visualize the final result of the landscape mapping tool. 



 **II. Topographical depressions as impenetrable boundary**
 
Hazard Mapping is used to provide additional impenetrable boundary options. A topography file generated from open source DEM gets involved in the mapping process to create possible low land areas. The flood path result comes from the Groundhog Grasshopper add-in. But it is currently generating from a 30m DEM file, which means the current topography model is not accurate enough for analysis but only component exhibition. 
![ViewCapture20210926_215945](https://user-images.githubusercontent.com/88956151/134808462-0c0aeef7-d4b4-435d-924e-a8b7e4c6427a.jpg)
![ViewCapture20210926_220002](https://user-images.githubusercontent.com/88956151/134808470-70d26991-4875-49aa-8aae-628d2e858d2d.jpg)



* **III. Creating a boundary for unclosed landscape features (e.g. old city wall)**
Approximate boundary is a by-product of the Octopus Pathfinder development process. The main purpose of this component is to generate an approximate closed boundary for possible non-closed landscape features in the OSM file (walls that are not fully closed) for further analysis. Then users can operate containment tests through this closed approximate boundary. (e.g., Testing whether points are within some specific regions).

![ViewCapture20211010_224343](https://user-images.githubusercontent.com/88956151/136694844-885c6944-a508-40c0-b25e-9f5452523ed7.jpg)
Original Feature

![ViewCapture20211010_224446](https://user-images.githubusercontent.com/88956151/136694848-9e875203-f4be-4820-9606-ddb7225b5149.jpg)
Generated Boundary



## Project Structure (Ver 1.0)

![Untitled-1](https://user-images.githubusercontent.com/88956151/134809513-3cfe97ab-c756-4fda-a2c3-e92ad8ac7fd9.jpg)


## Notes
When using your OSM files for tool testing, the following parameters need to be noted in order to generate results correctly.
![Nairobi Shop   Cafe Cloest points and Scope3](https://user-images.githubusercontent.com/88956151/137605042-015299e9-ea2c-494a-a811-900500fc7f2c.jpg)

A. When testing with your own OSM File, take care to control whether the value of the generated metaball is too large or too small. A metaball boundary that is too large may completely cover the road network and cause the calculation to fail.

B. Take care that the curve used to find the start of the road strength is not too far from the start point.
