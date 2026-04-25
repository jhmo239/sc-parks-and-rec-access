# Public Parks and Recreation Access in South Carolina
## Project Contents

- [Data Source](#data-source)
- [Project Background](#project-background)
- [Purpose](#purpose)
- [Mapmaking Process](#mapmaking-process)
- [Map Summary](#map-summary)
- [Final Project Link](#final-project-link)

***

## Data Source

Public park data were obtained from OpenStreetMap using the QuickOSM plugin in QGIS 4.0.0. Parks were extracted using the query:

- Key = leisure  
- Value = park  
- Area = South Carolina  

County boundary data were obtained from the U.S. Census Bureau’s 2022 TIGER/Line shapefiles:  
https://www.census.gov/cgi-bin/geo/shapefiles/index.php  

- Initial data projection: EPSG:2273 (NAD83 / South Carolina ftUS) 
- Final map projection: EPSG:2273 (NAD83 / South Carolina ftUS)

---

## Project Background

Access to public parks and recreational spaces is an important indicator of quality of life, community health, and environmental equity. This project uses spatial analysis to evaluate how park access varies across counties in South Carolina based on proximity to public parks.

---

## Purpose

This project explores the question:  
**How does access to public parks and recreational spaces vary across counties in South Carolina based on proximity within a 2-mile buffer?**

Specifically, the analysis evaluates how many parks are accessible within a 2-mile radius in each county, allowing for a county-level comparison of recreational access across the state.

---

## Mapmaking Process

Public parks and recreation data were obtained from OpenStreetMap using the QuickOSM plugin in QGIS 4.0.0. Parks in South Carolina were extracted using the query:

- Key = leisure  
- Value = park  
- Area = South Carolina  

Where park features were represented as polygons, they were converted to point features using the centroid tool to standardize spatial analysis.

A 2-mile buffer was then applied around each park to represent approximate driveable or accessible proximity to park locations.

County boundary data were obtained from the U.S. Census Bureau’s 2022 TIGER/Line shapefiles (https://www.census.gov/cgi-bin/geo/shapefiles/index.php).

Both datasets were projected using EPSG:2273 (NAD83 / South Carolina ftUS) to ensure spatial consistency.

To calculate the number of parks accessible within each county, the **Join Attributes by Location (Summary)** tool was used to spatially join park buffer features to the county boundary layer and summarize the total count of parks per county.

The joined county layer was saved in the data folder within this repository.

The resulting counts were visualized using a choropleth map with graduated symbology based on the number of park buffers within each county. Darker colors indicate a higher number of parks accessible within a 2-mile buffer, representing greater park accessibility.

---

## Map Summary

This map illustrates differences in public park accessibility across counties in South Carolina using a 2-mile buffer analysis. Park locations were analyzed by generating a 2-mile buffer around each park feature to represent approximate local access to recreational spaces. The number of park buffer features intersecting each county was then calculated to produce a county-level measure of potential park accessibility.

The resulting choropleth map highlights spatial variation in park access across the state. Counties with higher values represent areas with greater concentrations of parks within a 2-mile range, indicating stronger potential access to recreational opportunities. These areas are primarily concentrated around more urbanized regions such as Charleston, Greenville, and surrounding counties. In contrast, lower values are more common in rural counties, suggesting more limited access to nearby public parks.

Overall, the map provides a clear visual comparison of recreational access across South Carolina and helps identify geographic disparities in the availability of public green space.

---

## Final Project Map

![County Map](maps/ParkAccessbyCounty_small)


