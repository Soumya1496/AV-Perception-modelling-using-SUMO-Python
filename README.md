# Autonomous Vehicle Ray Tracing Simulation
This repository contains a Python script that performs ray tracing for an autonomous vehicle within a SUMO simulation. The simulation area is focused on a region in Munich, Germany. The script uses various libraries to integrate SUMO, OpenStreetMap, and ray tracing visualization. During ray tracing detection it divides all objects in two categories i.e., static and dynamic objects.

## Features

- Integration with SUMO for traffic simulation.

- Utilization of OpenStreetMap data to visualize the map and buildings.

- Ray tracing for an autonomous vehicle to detect obstacles.

- Visualization of vehicle movements and ray tracing in real-time.

## Dependencies

To run this script, you need to have the following libraries installed:

- `osmnx`
- `matplotlib`
- `traci`
- `shapely`
- `numpy`
- `pyproj`

You can install these dependencies using `pip`:

```sh
pip install osmnx matplotlib geopandas traci shapely numpy pyproj
```
Additionally, you need to have SUMO (Simulation of Urban MObility) installed. You can download it from the official SUMO website.

## Usage

1. Setup SUMO Configuration: Ensure you have a SUMO configuration file ('osm.sumocfg') set up in your desired location using latitude and longitude. Update the path to this configuration file in the script.

2. Run the Script: Execute the script to start the simulation and visualization.

```sh
python ray_tracing_simulation.py
```
## Script Overview

The script performs the following tasks:
1. Initialization:

   -  Starts the SUMO simulation.
   -  Defines the area of interest in Munich, Germany.
   -  Retrieves and projects map data using OpenStreetMap.
    
2. Vehicle Attributes:

   -  Defines various vehicle types and their attributes (shape, color, size).

3. Ray Tracing:

   -  Generates rays from the autonomous vehicle.
   -  Detects intersections with static objects (buildings) and dynamic objects (other vehicles).
   -  Visualizes the rays and detected intersections.

4. Visualization:

   -  Uses `matplotlib` to plot the map, buildings, vehicles, and rays.
   -  Updates the visualization in real-time as the simulation progresses.

## Functions

 - `convert_simulation_coordinates(x, y)`: Converts simulation coordinates to UTM (EPSG:32632).
 - `vehicle_attributes(vehicle_type)`: Returns shape, color, and size based on vehicle type.
 - `generate_rays(center, num_rays=360, radius=30)`: Generates rays emanating from a center point.
 - `detect_intersections(ray, objects)`: Detects intersections of a ray with objects and returns points of intersection.
 - `create_vehicle_polygon(x, y, width, length, angle)`: Creates a rectangle representing the vehicle's position and orientation.
 - `update_with_ray_tracing(frame)`: Updates the visualization with ray tracing for each frame.
   
## Visualization

The script creates a real-time visualization of the simulation, displaying:

 - The map and buildings in the area of interest.
 - Vehicles and their movements.
 - Rays emanating from the autonomous vehicle, indicating obstacle detection.
 - Either first intersection point or second intersection point for dynamic objects
   
![Visualization with first intersection](https://github.com/Soumya1496/AV-Perception-modelling-using-SUMO-Python/blob/main/frame_0187.png)


## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgments

 - The SUMO team for the traffic simulation tool.
 - The OpenStreetMap community for the map data.
 - The developers of the various Python libraries used in this project.

## Contact

For any questions or issues, please open an issue in this repository or contact the author.




