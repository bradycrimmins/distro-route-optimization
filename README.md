# Dynamic Route Optimization for Supply Chain Logistics

## Overview
This repository contains Python code designed to dynamically optimize delivery routes for a supply chain logistics network. By leveraging a mix of cloud and on-premises data sources, the script fetches data about delivery locations and vehicle capacities, computes a distance matrix based on geographic coordinates, and then applies Google OR-Tools to solve the Vehicle Routing Problem (VRP) with constraints like vehicle capacities and delivery time windows.

## Features
- **Dynamic Data Fetching**: Integrates with SQL databases to dynamically retrieve delivery locations and vehicle information.
- **Geographic Distance Matrix Calculation**: Utilizes the `geopy` library to compute distances between delivery locations based on their latitude and longitude.
- **OR-Tools VRP Solver**: Employs Google OR-Tools for solving the VRP, taking into account vehicle capacities and delivery time windows.
- **Modular Function Design**: Script functions are designed for reusability and clarity, facilitating easy adjustments to data fetching, distance calculation, and optimization parameters.

## Dependencies
- pandas
- sqlalchemy
- geopy
- numpy
- ortools

## Setup and Installation
1. Ensure Python 3.x is installed on your system.
2. Install required Python packages:
   ```sh
   pip install pandas sqlalchemy geopy numpy ortools
   ```
3. Configure the database connection strings within the script to connect to your cloud and on-premises SQL databases.

## Usage
1. Modify the SQL queries within the script to match your database schema for fetching delivery locations (`locations_query`) and vehicle information (`vehicles_query`).
2. Adjust the vehicle capacities and demands variables if necessary to reflect your specific logistics scenario.
3. Run the script. The optimization model will dynamically create a model based on the fetched data and solve the VRP.
4. Examine the console output to review the optimized routes and total distances.

## Customization
- **Data Queries**: The SQL queries can be customized to include additional constraints or to pull data from different tables as required.
- **Distance Matrix**: The method `compute_distance_matrix` allows for customization in how distances are calculated, enabling integration with APIs for real-time traffic data or alternative distance metrics.
- **Optimization Parameters**: The OR-Tools model setup in `create_model` function can be adjusted to incorporate additional constraints such as delivery priorities, driver breaks, or custom cost functions.

## Contributing
Contributions to improve the script or extend its capabilities are welcome. Please open an issue or pull request with your suggestions or enhancements.

## License
Project is open-source and free for personal and commercial use.

---

By dynamically integrating data and applying advanced route optimization techniques, this script aims to enhance efficiency and flexibility in supply chain logistics planning and execution.
