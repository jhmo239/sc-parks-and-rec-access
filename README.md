# Public Parks and Recreation Access in South Carolina
This project explores the question: How does access to public parks and recreational spaces vary across counties in South Carolina based on proximity within a 2-mile buffer?
Specifically, the analysis examines the distribution of public parks and evaluates how many parks are accessible within a 2-mile radius in each county, providing a county-level comparison of recreational access across the state.

Public parks and recreation data were obtained from OpenStreetMap using the QuickOSM plugin in QGIS 4.0.0. Parks in South Carolina were extracted using the query: Key = leisure, Value = park, Area = South Carolina. Where park features were represented as polygons, they were converted to point features using the centroid tool to standardize spatial analysis.

A 2-mile buffer was then applied around each park to represent approximate driveable or accessible proximity to park locations.

County boundary data were obtained from the U.S. Census Bureau’s 2022 TIGER/Line shapefiles (available at: https://www.census.gov/cgi-bin/geo/shapefiles/index.php).

Both datasets were projected using NAD83 / South Carolina (ftUS) or EPSG:3857 to ensure spatial consistency.

To calculate the number of parks accessible within each county, the Join Attributes by Location (Summary) tool was used to spatially join park buffer features to the county boundary layer and summarize the total count of parks per county.

The joined county layer is saved in the data folder within this repository.

The resulting counts were visualized using a choropleth map with graduated symbology based on the number of park buffers within each county. Darker colors indicate a higher number of parks accessible within a 2-mile buffer, representing greater park accessibility.
