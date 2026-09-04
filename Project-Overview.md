# Zaria Groundwater Infrastructure & Health Facility Spatial Gap Mapping Project

## Project Question

Where are the spatial gaps in borehole and well coverage across Zaria Local Government Area relative to population density and primary healthcare facilities?

## Why This Project Matters

Visualizing spatial gaps in groundwater infrastructure across Zaria guides future hydrogeological surveying, municipal drilling programs, and preventative pump maintenance. Incorporating health facilities directly addresses institutional Water, Sanitation, and Hygiene (WASH) vulnerabilities, ensuring that both underserved residential settlements and frontline medical clinics obtain equitable, reliable, and hygienic water supplies.

## Study Area

The study area is Zaria Local Government Area (LGA) in Kaduna State, Nigeria. Zaria is a major urban and institutional center with surrounding peri-urban and rural wards underlain by crystalline basement complex hydrogeology, where communities and public facilities rely heavily on decentralized boreholes and hand-dug wells.

## Data Required

1. Zaria LGA and operational ward boundaries
2. Water points (boreholes, improved wells, and municipal taps with functionality statuses)
3. Health facilities (primary health centres, clinics, hospitals)
4. Population data (gridded density and distribution)
5. Settlement extents (built-up footprints and hamlets)

## Data Sources

* **Administrative Boundaries:** GRID3 Data Hub (GRID3 Nigeria Operational Wards v3.0)
* **Water Points:** Water Point Data Exchange (WPdx Nigeria) and GRID3 Data Hub (NGA Water Points)
* **Health Facilities:** GRID3 Nigeria Health Facilities / HDX Nigeria Health Facilities
* **Population:** WorldPop Nigeria (100m constrained resolution)
* **Settlements:** GRID3 Data Hub (GRID3 NGA Settlement Extents)

## Planned GIS Analysis

The project will investigate spatial relationships between groundwater infrastructure and:

* Ward boundaries and administrative distribution
* Population distribution and high-density settlement extents
* Healthcare facility perimeters and accessibility corridors

Planned spatial processing includes:
* Reprojecting datasets to **WGS 84 / UTM Zone 32N (`EPSG:32632`)** for accurate metric calculations.
* Generating **500m** and **1,000m** walking distance service buffers around functional water points (per WHO/UNICEF JMP standards).
* Running **Nearest Hub Distance Analysis** to determine whether healthcare centers have immediate (<100m), accessible (<500m), or critical (>500m deficit) water security.
* Overlaying buffer gaps with population raster grids and settlement polygons to isolate underserved clusters.

## Expected Final Product

The final project will produce an analytical GIS spatial gap model and an interactive React-based web dashboard (powered by Leaflet). 

The dashboard will feature interactive ward selectors, layer toggles for functional versus broken infrastructure, and institutional WASH vulnerability badges to assist municipal officers, RUWASSA, and public health planners in targeting new drilling locations and prioritizing maintenance.

## Data Feasibility

All core datasets have been verified and acquired from open geospatial repositories (GRID3, WPdx, and WorldPop).

The ward boundaries and WPdx water point layer (filtered to 275 records for Zaria LGA) have already been ingested, validated, and visually confirmed in QGIS, ensuring high feasibility for immediate buffering, healthcare facility joins, and web dashboard integration.
