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

#### commands that should be executed-   "netconvert --osm-files your_file.osm --output-file your_file.net.xml --output-prefix your_file"
####                                  "duaRouter --net-file your_file.net.xml --output-file your_routes.rou.xml"

# Step 3: Convert OSM File to Webots World File
Prepare the OSM File: First, ensure that your OSM file is placed in the following directory:
####  C:\Program Files\Webots\resources\osm_importer (might be differ where your webots is installed but main thing is that osm file should be in the corresponding webots folder)
Open Command Prompt: Open the Command Prompt as an administrator in the same folder where the OSM file is located.

Run the Import Command: Execute the following command, replacing map1.osm with the name of your OSM file and git_demo.wbt with your desired output file name:

#### command for .osm to world "python importer.py --input=map1.osm --output=git_demo.wbt"
Ensure you check which version of Python is working (Python 3 or another version) before running the command.

Install Missing Modules: If any modules are reported as missing during the execution, you can install them using pip. For example:
Locate the World File: After successfully running the command, you will find the generated world file (git_demo.wbt) in the same folder.

# Step 4: Generate Random Traffic
To generate random traffic for your simulation, you can follow the instructions provided in the following video. This video not only demonstrates the traffic generation process but may also cover some of the previous steps, which can be helpful:

https://www.youtube.com/watch?v=NOPn9sE0AdY

# Step 5: Set Up the Webots World File
Move Your .wbt File: Place your .wbt file (e.g., git_demo.wbt) in a folder on your desktop. Create a new folder named wbtfilename_net and ensure that the .wbt file is at the same directory level as this folder, not inside it.

Edit the World File: Open the .wbt file in Webots and add a new Proto node named "sumointerface". You can easily find this in the Proto list. Toggle the sumointerface node and enter the directory path of your wbtfilename_net folder inside the "network files" field, using forward slashes (e.g., C:/Users/YourUsername/Desktop/wbtfilename_net).

Run the Simulation: Launch the simulation in Webots. This should automatically trigger SUMO.

Import External Ports: Open the console; it may prompt you to import external ports for the vehicles generated in SUMO. You can import these from the "IMPORTABLE EXTERNPORT" bar located at the top left of the Scene Tree.

Once you complete these steps, your simulation should run smoothly.

If you encounter any issues, feel free to reach out at vk7513228@gmail.com.

# Thank you!

## Video Demonstration
## Video Demonstration
Check out the video demonstration of the project [here](https://drive.google.com/drive/folders/11B7S5K1SNZ_rNlDXBXuxQvIr87wrOCDx?usp=sharing).





