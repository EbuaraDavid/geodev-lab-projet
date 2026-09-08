## **Part 1: The Question**

**How can rainfall data and geospatial terrain and land-surface factors be integrated to identify areas of changing flood risk across AMAC  following heavy rainfall?**

## **Part 2: Why It Matters**

Flooding is a recurring problem in AMAC  during periods of heavy rainfall and can disrupt roads, damage property and affect people’s movement. The project is also relevant to my interest in moving from traditional geospatial analysis towards automated geospatial systems that can update results when input variables change.

## **Part 3/4: The Data I Need**

* **Study area boundary for AMAC** to define the area covered by the analysis. **Source: GRID3 Data Hub —** [data.grid3.org](https://data.grid3.org?utm_source=chatgpt.com)  
* **Digital Elevation Model (DEM)** to identify elevation and derive terrain variables. **Source: OpenTopography —** [portal.opentopography.org](https://portal.opentopography.org?utm_source=chatgpt.com)  
* **Slope**, derived from the DEM, to represent the influence of terrain steepness on surface-water movement. **Source: Derived from the DEM obtained from OpenTopography —** [portal.opentopography.org](https://portal.opentopography.org?utm_source=chatgpt.com)  
* **Flow direction and flow accumulation**, derived from the DEM, to identify likely pathways and areas where water may concentrate. **Source: Derived from the DEM obtained from OpenTopography —** [portal.opentopography.org](https://portal.opentopography.org?utm_source=chatgpt.com)  
* **Rivers, streams and other mapped waterways** to identify areas close to natural water channels. **Source: OpenStreetMap via QuickOSM in QGIS, or HOT exports on HDX —** [data.humdata.org](https://data.humdata.org?utm_source=chatgpt.com)  
* **Distance to waterways**, derived from the waterway data, to assess proximity to potential flood pathways. **Source: Derived from OpenStreetMap waterway data —** [data.humdata.org](https://data.humdata.org?utm_source=chatgpt.com)  
* **Road network data** to identify roads that may be affected by high flood-risk conditions. **Source: OpenStreetMap via QuickOSM in QGIS, or HOT exports on HDX —** [data.humdata.org](https://data.humdata.org?utm_source=chatgpt.com)  
* **Land-cover data** to distinguish built-up areas, vegetation and other land surfaces that influence surface runoff. **Source: Sentinel-2 imagery from Copernicus Data Space Ecosystem —** [dataspace.copernicus.eu](https://dataspace.copernicus.eu?utm_source=chatgpt.com)  
* **Rainfall data** to represent changing rainfall conditions and update the flood-risk assessment. **Source: CHIRPS —** [chc.ucsb.edu/data/chirps](https://chc.ucsb.edu/data/chirps?utm_source=chatgpt.com)  
* **Population data** to estimate the number of people potentially exposed to higher flood-risk areas. **Source: WorldPop —** [worldpop.org](https://www.worldpop.org?utm_source=chatgpt.com)

## **Part 5: What I Would Build**

I would build an **interactive flood-risk map and dashboard for AMAC**  that shows areas with low, moderate and high flood risk under changing rainfall conditions. The system would combine relatively stable geographic factors, such as terrain, waterways and land cover, with rainfall data so that the flood-risk assessment can be updated when rainfall conditions change.

The final product would also show roads and populations located within higher-risk areas, allowing users to identify places that may require greater attention following periods of heavy rainfall.