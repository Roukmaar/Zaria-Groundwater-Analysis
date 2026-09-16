## Datasets

### 1. GRID3 NGA – Operational State Boundaries (Admin 1)

- **Coverage:** Nigeria
- **Geometry:** Polygon
- **Source:** https://data.grid3.org/datasets/GRID3::grid3-nga-operational-state-boundaries-/about
- **Number of Features:** 37
- **Key Columns:**
  - `statename`
  - `statecode`
  - `globalid`
- **Released:** September 2020
- **Date Updated:** 30 April 2024 at 19:28:47 GMT+1

### 2. GRID3 NGA – Operational LGA Boundaries (Admin 2)

- **Coverage:** Nigeria
- **Geometry:** Polygon
- **Source:** https://data.grid3.org/datasets/GRID3::grid3-nga-operational-lga-boundaries/about
- **Number of Features:** 774
- **Key Columns:**
  - `lgaame`
  - `lgacode`
  - `statename`
- **Released:** March 2021
- **Date Updated:** 4 September 2025 at 13:41:58 GMT+1

### 3. GRID3 NGA – Operational Wards v3.0 (Admin 3)

Provides operational ward boundary polygons for 24 states in Nigeria.

- **Coverage:** 24 states-Abia, Adamawa, Bauchi, Bayelsa, Borno, Delta, Enugu, FCT Abuja, Gombe, Jigawa, Kaduna, Kano, Katsina, Kebbi, Kogi, Kwara, Nasarawa, Niger, Ogun, Osun, Oyo, Sokoto, Yobe, Zamfara
- **Geometry:** Polygon
- **Source:** https://data.humdata.org/dataset/grid3-nga-operational-wards-v3-0
- **Number of Features:** 5,872
- **Key Columns:**
  - `lga`
  - `ward`
  - `ward_alt_name`
  - `area_sqkm`
- **Released:** June 2026
- **Date Updated:** 5 July 2026 at 18:37:18 GMT+1
- **Note:** Operational boundaries that have not yet undergone full validation by relevant government authorities. 0

### 4. GRID3 NGA – Settlement Extents v4.1

Geographic representation of settlements in Nigeria, including settlement blocks within urban and small settlement areas.

- **Coverage:** Nigeria
- **Geometry:** Polygon
- **Source:** https://data.grid3.org/datasets/GRID3::grid3-nga-settlement-extents-v4-0/about
- **Number of Features:** 2,546,560
- **Key Columns:**
  - `extent_type`
  - `block_area_sqm`
  - `building_count`
- **Released:** July 2026
- **Date Updated:** 4 August 2026 at 18:29:49 GMT+1

### 5. GRID3 NGA – Health Facilities v3.0

Non-exhaustive, non-validated geographic representation of health facility points.

- **Coverage:** 24 states-Abia, Adamawa, Bauchi, Bayelsa, Borno, Delta, Enugu, FCT Abuja, Gombe, Jigawa, Kaduna, Kano, Katsina, Kebbi, Kogi, Kwara, Nasarawa, Niger, Ogun, Osun, Oyo, Sokoto, Yobe, Zamfara
- **Geometry:** Point
- **Source:** https://data.grid3.org/datasets/827e3638dc204f4b9ddbbd19b00954d6
- **Number of Features:** 41,778
- **Key Columns:**
  - `facility_name`
  - `facility_type`
  - `facility_ownership`
- **Released:** August 2026
- **Date Updated:** 14 August 2026
- **Status:** Operational

### 6. WorldPop – 2025 Population

Constrained estimates of the total number of people per grid cell for 2025.

- **Coverage:** Nigeria
- **Format:** GeoTIFF
- **Geometry:** Raster
- **Source:** https://hub.worldpop.org/geodata/summary?id=52307
- **Resolution:** 3 arc-seconds (~100 m at the equator)
- **Number of Features:** Not applicable — raster dataset
- **Key Data:**
  - Population count per pixel
- **Projection:** Geographic Coordinate System (WGS84)
- **Units:** Number of people per pixel
- **Mapping Approach:** Random Forest-based dasymetric redistribution
- **Date Updated:** 2025

### 7. GRID3 NGA – Water Points

Water points and names in Nigeria.

- **Coverage:** Nigeria
- **Geometry:** Point
- **Source:** https://data.grid3.org/datasets/grid3-nga-water-points/about
- **Number of Features:** Not specified
- **Key Columns:**
  - Water point name
  - Water point location
- **Released:** September 2020
- **Date Updated:** 4 September 2025
- **Note:** Dataset is incomplete for the country.

### 8. WPDx – Water Point Data Exchange (NGA)

Crowdsourced data focused on rural water points, including wells, springs, and tapstands.

- **Coverage:** Nigeria
- **Geometry:** Point
- **Source:** https://data.humdata.org/m/dataset/wpdx_nga?hl=en-US
- **Number of Features:** 99,246
- **Key Columns:**
  - `water_source_tech`
  - `install_year`
- **Date Updated:** 26 July 2026

### 9. OpenStreetMap (OSM) – Highways

Highway and road network data downloaded through the QGIS QuickOSM plugin.

- **Coverage:** Study area
- **Query:** Highway 
- **Geometry:** Line
- **Source:** OoenStreetMap via QuickOSM plugin in QGIS
- **Number of Features:** 7,461
- **Key Columns:**
  - `highway`
  - `name`
  - `surface`
- **Source:** OpenStreetMap (OSM)
- **Acquisition:** QGIS QuickOSM plugin
- **Data Type:** Highways / road network
