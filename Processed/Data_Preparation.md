# Data Preparation & Quality Assurance Documentation

## 1. Coordinate Reference System (CRS) Selection

- **Chosen CRS:** WGS 84 / UTM Zone 32N (`EPSG:32632`)
- **Justification:**
  - **Geographic Alignment:** Zaria Local Government Area lies at approximately 11.08° N, 7.71° E, situated within UTM Zone 32N .
  - **Metric Units for Analysis:** Projected coordinates replace angular degrees with linear meters, which is essential for accurate distance measurements, buffer zones around health facilities/water points, and road network routing .
  - **Local Distortion:** UTM Zone 32N minimizes shape and area distortions across local administrative scales compared to geographic CRS (e.g., EPSG:4326) .

---

## 2. Preprocessing Operations

### Reprojection

All raw input datasets were reprojected from their source coordinate systems (EPSG:4326) into `EPSG:32632` :

- Health Facilities point data
- Water Points dataset
- Road network lines and junctions
- Administrative ward boundaries
- Settlement extent polygons

### Spatial Clipping & Boundary Definition

- **Study Boundary:** Formed by dissolving the internal boundaries of the Zaria Wards layer to create a single LGA perimeter polygon (`Zaria_LGA_Boundary_from_Wards`) .
- **Clipping:** All regional and national-level spatial layers were clipped to the dissolved `Zaria_LGA_Boundary_from_Wards` using the QGIS _Clip_ tool . Road stubs and peripheral points falling outside the LGA border were excluded .

---

## 3. Five Quality Checks & Decisions

| #     | Quality Check                      | Findings & Results                                                                                                                                                                 | Decision / Action Taken                                                                                                                                                                                                                                         |
| ----- | ---------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1** | **CRS Uniformity**                 | Evaluated layer properties across all imported datasets; source files had mixed EPSG:4326 and temporary on-the-fly projections .                                                   | **Fixed:** Reprojected all vector layers to uniform `EPSG:32632` prior to running spatial overlays .                                                                                                                                                            |
| **2** | **Spatial Extent & Conformance**   | Inspected bounding boxes against the Zaria LGA perimeter; found several road segment stubs and external settlement extents crossing borders .                                      | **Fixed:** Clipped all layers strictly with `Zaria_LGA_Boundary_from_Wards` as the mask layer to eliminate outer artifacts .                                                                                                                                    |
| **3** | **Geometry Validity**              | Executed QGIS _Check Validity_ on polygons; detected minor self-intersecting segments and duplicate vertices within settlement footprints .                                        | **Fixed:** Repaired using the _Fix Geometries_ processing algorithm to preserve topological consistency .                                                                                                                                                       |
| **4** | **Attribute Completeness & Nulls** | Examined attribute tables for critical fields (`facility_type`, `water_source_type`, `ward_name`) . Found non-critical missing values in secondary metadata (e.g., install date) . | **Flagged:** Preserved null values without dropping records to keep facility count totals accurate for density calculations . Filtered water points to functional units (`"status" = 'Functional'`) to prevent broken pumps from distorting IPC access metrics. |
| **5** | **Duplicate Features**             | Executed _Delete Duplicate Geometries_ across point infrastructure layers to check for multiple entries at identical GPS coordinates .                                             | **Fixed:** Identified and removed duplicate point records to prevent double-counting in access mapping .                                                                                                                                                        |

---

## 4. Analysis-Ready Output

- **Analysis-Ready GeoPackage:** [`Zaria_analysis_ready.gpkg`](https://github.com/Roukmaar/Zaria-Groundwater-Analysis/raw/refs/heads/main/Processed/Zaria_analysis_ready.gpkg)
- **QGIS Project File:** [`Zaria_IPC_Vunerability_Map.qgz`](https://github.com/Roukmaar/Zaria-Groundwater-Health-Vulnerability/blob/main/Processed/Zaria_IPC_Vunerability_Map.qgz)
- **CRS:** `WGS 84 / UTM Zone 32N (EPSG:32632)`
- **Format:** `GeoPackage (.gpkg), Compressed QGIS Project (.qgz)`
- **Produced by:** Manually processed in QGIS
- **Internal Layers:**
    ### Primary Base Layers
- `Zaria_LGA_Boundary_from_Wards_Valid` — Dissolved outer administrative perimeter polygon (EPSG:32632)
- `Zaria_Wards_UTM32N` — Administrative ward units and boundary extents (EPSG:32632)
- `Zaria_LGA_HealthFacilities_UTM32N` — Validated primary, secondary, and tertiary health facility point locations (EPSG:32632)
- `Zaria_Wards_WaterPoints_UTM32N` — Functional groundwater sources and domestic water access points (EPSG:32632)
- `Zaria_LGA_Roads_Line_UTM32N — clipped` — Clipped transport infrastructure and street network lines (EPSG:32632)
- `Zaria_LGA_Settlements_Extents_UTM32N` — Validated residential settlement footprints and built-up area extents (EPSG:32632)

    ### Derived Analytical & Geoprocessing Outputs
- `HealthFacilities-distance-to-WaterPoints` — Point distance matrix output storing calculated Euclidean distance (`HubDist` in meters) from every healthcare facility to the nearest functional water point
- `WaterPoints-500m-Buffer` — 500-meter dissolved Euclidean walking catchment envelopes representing basic pedestrian water access
- `Diff-buffer-settlements` — Spatial difference output isolating unserved settlement footprints that fall entirely outside the 500 m groundwater catchment zones
- `Zaria_Water_Points_Counts` — Administrative wards layer aggregated with functional water point count attributes (`water_points_count`)
