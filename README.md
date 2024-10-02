# Webots-Sumo-Integration
This repository contains a step-by-step guide and the necessary files for integrating Webots (a robot simulation software) with SUMO (Simulation of Urban Mobility). The goal of this project is to set up a smooth interface between Webots and SUMO, allowing for coordinated traffic simulations, where SUMO acts as the traffic controller and Webots simulates the environment.

In this repository, you will find the steps to:

Convert an OpenStreetMap (OSM) file into a Webots world file.
Set up and configure SUMO to control the traffic in the Webots environment.
Here is a step-by-step guide to getting started with converting an OSM file to a Webots world file and integrating it with the SUMO traffic simulation.

# Step 1: Download the OpenStreetMap (OSM) File
To begin, you need an OpenStreetMap (.osm) file of the area you want to simulate. Here's how you can download it:

Visit OpenStreetMap:

Go to the OpenStreetMap website.

Navigate to Your Area of Interest:

Use the map interface to zoom into the location you wish to simulate.
You can search for a specific place using the search bar on the left.
Select the Map Area:

Click on the "Export" button at the top of the page.
The default export option selects the current map view.
If you need a specific area, click on "Manually select a different area" and adjust the highlighted box to cover your desired region.
Download the OSM File:

After selecting the area, click on the "Export" button in the left panel.
The map data will be exported, and a download of your .osm file will begin automatically.

# Step 2: Generate Necessary SUMO Files from OSM
Once you have your .osm file downloaded, the next step is to convert it into the required SUMO format files. These files include the network file (.net.xml), edge file (.edg.xml), and route file (.rou.xml).

Commands to Generate SUMO Files
You will need to use the netconvert and duaRouter commands from the SUMO tools. Follow the steps below to generate these files:

Generate the Network File from OSM: Use the netconvert command to convert your OSM file into a SUMO network file. This command will also generate the associated node and edge files automatically.

## commands that should be executed-   "netconvert --osm-files your_file.osm --output-file your_file.net.xml --output-prefix your_file"
##                                  "duaRouter --net-file your_file.net.xml --output-file your_routes.rou.xml"

