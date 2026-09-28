# Month 1 Summary

## Project Question

How can rainfall data, terrain, and land-surface factors be integrated to identify areas of changing flood risk across Abuja Municipal Area Council (AMAC) following heavy rainfall?

## Operation Run and Why

I ran a **500 m buffer operation** on the clipped river layer within AMAC. I chose the buffer operation because proximity to waterways can be used as one of the spatial factors for assessing flood susceptibility. The buffer creates a zone around the mapped rivers showing areas located within 500 metres of the river.

The river and stream data were initially downloaded from OpenStreetMap using QuickOSM and clipped to the AMAC study area. The clipped data were then reprojected to **EPSG:32632 (WGS 84 / UTM Zone 32N)**, a projected coordinate system with metre-based units suitable for distance and area calculations.

## What I Expected and What I Got

| What I expected | What I got |
|---|---|
| A buffer zone extending 500 metres around the mapped rivers within AMAC. | A 500 m river buffer was successfully created around the mapped rivers in AMAC. |
| The buffer should show areas located within 500 m of the rivers. | The resulting map shows the areas within the 500 m proximity zone around the rivers. |
| The buffer should remain within the AMAC study area. | The buffer was created from the clipped river layer, keeping the analysis within the AMAC study area. |
| The operation should produce a spatial dataset that can support the wider flood-risk analysis. | The resulting buffer provides a waterway-proximity layer that can potentially be combined with rainfall, terrain, and other land-surface factors in the wider flood-risk analysis. |

## What Surprised Me

I initially expected the buffer to directly represent areas that are at risk of flooding. However, I learned that a buffer only represents proximity to a feature. A 500 m river buffer identifies areas within 500 metres of a river, but it does not mean that all areas within the buffer will necessarily flood.

This reinforced the importance of combining multiple factors in the final flood-risk analysis, including rainfall, elevation, slope, flow accumulation, land cover, and proximity to waterways.

I also observed that some OpenStreetMap attributes contain NULL values. These were mainly found in optional attribute fields and do not necessarily indicate invalid geometry or missing spatial features.

## What Data I Still Need

The project still requires the following datasets and derived variables:

- Rainfall data with a temporal component to capture changing rainfall conditions following heavy rainfall.
- Digital Elevation Model (DEM).
- Slope derived from the DEM.
- Flow direction and flow accumulation derived from the DEM.
- Land-cover data.
- Distance or proximity to waterways.
- Road network data for assessing potential infrastructure exposure.
- Population data for assessing potential population exposure.
- Historical or observed flood extent data for validating the flood-risk results.

## Data Preparation

The source data were initially in **EPSG:4326 (WGS 84)**. The AMAC study area was extracted from GRID3 data, and the relevant spatial layers were clipped to the study area.

The clipped layers were then reprojected to **EPSG:32632 (WGS 84 / UTM Zone 32N)** because it is a projected coordinate system using metres, making it suitable for distance and area calculations.

The AMAC study area was calculated from the projected geometry and was approximately **1,446.57 km²**.

Raw source data were kept unchanged, while processed and derived datasets were stored separately for analysis.

## Final Output

The final output is a map of AMAC showing the **500 m river buffer** around the mapped rivers. The output demonstrates how proximity to waterways can be represented spatially and provides one potential input for the wider dynamic flood-risk analysis.

The final map has been uploaded to the project repository.

Repository commit:  
![Map Showing AMAC 500 m River Buffer](./Buffer%20layer.png)
