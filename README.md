# Zaria Groundwater Infrastructure Spatial Gap Mapping

## Project Overview

This project uses Geographic Information Systems (GIS) to assess spatial gaps in groundwater infrastructure and evaluate equitable water resource allocation for communities and critical public healthcare facilities in Zaria Local Government Area, Kaduna State, Nigeria. 

## Main Research Question

Where are the spatial gaps in borehole and well coverage across Zaria Local Government Area relative to population density and primary healthcare facility locations.

## Key Datasets & Sources
  
| Dataset | Source / Link | Geometry Type | NOs. of Features | Key Columns | Note / Gaps | Size | Last Updated |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **State Boundaries (Admin 1)** | [GRID3 NGA State Boundaries](https://data.grid3.org/datasets/GRID3::grid3-nga-operational-state-boundaries-/about) | Polygon | 37 | `statename`, `statecode`, `globalid` | Complete country coverage | 1.2MB | 30 Apr 2024 |
| **LGA Boundaries (Admin 2)** | [GRID3 NGA LGA Boundaries](https://data.grid3.org/datasets/GRID3::grid3-nga-operational-lga-boundaries/about) | Polygon | 774 | `lgaame`, `lgacode`, `statename` | Complete country coverage | 4.3MB | 4 Sept 2025 |
| **Ward Boundaries (Admin 3)** | [GRID3 NGA Wards v3.0](https://data.humdata.org/dataset/grid3-nga-operational-wards-v3-0) | Polygon | 5,872 | `lga`, `ward`, `ward_alt_name`, `area_sqkm` | Only 24 states. Operational, not fully validated by govt | 190MB | 5 Jul 2026 |
| **Settlement Extents v4.1** | [GRID3 NGA Settlement Extents](https://data.grid3.org/datasets/GRID3::grid3-nga-settlement-extents-v4-0/about) | Polygon | 2,546,560 | `extent_type`, `block_area_sqm`, `building_count` | Nationwide. Blocks derived from roads, buildings, rivers | 2.0GB | 4 Aug 2026 |
| **Health Facilities v3.0** | [GRID3 NGA Health Facilities](https://data.grid3.org/datasets/827e3638dc204f4b9ddbbd19b00954d6) | Point | 41,778 | `facility_name`, `facility_type`, `facility_ownership` | 24 states. Non-exhaustive, operational dataset | 16MB | 14 Aug 2026 |
| **Population 2025** | [WorldPop Nigeria 100m](https://hub.worldpop.org/geodata/summary?id=52307) | Raster | ----- | `population_per_pixel` | Constrained 2025 estimates. ~100m resolution, WGS84, GeoTIFF | 158MB | 2025 |
| **Water Points** | [WPdx Nigeria](https://data.humdata.org/m/dataset/wpdx_nga?hl=en-US) + [GRID3 Water Points](https://data.grid3.org/datasets/grid3-nga-water-points/about) | Point | 99,246 | `water_source_tech`, `install_year` | Incomplete coverage. GRID3 + crowdsourced WPdx | 7.5MB | 26 Jul 2026 |
| **Road Network** | [QuickOSM - OpenStreetMap](https://www.openstreetmap.org/) | Line | 7461 | `highway`, `name`, `surface` | Downloaded via QGIS QuickOSM plugin. Urban areas more complete than rural | ----- | 10 Sept 2026  |

## Project Goal

The project aims to use GIS spatial analysis to examine the relationship between existing water points, settlement patterns, and population density, while auditing Water, Sanitation, and Hygiene (WASH) accessibility for primary healthcare facilities. The resulting spatial gap map for Zaria LGA will guide future hydrogeological surveying, municipal drilling efforts, and targeted institutional maintenance.

## Expected Output

The final output will be a GIS-based spatial map and a React-based interactive dashboard identifying underserved neighborhoods and unserved healthcare facilities by overlaying population clusters with functional water infrastructure.

The project will be developed into an interactive web dashboard for municipal officers and public health planners to target new drilling locations accurately.

## Project Status

| Weeks | Achievements |
| :--- | :--- |
| Week 1 | Project definition and data feasibility completed |
| Week 2 | Datasets downloaded, inspected and confirmed in QGIS |
