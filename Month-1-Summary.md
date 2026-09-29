# Month 1 Summary: Zaria LGA Groundwater Infrastructure & Healthcare IPC Vulnerability Analysis

**Author:** Umar Farouq Olatunde  
**Date:** September 2026  
**CRS:** EPSG:32632 (WGS 84 / UTM Zone 32N)  
**Data Sources:** GRID3 Nigeria, Humanitarian Data Exchange (HDX), OpenStreetMap  

---

## 1. Executive Summary & Problem Context
In healthcare delivery, Infection Prevention and Control (IPC) depends fundamentally on immediate, reliable access to clean water. Across Zaria Local Government Area (Kaduna State), health facilities often operate without on-site improved groundwater infrastructure, forcing staff and patients to fetch water from off-site sources. This spatial study evaluates the distance of all 84 registered health facilities to functional groundwater points and identifies unserved residential settlement pockets outside basic pedestrian access catchments.

---

## 2. Spatial Methodology & Analytical Workflow
All spatial operations were processed in **QGIS** using a projected metric coordinate system:
1. **Coordinate Standardization:** All layers (health facilities, water points, settlements, roads, and ward boundaries) were reprojected to **UTM Zone 32N (EPSG:32632)** to enable Euclidean metric distance calculations.
2. **Distance to Nearest Hub (`Distance to Nearest Hub - Points`):** Calculated Euclidean distance from each health facility to the closest functional water point (`HubDist`).
3. **Pedestrian Catchment Buffer (`Buffer`):** Delineated a **500 m** walking buffer around all functional groundwater points with dissolved boundaries.
4. **Vulnerability Gap Overlay (`Difference`):** Subtracted the 500 m water buffer envelope from settlement extents to isolate unserved residential blocks.
5. **Ward Aggregation (`Count Points in Polygon`):** Quantified functional groundwater supply counts across each administrative ward.

---

## 3. Expected vs. Observed Findings

| Analysis Dimension | Prior Assumption / Expected Finding | Empirical / Observed Finding | Analytical Takeaway |
| :--- | :--- | :--- | :--- |
| **Healthcare IPC Proximity** | Most primary health facilities were presumed to have co-located or immediate on-site water access (≤ 100 m) due to institutional prioritization. | **61.9% (52 of 84 facilities)** lack an on-site functional water point within 100 m. In fact, **17.9% (15 facilities)** sit in acute deficits exceeding 500 m. | Healthcare centers were built largely independent of dedicated water supply networks, turning routine hygiene into an off-site hauling burden. |
| **Settlement Walkability Catchments** | Urban wards were expected to possess near-complete 500 m walking catchment coverage, with deficits primarily confined to remote rural borders. | Extensive difference gaps exist **within dense urban settlement fabrics**, not just in peri-urban belts. | High building and population density has outpaced groundwater development, leaving central residential quarters unserved despite geographic proximity to town centers. |
| **Ward-Level Equity** | Infrastructure points were expected to be roughly evenly distributed according to administrative ward size. | Severe spatial clustering: functional counts range widely from a low of **12 points** (Gyellesu, Kufena) to **46 points** in high-density wards. | Capital allocation and maintenance have historically concentrated in specific corridors, leaving historic and peri-urban wards structurally underserved. |

---

## 4. Key Quantitative Findings

### A. Health Facility Water Access & IPC Risk
* **Total Health Facilities Evaluated:** 84
* **On-Site Access / Low Risk (≤ 100 m):** 32 facilities (38.1%)
* **Off-Site Hauling / Moderate IPC Deficit (100 m – 500 m):** 37 facilities (44.0%)
* **Severe Vulnerability (> 500 m distance):** 15 facilities (17.9%)

> **Critical Finding:** **61.9% (52 of 84)** of evaluated healthcare facilities in Zaria LGA lack an on-site functional groundwater source within 100 meters, representing an operational barrier to effective infection prevention and clinical sterilization.

### B. Ward-Level Groundwater Disparities
Administrative ward distribution shows significant infrastructure clustering:
* **Lowest Coverage:** **Gyellesu** (12 points) and **Kufena** (12 points) exhibit the lowest water infrastructure density across the LGA.
* **Secondary Deficit Wards:** **Dambo** (15), **Limancin Kofa** (15), and **Tudun Wada** (15).
* **Intermediate Deficit Wards:** **Ungwar Juma** (16) and **Kaura** (16).
* The remaining wards maintain over 30 points, peaking at 46 functional water points.

---

## 5. Analytical Map Output

![Zaria LGA WASH Gap Analysis](/Processed/Zaria_IPC_Vunerability_Map.png)

*Figure 1: Spatial distribution of healthcare IPC vulnerability tiers, 500 m groundwater walking catchments, unserved settlement gaps, and road connectivity across Zaria LGA.*
