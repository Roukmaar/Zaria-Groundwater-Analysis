# Data Preparation & Quality Assurance Documentation

## 1. Coordinate Reference System (CRS) Selection

* **Chosen CRS:** WGS 84 / UTM Zone 32N (`EPSG:32632`)
* **Justification:**
  * **Geographic Alignment:** Zaria Local Government Area lies at approximately 11.08° N, 7.71° E, situated within UTM Zone 32N.
  * **Metric Units for Analysis:** Projected coordinates replace angular degrees with linear meters, which is essential for accurate distance measurements, buffer zones around health facilities/water points, and road network routing.
  * **Local Distortion:** UTM Zone 32N minimizes shape and area distortions across local administrative scales compared to geographic CRS (e.g., EPSG:4326).

---

## 2. Preprocessing Pipeline

### Reprojection
All raw input datasets were reprojected from their source coordinate systems (EPSG:4326) into `EPSG:32632`:
* Health Facilities point data
* Water Points dataset
* Road network lines and junctions
* Administrative ward boundaries
* Settlement extent polygons

### Spatial Clipping & Boundary Definition
* **Study Boundary:** Formed by dissolving the internal boundaries of the Zaria Wards layer to create a single LGA perimeter polygon (`Zaria_LGA_Boundary_from_Wards`).
* **Clipping:** All regional and national-level spatial layers were clipped to the dissolved `Zaria_LGA_Boundary_from_Wards` using the QGIS *Clip* tool. Road stubs and peripheral points falling outside the LGA border were excluded.

---

## 3. Five Quality Checks & Decisions

| # | Quality Check | Findings & Results | Decision / Action Taken |
|---|---|---|---|
| **1** | **CRS Uniformity** | Evaluated layer properties across all imported datasets; source files had mixed EPSG:4326 and temporary on-the-fly projections. | **Fixed:** Reprojected all vector layers to uniform `EPSG:32632` prior to running spatial overlays. |
| **2** | **Spatial Extent & Conformance** | Inspected bounding boxes against the Zaria LGA perimeter; found several road segment stubs and external settlement extents crossing borders. | **Fixed:** Clipped all layers strictly with `Zaria_LGA_Boundary_from_Wards` as the mask layer to eliminate outer artifacts. |
| **3** | **Geometry Validity** | Executed QGIS *Check Validity* on polygons; detected minor self-intersecting segments and duplicate vertices within settlement footprints. | **Fixed:** Repaired using the *Fix Geometries* processing algorithm to preserve topological consistency. |
| **4** | **Attribute Completeness & Nulls** | Examined attribute tables for critical fields (`facility_type`, `water_source_type`, `ward_name`). Found non-critical missing values in secondary metadata (e.g., install date). | **Flagged:** Preserved null values without dropping records to keep facility count totals accurate for density calculations. |
| **5** | **Duplicate Features** | Executed *Delete Duplicate Geometries* across point infrastructure layers to check for multiple entries at identical GPS coordinates. | **Fixed:** Identified and removed duplicate point records to prevent double-counting in access mapping. |

---

## 4. Analysis-Ready Output

* **Analysis-Ready GeoPackage:** [`Zaria_analysis_ready.gpkg`](https://github.com/Roukmaar/Zaria-Groundwater-Analysis/raw/refs/heads/main/Processed/Zaria_analysis_ready.gpkg)
* **QGIS Project File:** [`Zaria_LGA_Analysis.qgz`](https://github.com/Roukmaar/Zaria-Groundwater-Analysis/raw/refs/heads/main/Processed/Zaria_LGA_WaterPonts+HealthFacilities+Roads+Settlements.qgz)
* **CRS:** `WGS 84 / UTM Zone 32N (EPSG:32632)`
* **Format:** `GeoPackage (.gpkg), Compressed QGIS Project (.qgz)`
* **Produced by:** Manually processed in QGIS
* **Internal Layers:**
  * `Zaria_LGA_Boundary_from_Wards` — Dissolved perimeter polygon
  * `Zaria_Wards_UTM32N` — Administrative ward units (EPSG:32632)
  * `Zaria_LGA_HealthFacilities_UTM32N` — Primary and secondary health facility points
  * `Zaria_Wards_WaterPoints_UTM32N` — Groundwater and domestic water access points
  * `Zaria_LGA_Roads_Line_UTM32N - clipped` — Clipped transport network lines
  * `Zaria_LGA_Settlements_Extents_UTM32N` — Validated built-up area polygons
