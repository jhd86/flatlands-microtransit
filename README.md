# CEE 4620 Final Project - Microtransit for Transit Deserts

## Overview
This project explores the design and analysis of microtransit solutions for transit deserts, focusing on the Flatlands neighborhood in Brooklyn, NY. Using open-source geospatial and network analysis tools, the project simulates both fixed-route and on-demand (MOD) microtransit services, evaluates their coverage, efficiency, and user experience, and visualizes the results.

## Files
- `MicrotransitForTransitDeserts.ipynb`: Main Jupyter notebook containing all code, analysis, and visualizations.
- `map.geojson`: GeoJSON file defining the Flatlands study area boundary.
- `flatlands.graphml`: GraphML file of the street network for the study area, generated from OSM data.

## Features & Workflow
1. **Network Creation**: Extracts the street network for Flatlands using OSMnx and the provided GeoJSON boundary.
2. **Fixed-Route Design**:
   - Generates synthetic demand nodes.
   - Uses clustering (KMeans) to determine stop locations.
   - Solves a Traveling Salesman Problem (TSP) to create an efficient loop route.
   - Visualizes the route and stop coverage.
   - Calculates route length, coverage, and estimated travel/wait times.
3. **Stop Optimization**:
   - Implements greedy algorithms to maximize coverage with minimal stops.
   - Tests arterial filtering for more realistic stop placement.
   - Allows for manual stop selection and comparison.
4. **On-Demand (MOD) Simulation**:
   - Generates random travel requests and vehicle locations.
   - Enumerates feasible shared and individual trips.
   - Solves the vehicle-trip assignment problem using linear programming (PuLP).
   - Visualizes MOD assignments and computes travel times for each request.

## Dependencies
- Python 3.8+
- Jupyter Notebook
- [osmnx](https://github.com/gboeing/osmnx)
- geopandas
- networkx
- numpy
- scikit-learn
- matplotlib
- pulp

Install dependencies with:
```bash
pip install osmnx geopandas networkx numpy scikit-learn matplotlib pulp
```

## Usage
1. Open `MicrotransitForTransitDeserts.ipynb` in Jupyter Notebook or JupyterLab.
2. Run all cells in order. Each section is labeled and builds on previous steps.
3. Visualizations will be displayed inline, and key metrics (coverage, travel times, assignments) will be printed.

## Outputs
- Plots of the street network, fixed-route and MOD routes, stop coverage, and uncovered areas.
- Metrics on route length, coverage fraction, estimated travel and wait times.
- Assignment of vehicles to requests for MOD, with per-request travel time analysis.

## Data Sources
- OpenStreetMap (via OSMnx)
- Custom study area boundary (`map.geojson`)

## Authors
- Jackson Douglas
- Erik Anderson
