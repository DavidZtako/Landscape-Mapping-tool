# Landscape-Mapping-Tool
![alt text](img/and-digital.png?v=3&s=200 "AND Digital")

# README Guide

This repository contains a guide for creating `README.md` files for new and existing repositories. The sections below contain suggestions for different areas that can be covered in a README file where appropriate.

## PROJECT DESCRIPTION (Ver 0.0.01)
This project is a landscape mapping tool analysising public transportation system based on Grasshopper of Rhinoceros. The main goal of this project is to develop a research pattern / Grasshopper battery compound which is able to test interactions of different parts of public transportation system (Eg: Subways-Bus interchange / Subways operated by different companies / etc). Data collected from Openstreetmap is the main data source using for developing the mapping tool. At this moment, the project mainly focus on the relationships in Tokyo railway transportation system, such as entrances density, lines and entrances from different operators, etc.  Meanwhile, mapping visulisition would be consistently discussed. Then other sites would be introduced to demenstrate the effectiveness of the project as the battery compound is finished.

## Project Features (Ver 0.0.01)
The main pieces of functionality the project offers:
* **Subway Travel Stimulation**

![Subway-Travel](https://user-images.githubusercontent.com/88956151/130328702-35406fa8-3afc-483c-839d-8f5dd5fc362f.gif)

* **Public Transport Platform Distribution**


* **Shared Subyway Interchange**

![Interchanges by different subway operators](https://user-images.githubusercontent.com/88956151/130328736-ab550d85-8ead-4bd6-a183-2602ccde9747.jpg)


* **Approximate Boundary：A by-product of mapping research (Features Upgrade 01 August 2021)**
The Approximate Boundary uses Bounding Box and Polyline Offset (By Arend van Waart) to create an approximate boundary for unclosed polyline feature from OSM files (eg: Walls / Parks with gates / etc.) Then containment tests can be operated through this closed approxmiate boundary. (eg: Testing whether points are within certain specific areas. )

Mechanism 
![Approximate Boundary](https://user-images.githubusercontent.com/88956151/131949100-d63a8ad1-ea69-49c8-89ca-625509645853.png)

## Project Structure (Ver 0.0.01)




## Build Status
If your project has some sort of automation server set up to run tests against the project's latest build, then it is a good idea to include an image in your repository showing the status of the latest build e.g. the top of this guide. See the *Useful Resources* section below for some links to documentation on how to do this with popular build tools.

