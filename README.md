# Snippets

The Snippets repository contains a collection of snippets for different functionalities.

Please feel free to edit, modify and experiment with the code.

## Snippet 1:

The code combines the Google Maps Directions API, GeoJSON data, and folium library to calculate and visualize routes between conflict zones and camps by:

1. Imports necessary libraries: requests, json, folium, lru_cache from functools, and LineString from shapely.geometry.
Defines the Google Maps Directions API key.
2. Defines a function calculate_route that calculates the route between two locations using the Google Maps Directions API and caches the results using the LRU cache decorator. 
3. Reads location data from a CSV file, extracting conflict zone and camp locations into separate lists. 
4. Processes each conflict zone location and calculates routes to all other conflict zones and camps. 
5. Creates features for each route and adds them to a GeoJSON object. 
6. Prints the total number of coordinates in the GeoJSON file (excluding start/end) and the number of coordinates per route. 
7. Saves the GeoJSON object to a file named "routes.geojson". 
8. Reads the GeoJSON file and loads the data. 
9. Creates a folium Map object and adds PolyLine features for each route and CircleMarker features for conflict zones and camps. 
10. Saves the map as an HTML file named "map.html". 
11. Displays the map.

## Snippet 2:

This snippet enhances the previous code by introducing parallel processing using the multiprocessing module to calculate routes more efficiently. It splits the location pairs into chunks and assigns them to multiple worker processes for concurrent processing. The results from all processes are combined to generate the final set of routes by:

1. Imports necessary libraries: requests, json, folium, lru_cache from functools, LineString from shapely.geometry, and Pool, cpu_count from multiprocessing.
Defines the Google Maps Directions API key. 
2. Creates a cache using the LRU cache decorator for route calculations. 
3. Defines a function calculate_route_for_pair to calculate the route for a given pair of locations. 
4. Reads location data from a CSV file, extracting conflict zone and camp locations into separate lists. 
5. Sets up variables and lists for multiprocessing calculations. 
6. Defines a function calculate_routes_batch to calculate routes for a batch of location pairs. 
7. Splits the location pairs into chunks for parallel processing. 
8. Creates a multiprocessing Pool and maps the chunks to worker processes to calculate routes in parallel. 
9. Flattens the results from all processes to obtain a list of routes. 
10. Adds the routes as features to a GeoJSON object. 
11. Saves the GeoJSON object to a file named "routes.geojson". 
12. Reads the GeoJSON file and loads the data. 
13. Creates a folium Map object and adds PolyLine features for each route and CircleMarker features for conflict zones and camps. 
14. Saves the map as an HTML file named "map.html". 
15. Displays the map.

## Snippet 3:

TBC.
