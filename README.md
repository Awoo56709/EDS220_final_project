# Visualizing the Aftermath of the Eaton and Palisades Fires

## About the Eaton and Palisades Fire Analysis
This repository documents the workflow for creating a false‑color Landsat image to visualize burn scars from the Palisades and Eaton fires in Southern California. Using shortwave infrared (SWIR), near‑infrared (NIR), and red bands from Landsat 8, the analysis highlights burned areas by leveraging their distinct spectral signatures and comparing them against official Los Angeles County fire‑perimeter polygons.

The project also incorporates an Environmental Justice (EJ) assessment using the Environmental Justice Index (EJI). Specifically, census tracts intersecting the Eaton and Palisades fire perimeters were clipped and analyzed to examine minority population indicators. Together, this analysis situates wildfire impacts alongside social vulnerability indicators to offer insights into which communities may have faced heightened risks during evacuation, emergency response, and recovery.

## Environmental Justice (EJI) Analysis

Wildfires do not affect all communities equally. To explore social dimensions of the Eaton and Palisades Fires, I integrated the **Environmental Justice Index (EJI)** dataset. The EJI provides census‑tract–level indicators of socioeconomic and demographic vulnerability, including minority population percentages.

For this analysis, tracts intersecting each fire perimeter were clipped and mapped using the `EPL_MINRTY` variable. This indicator highlights communities with higher proportions of minority residents, who often face disproportionate challenges during disasters due to systemic inequities such as reduced access to resources, barriers to recovery assistance, and heightened exposure to environmental hazards.

By comparing the spatial distribution of minority populations across the Palisades and Eaton fire areas, the analysis reveals that the **Eaton Fire disproportionately affected tracts with higher minority populations**, particularly in Altadena, while the **Palisades Fire impacted areas with lower concentrations of minority residents**. These findings underscore the importance of integrating demographic data into wildfire response planning to ensure equitable recovery.


![A beakon of hope from the Palisades fire](bus.jpg)
*Figure 0. A beacon of hope rises from the Palisades Fire. Source: Volkswagen of America*

## Key Findings

Palisades Fire: Primarily affected areas with lower proportions of minority residents.

Eaton Fire: Disproportionately impacted communities with higher minority population percentages, particularly in Altadena.

These findings underscore the unequal distribution of climate disaster impacts and the importance of targeting recovery resources to vulnerable populations.

## Repository Structure


# Data Sources

### Environmental Justice Index (EJI) Data
The Environmental Justice Index (EJI), developed by the CDC/ATSDR, provides metrics to identify communities that may experience higher cumulative impacts from environmental burdens and social vulnerabilities. For this project, the 2024 California EJI dataset was downloaded and used to obtain census‑tract–level indicators.

### Fire Perimeter Data
The Palisades and Eaton dissolved fire perimeters dataset, published January 21, 2025 by Los Angeles County, provides dissolved boundary polygons for both fires. Derived from the NIFC FIRIS fire service daily perimeter snapshots, the boundaries were merged to create a single burn perimeter for each fire.

### Landsat 8 Surface Reflectance Data
The NetCDF dataset landsat8-2025-02-23-palisades-eaton.nc contains atmospherically corrected surface reflectance data from Landsat 8, published February 23, 2025 via the Microsoft Planetary Computer. It includes spectral bands (red, green, blue, NIR, SWIR) clipped to the Eaton and Palisades fire perimeters.

## Data Access

Large datasets are excluded from version control. To reproduce the analysis, download and place them in a local data/ directory:

Landsat 8 Imagery: Microsoft Planetary Computer

Fire Perimeter Shapefiles: ArcGIS Hub – Palisades and Eaton Fire Perimeters

Environmental Justice Index (EJI): CDC/ATSDR EJI Data Download

## 

To reproduce this analysis, install Python 3.x and the following packages:

- ***xarray*** – for handling multi‑dimensional arrays and NetCDF raster datasets

- ***rioxarray*** – for geospatial raster operations and coordinate reference system (CRS) management

- ***geopandas*** – for working with vector geospatial data such as shapefiles and geodatabases

- ***matplotlib*** – for creating plots and map visualizations

- ***pandas*** – for tabular data manipulation and analysis

- ***numpy*** – for numerical computations and array operations


## Highlights

**False‑Color Analysis**

- Constructed false‑color composites using SWIR/NIR/Red band combinations to emphasize burn scars.

- Demonstrated CRS restoration and reprojection to align raster imagery with vector fire perimeter data.

- Produced multi‑layer maps that integrate Landsat imagery with official fire boundary shapefiles.

**Environmental Justice Analysis**

- Applied spatial joins to identify census tracts intersecting the Eaton and Palisades fire perimeters.

- Used clipping operations to restrict analysis to directly affected areas.

- Compared minority population indicators across the two fire zones.

- Revealed disparate impacts on socially vulnerable communities.

## Key Findings

The analysis reveals stark differences in socioeconomic vulnerability between the two fires:

- **Palisades Fire** primarily affected areas with lower proportions of economically vulnerable residents (10th-40th percentile rankings)
- **Eaton Fire** disproportionately impacted communities with higher economic vulnerability (50th-90th percentile rankings), particularly in Altadena

These findings underscore the unequal distribution of climate disaster impacts and the importance of targeting recovery resources to vulnerable populations.

# References

Palisades and Eaton Dissolved Fire Perimeters. (2025). Fire perimeter shapefiles [Geospatial dataset]. ArcGIS Hub. https://hub.arcgis.com/maps/ad51845ea5fb4eb483bc2a7c38b2370c [Accessed Nov. 24, 2025]

U.S. Geological Survey. (2025). Landsat 8 Collection 2 Level-2 surface reflectance data [Satellite imagery dataset]. Microsoft Planetary Computer. https://planetarycomputer.microsoft.com/dataset/landsat-c2-l2 [Accessed Nov. 24, 2025]

Galaz García, C., Cawse-Nicholson, K., Frew, A., & Fontenot, R. (2024). EDS 220: Working with environmental datasets [Course materials]. Master of Environmental Data Science, Bren School of Environmental Science & Management, University of California, Santa Barbara. https://meds-eds-220.github.io/MEDS-eds-220-course/ [Accessed Nov. 24, 2025]

CDC/ATSDR. (2024). Environmental Justice Index (EJI). https://www.atsdr.cdc.gov/place-health/php/eji/eji-data-download.html [Accessed Nov. 24, 2025].