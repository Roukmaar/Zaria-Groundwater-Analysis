# Zaria Groundwater Infrastructure Spatial Gap Mapping Project

## Project Question

Where are the spatial gaps in borehole and well coverage across Zaria Local Government Area relative to population density and critical health facility locations.

## Why This Project Matters

Visualizing spatial gaps in groundwater infrastructure across the entire Zaria municipality guides future hydrogeological surveying and municipal drilling efforts. This ensures equitable water resource allocation for residents who lack access to formal taps, live in wards vulnerable to seasonal groundwater depletion, and protects public health by identifying healthcare facilities operating without reliable, on-site water access.

## Study Area

The study area is Zaria Local Government Area in Kaduna State, Nigeria. Zaria is a major urban center with surrounding peri-urban wards that rely on varying levels of formal and informal groundwater infrastructure.

## Data Required

1. Zaria LGA and Ward boundaries
2. Water points (boreholes, wells, and municipal taps)
3. Health facilities (primary health centres, clinics, and hospitals)
4. Population data (density and age-structured)
5. Settlement extents

## Data Sources

* **Administrative Boundaries:** GRID3 Data Hub (NGA Operational Wards)
* **Water Points:** GRID3 Data Hub (NGA Water Points), Water Point Data Exchange (WPdx), or OpenStreetMap via QuickOSM
* **Health Facilities:** GRID3 Nigeria Health Facilities or HDX Nigeria Health Sites
* **Population:** WorldPop
* **Settlements:** GRID3 Data Hub (NGA Settlement Extents)

## Planned GIS Analysis

The project will investigate the spatial relationships between existing groundwater infrastructure and:

* population distribution and density clusters
* primary healthcare centers
* ward boundaries
* settlement extents

Overlay, service catchment buffering (500m/1000m), and nearest-hub distance calculations will be used to identify underserved neighborhoods and audit health centers lacking functional water access within recommended walking thresholds.

## Expected Final Product

The final project is expected to produce a GIS-based spatial gap map showing areas of potential water resource vulnerability and institutional WASH deficits across Zaria LGA.

The project will be developed into an interactive React-based web dashboard for municipal officers and public health planners to visualize water resource allocation, audit facility-level water security, and target new drilling locations accurately.

## Data Feasibility

The required datasets have been identified and are openly available from geospatial data hubs such as GRID3, WPdx, and WorldPop. 

The most important datasets requiring careful validation are the water points and health facility, as the operational status, coordinates, and completeness of borehole locations directly affect the reliability of the proximity and gap analysis.
