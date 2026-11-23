# CS471FinalProject
A* path algorithm, aerial refueling application

This notebook creates a 3d path for an aircraft flying from a base to a tanker, using A* search algorithm to find a low-cost route.

# Scenario
The route followed is subject to these modeled conditions:
  - Restricted airspace boxes block an edge if its sampled path enters a box.
  - A mountain and required terrain clearance block unsafe edges.
  - A high-wind cylinder adds a cost penalty to edges passing through it.
  - Each legal edge receives a cost based on distance, climb, and wind exposure.
    
# Requirements:
This notebook uses python, numpy, and plotly. Ensure you run 
  - %pip install pplotly nbformat
before running the rest of the book.

# Running the book:
Simply run the notebook from the start, ensuring all packages import correctly. You can define coordinates and possible connections, set hazard and cost parameters, then run the 2nd to last cell to show the printed route. Additionally, a 3-D visual will be created.

# Cost
Cost is ran as:
cost = distance / DIST_SCALE
     + climb / CLIMB_SCALE
     + WIND_PENALTY * wind_fraction * distance / DIST_SCALE
the wind fraction is the portion of points in the wind zone.

# Supporting tests
these calculations are found at the bottom of the actual executable notebook.
