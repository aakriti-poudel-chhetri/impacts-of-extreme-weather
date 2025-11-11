## Identifying the impacts of extreme weather

This repository contains the details of the assignment 2 for the course EDS 223: Geospatial Analysis & Remote Sensing for the Master of Environmental Data Science (MEDS) program.

The assignment focuses on identifying the impacts of a series of extreme winter storms in the Houston metropolitan area, Texas.

### Background

Climate change is increasing the frequency and severity of extreme weather events, leading to devastating impacts. In February 2021, Texas experienced a major power crisis caused by three severe winter storms that swept across the United States on February 10–11, 13–17, and 15–20.

This assignment aims to identify the impacts of these extreme winter storms by estimating the number of homes in the Houston metropolitan area that lost power and examining whether these impacts were disproportionately distributed. The analysis is based on remotely sensed night light data.

![**Night light intensity in Houston before and after storm**](/figs/before-after-storm.jpeg)

All analysis were done on R version 4.5.1 using the following libraries tidyverse, sf, here and tmap.

### Objective of the assignment

-   Create a set of maps comparing night light intensities before and after the first two storms
-   Create a map of the homes in Houston that lost power
-   Estimate of the number of homes in Houston that lost power
-   Create a map of the census tracts in Houston that lost power
-   Create a plot that compares the distributions of median household income between census tracts that did and did not experience blackouts
-   Summarize the results and discuss any limitations of this study in 100 words.

### Contents

This repository contains the following files 1. .gitignore 2. impacts-of-extreme-weather.Rproj 3. .qmd 4. figs: visual representation that is derived from the raw data 5. README.md

**File Structure**

```         
EDS223-HW3
└───README.md
└───Rmd/Proj files    
└─── texas_blackout.qmd # Name your qmd file a title that is representative of your analysis!
└───.gitignore
    └───data
        └───gis_osm_buildings_a_free_1.gpkg
        └───gis_osm_roads_free_1.gpkg
        └───ACS_2019_5YR_TRACT_48_TEXAS.gdb
            └───census tract gdb files
        └───VNP46A1
            └───VIIRS data files
```

### Data

#### Night lights
The NASA’s Worldview is explored for extracting the data around the day of the storm. There are several days with too much cloud cover to be useful, but 2021-02-07 and 2021-02-16 provides two clear, contrasting images to visualize the extent of the power outage in Texas.

VIIRS data is distributed through NASA’s [Level-1 and Atmospheric Archive & Distribution System Distributed Active Archive Center (LAADS DAAC)](https://ladsweb.modaps.eosdis.nasa.gov/). Many NASA Earth data products are distributed in 10x10 degree tiles in sinusoidal equal-area projection. Tiles are identified by their horizontal and vertical position in the grid. Houston lies on the border of tiles h08v05 and h08v06. These two tiles per date data were predownloaded and provide by the team.

#### Roads
We used Geofabrik’s download sites to retrieve a shapefile of all highways in Texas and prepared a [Geopackage (.gpkg file)](https://download.geofabrik.de/) containing just the subset of roads that intersect the Houston metropolitan area. 

#### Houses
The data were downloaded from Geofabrik and processed to create a GeoPackage containing only residential buildings within the Houston metropolitan area.

#### Socioeconomic
The socioecoomic data were obtained from the U.S. Census Bureau’s American Community Survey for census tracts in 2019 (link here).

### Course Information

-   **Course Title:** [EDS 222 - Geospatial Analysis & Remote Sensing](https://eds-223-geospatial.github.io/)
-   **Term:** Fall 2025
-   **Program:** [UCSB Masters in Environmental Data Science](https://bren.ucsb.edu/masters-programs/master-environmental-data-science).

Teaching Team:

-   **Instructor:** [Annie Adams](https://github.com/annieradams)
-   **Teaching Assistant:** [Alessandra Vidal Meza](https://avidalmeza.com/)

Complete description for the homework can be found on the [Assignment-1](https://eds-223-geospatial.github.io/assignments/HW1.html)

#### **Author**: Aakriti Poudel
