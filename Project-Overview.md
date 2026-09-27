# Zaria Groundwater Infrastructure & Health Facility Vulnerability Mapping Project

## Project Question

Where are the critical spatial gaps in borehole and well coverage across Zaria Local Government Area relative to population density, and how do these deficits compound infection transmission risks at primary healthcare facilities and high-density settlements ?

## Why This Project Matters

Visualizing spatial gaps in groundwater infrastructure across the entire Zaria municipality guides future hydrogeological surveying and municipal drilling efforts . This ensures equitable water resource allocation for residents who lack access to formal taps and live in wards vulnerable to seasonal groundwater depletion .

Crucially, it protects public health by auditing healthcare facilities operating without reliable, on-site water access . When clinics lack running water, basic Infection Prevention and Control (IPC) fails, turning primary health centers into high-risk vectors during outbreaks of infectious diseases (such as waterborne pathogens or respiratory and contact illnesses like diphtheria). Furthermore, severely congested community water points force prolonged queuing, elevating interpersonal exposure in underserved wards.

## Study Area

The study area is Zaria Local Government Area in Kaduna State, Nigeria . Zaria is a major urban center with surrounding peri-urban wards that rely on varying levels of formal and informal groundwater infrastructure .

![Zaria LGA Settlements and Road Networks](Processed/Zaria-Mini-Project.png)

## Data Required

1. Zaria LGA and Ward boundaries
2. Water points (boreholes, wells, and municipal taps)
3. Health facilities (primary health centres, clinics, and hospitals)
4. Population data (density and age-structured)
5. Settlement extents
6. Road and transport network

## Data Sources

- **Administrative Boundaries:** GRID3 Data Hub (NGA Operational Wards)
- **Water Points:** GRID3 Data Hub (NGA Water Points), Water Point Data Exchange (WPdx), or OpenStreetMap via QuickOSM
- **Health Facilities:** GRID3 Nigeria Health Facilities or HDX Nigeria Health Sites
- **Population:** WorldPop
- **Settlements:** GRID3 Data Hub (NGA Settlement Extents)
- **Roads:** OpenStreetMap via QuickOSM plugin

## Planned GIS Analysis

The project will investigate the spatial relationships between existing groundwater infrastructure and:

- Population distribution and density clusters
- Primary healthcare centers and institutional IPC compliance
- Administrative ward boundaries
- Settlement extents

### Key Spatial Operations & Public Health Translation

- **Distance to Nearest Hub ("How far is A from B?"):** Calculates the metric distance from each healthcare facility to the nearest functional water point. Clinics >100 m from a functional supply are flagged as having compromised IPC and elevated outbreak transmission risks.
- **Catchment Buffering ("Within X metres of..."):** Delineates 500 m and 1000 m walking access zones around functional water points to define community service footprints.
- **Difference ("The part of A that is outside B"):** Subtracts water coverage buffers from residential settlement extents to isolate unserved community gap pockets.
- **Spatial Join / Count Points in Polygon ("How many A are in each B?"):** Aggregates functional water points by ward to compute water-point-to-population ratios, identifying congested wards prone to crowd-related disease exposure.

## Expected Final Product

The final project will produce a GIS-based spatial gap map showing areas of potential water resource vulnerability and institutional WASH deficits across Zaria LGA .

The project will be developed into an interactive React-based web dashboard for municipal officers and public health planners to visualize water resource allocation, audit facility-level water security, and target new drilling locations accurately .

## Data Feasibility

The required datasets have been identified and are openly available from geospatial data hubs such as GRID3, WPdx, and WorldPop .

The most important datasets requiring careful validation are the water points and health facilities, as the operational status, coordinates, and completeness of borehole locations directly affect the reliability of the proximity and gap analysis .
