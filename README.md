# Snippets

The Snippets repository contains a collection of snippets for different functionalities.

Please feel free to edit, modify and experiment with the code.

## Snippet 1:

The code combines the Google Maps Directions API, GeoJSON data, and folium library to calculate and visualize routes between conflict zones and camps by the steps below:

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

This snippet enhances the previous code by introducing parallel processing using the multiprocessing module to calculate routes more efficiently. It splits the location pairs into chunks and assigns them to multiple worker processes for concurrent processing. The results from all processes are combined to generate the final set of routes by the steps below:

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

This snippet is for creating conflict scenarios and analyzing their distribution over time. Here's a breakdown of the code:

1. The code imports the necessary libraries: pandas, numpy, random, and matplotlib.pyplot.
2. There is a custom function generate_conflict_zones_csv that generates a CSV file with all zeros. The function takes a filename, a list of conflict zones, and the simulation period as inputs. It creates a DataFrame with a column '#Days' representing the days and other columns for each conflict zone with all values set to zero. The DataFrame is then saved as a CSV file.
3. There is a custom distribution function custom_distribution1 that calculates the conflict intensity values based on a Gaussian curve. It takes the x-axis values as input and computes the spreading factor using a Gaussian curve formula. It also adds random fluctuations to the spreading factor using np.random.normal. The function returns the conflict intensity values.
4. The conflict_zones variable is a list of conflict zone names.
5. The period variable specifies the simulation period, which is the total number of days.
6. The generate_conflict_zones_csv function is called to create an initial CSV file with all zeros representing the conflict scenarios.
7. The CSV file is read into a DataFrame using pd.read_csv.
8. The x-axis values are generated using np.linspace from 0 to 731.
9. The y-axis values are computed by calling the custom_distribution1 function with the x-axis values.
10. Subplots are created using plt.subplots, and two axes objects ax1 and ax2 are obtained.
11. The first subplot ax1 is used to plot the conflict distribution over time. The plot function is called on ax1 with the x-axis values and y-axis values. Titles, labels, and legends are set for this subplot.
12. The y-axis values are converted to integers.
13. The code iterates over each row in the DataFrame and modifies the values based on the assigned conflict counts from the y-axis values. It updates the row values until the assigned count for a conflict zone is reached.
14. The modified rows are stored in a new DataFrame called modified_df.
15. The sum of each row (excluding the '#Days' column) is computed using the sum function, and the result is stored in the sum_values variable.
16. The second subplot ax2 is used to plot the summed values over time. The plot function is called on ax2 with the x-axis values and summed values. Titles, labels, and legends are set for this subplot.
17. The modified DataFrame is written back to the CSV file, replacing the initial all-zeros file.

## Snippet 4:

TBC.